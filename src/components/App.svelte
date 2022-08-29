<script>
  import Meta from "./Meta.svelte"
  import Header from "./stand/Header.svelte"
  import Icon from "./helpers/Icon.svelte"
  import Footer from "./stand/Footer.svelte"
  import inView from "$actions/inView.js";
  import content from "$data/copy.json"
  import {fade,fly} from 'svelte/transition';
  import {Container,Row,Col,TabContent, TabPane, Carousel, CarouselControl, CarouselIndicators, CarouselItem} from 'sveltestrap'
  import viewport from "$stores/viewport.js"
  import Boundary from "../components/helpers/Boundary.svelte"
  let isInView;
  let tabView = "c1";
  let tabUrl;
  const items = [
    'tegan',
    'ubcic'
  ];
  let activeIndex = 0;


</script>

<Meta />

<section class="cover" style="height:{$viewport.height-8}px;background-image:url('assets/ogbg.jpeg')">
  <div class="overlay">
    <Header />
    <div class="cover-content">
    </div>
  </div>
</section>
<section class="intro" style="margin-top:-{$viewport.height/2}px;">
  <Container>
    <Row>
      <Col sm=12 md=8 lg=8>
        <h1>{content.Title}</h1>
        <h3>{content.Intro} <span class="highlight"> {content.Highlight}</span></h3>
      </Col>
      <Col sm=12 md=4 lg=4>
        <div class="primary-nav">
          <a href="#map">Explore the map</a>
          <a href="#evidence">See the evidence</a>
          <a href="#timeline">How we got here</a>
          <div class="social-share">
            <a target="_new" href="https://www.facebook.com/sharer.php?u=https%3A%2F%2Fpublications.stand.earth%2Fold-growth"><button class="facebook"><Icon name="facebook" stroke="var(--white)" stroke-width=2 width="30" /></button></a>
            <a target="_new" href="https://twitter.com/intent/tweet?url=https%3A%2F%2Fpublications.stand.earth%2Fold-growth%2F&via=standearth&text=text=Check%20out%20this%20website%20%40standearth%20just%20launched%20exposing%20B.C.%E2%80%99s%20%23oldgrowth%20scandal%F0%9F%98%A1%20This%20irrefutable%20evidence%20proves%20that%20the%20%40bcndp%20has%20been%20engaging%20in%20a%20disinformation%20campaign,%20grandstanding%20protecting%20these%20ancient%20forests%20when%20they%E2%80%99re%20still%20being%20logged%20by%20big%20corporations"><button class="twitter"><Icon name="twitter" stroke="var(--white)" stroke-width=2 width="30"/></button></a>
          </div>
      </div>
      </Col>
    </Row>
</Container>
</section>
<section class="map">
  <Boundary left_spacing='50' color='var(--white)' orientation='triangle'/> 
    <div class="map-content">
      <Container>
        <Row>
          <div style="margin-top:-{$viewport.height/6}px;" use:inView={{ bottom: 250 }} on:enter={( ) => isInView="visible"} on:exit={() => isInView="nope"}>
            <Col sm=12 md={{size:8,offset:2}} lg={{size:8,offset:2}}>
              {#if isInView == "visible"}
              <div class="deferral" transition:fly="{{ y: 200, duration: 1000 }}">
                <h3><i>{content.Deferral.Title}</i></h3>
                <p>{@html content.Deferral.Content} </p>
              </div>
              {/if}
            </Col>
          </div>
        </Row>
        <Row>
          <Col sm=12 md={{size:10, offset:1}} lg={{size:10, offset:1}}>
            <a name="map"></a>
            <h2>{content.Map.Heading}</h2>
            <p>{content.Map.Subheading}</p>
          </Col>
        </Row>
      </Container>
      <iframe src="https://angio.maps.arcgis.com/apps/instant/sidebar/index.html?appid=52786208488e4e58a83fbe05db14c50c" width="100%" height="700" frameborder="0" style="border:0" allowfullscreen>iFrames are not supported on this page.</iframe>  
    </div>
</section>

<section class="evidence">

  <div id="evidence-header" style="background-image:url('assets/cover3.jpeg');">
    <div id="evidence-copy">
      <h2>{content.Evidence.Heading}</h2>
      <p style='padding-bottom:50px;'>{content.Evidence.Subheading}</p>
    </div>
  </div>
  <div class="navigation">
    <!-- svelte-ignore a11y-missing-content -->
    <a name="evidence"></a>
    <Container>
  
      <Row>
      <Col sm=12 md=12 lg=12>
    <TabContent pills on:tab={(e) => (tabView = e.detail)}>
      <TabPane tabId="c1" active>
        <span slot="tab">
          <h4>Sinclair Group</h4>
        </span>
        
          {#if tabView == "c1"}
          <div class="clearcut" transition:fly="{{ y: 200, duration: 1000 }}">
            <p><i> Candidate deferral in the north-central interior, logged by Sinclair Group. Deferral outlined in green, logged area shaded red.</i></p>
            <iframe frameborder="0" class="juxtapose" width="100%" height="700" src="https://cdn.knightlab.com/libs/juxtapose/latest/embed/index.html?uid=b6cf8e06-256c-11ed-b5bb-6595d9b17862"></iframe>
            
          </div>  
          {/if}
        
      </TabPane>
      <TabPane tabId="c2">
        <span slot="tab">
          <h4>Canfor</h4>
        </span> 
        {#if tabView == "c2"}
          <div class="clearcut" transition:fly="{{ y: 200, duration: 1000 }}">
            <p> Candidate deferral in the north-central interior, logged by Canfor. Deferral outlined in green, logged area shaded red.</p>
            <iframe frameborder="0" class="juxtapose" width="100%" height="700" src="https://cdn.knightlab.com/libs/juxtapose/latest/embed/index.html?uid=2d9a1362-27e8-11ed-b5bb-6595d9b17862"></iframe>
          </div>  
        {/if}
      </TabPane>
      <TabPane tabId="c3">
        <span slot="tab">
          <h4>Western Forest Products</h4>
        </span> 
        {#if tabView == "c3"}
          <div class="clearcut" transition:fly="{{ y: 200, duration: 1000 }}">
            <p> Candidate deferral in coastal Vancouver Island, logged by Western Forest Products. Deferral outlined in green, logged area shaded red.</p>
            <iframe frameborder="0" class="juxtapose" width="100%" height="700" src="https://cdn.knightlab.com/libs/juxtapose/latest/embed/index.html?uid=5107bcd4-27cd-11ed-b5bb-6595d9b17862"></iframe>
          </div>  
        {/if}
      </TabPane>
      <TabPane tabId="c4">
        <span slot="tab">
          <h4>Coastal GasLink</h4>
        </span> 
        {#if tabView == "c4"}
          <div class="clearcut" transition:fly="{{ y: 200, duration: 1000 }}">
            <p> Candidate deferral in the north-west of BC, logged by Coastal GasLink. Deferral outlined in green, logged area shaded red.</p>
            <iframe frameborder="0" class="juxtapose" width="100%" height="700" src="https://cdn.knightlab.com/libs/juxtapose/latest/embed/index.html?uid=7b57bab4-27e8-11ed-b5bb-6595d9b17862"></iframe>
          </div>  
        {/if}
      </TabPane>
      <TabPane tabId="c5">
        <span slot="tab">
          <h4>West Fraser</h4>
        </span> 
        {#if tabView == "c5"}
          <div class="clearcut" transition:fly="{{ y: 200, duration: 1000 }}">
            <p> Candidate deferral in the Cariboo, logged by West Fraser. Deferral outlined in green, logged area shaded red.</p>
            <iframe frameborder="0" class="juxtapose" width="100%" height="700" src="https://cdn.knightlab.com/libs/juxtapose/latest/embed/index.html?uid=aa48d5bc-27cd-11ed-b5bb-6595d9b17862"></iframe>
          </div>  
        {/if}
      </TabPane>
      <TabPane tabId="c6">
        <span slot="tab">
          <h4>Trans Mountain</h4>
        </span> 
        {#if tabView == "c6"}
          <div class="clearcut" transition:fly="{{ y: 200, duration: 1000 }}">
            <p> Candidate deferral in the southern interior, logged by Trans Mountain. Deferral outlined in green, logged area shaded red. </p>
            <iframe frameborder="0" class="juxtapose" width="100%" height="700" src="https://cdn.knightlab.com/libs/juxtapose/latest/embed/index.html?uid=6ade917c-27ce-11ed-b5bb-6595d9b17862"></iframe>
          </div>  
        {/if}
      </TabPane>
    </TabContent>
    </Col>
  </Row>
    <div class="report">
      <Row>
      <Col sm=12>
        <a href="https://www.stand.earth/sites/stand/files/tall_talk_final.pdf"><h2>Download the full report from Stand.earth Research Group <Icon name="download" stroke="var(--stand-primary)" stroke-width=2 width="40" /></h2><img src="assets/report_cover.png"></a>
      </Col>
    </Row>
    </div>  
  </Container>
  </div>
</section>

<section class="timeline">
  <Boundary left_spacing='17' color='var(--white)' orientation='triangle'/> 
  <div class="timeline-content">
    <Container>
      <Row>
        <Col sm=12 md=4 lg=4>
          <a name="timeline"></a>
          <h2>{content.Timeline.Headline}</h2>
          <p>{content.Timeline.Description}</p>
        </Col>
        <Col sm=12 md=8 lg=8>
          <iframe src='https://cdn.knightlab.com/libs/timeline3/latest/embed/index.html?source=1h7qOZecmsiWzR0kaWz52Z1RnEzbUObX4Cz4WlhcBUP8&font=Default&lang=en&initial_zoom=2&height=650' width='100%' height='650' webkitallowfullscreen mozallowfullscreen allowfullscreen frameborder='0'></iframe>                            
        </Col>
      </Row>
    </Container>
  </div>
</section>

<section class="video">
  <Boundary left_spacing='17' color='var(--white)' orientation='triangle'/> 
  <div class="video-content">
    <Container>
      <Row>
        <Col sm=12 md=12 lg=12>
          <a name="video"></a>
          <h2 style="text-align:center;padding-bottom:20px;">The Whole World Is Watching</h2>
          <p>{content.Quote}</p>
        </Col>
      </Row>
      <Row>
        <Col sm=12 md={{size:6,offset:3}} lg={{size:6,offset:3}}>
          <iframe width="100%" height="415" src="https://www.youtube.com/embed/EfyEYE650t8?controls=0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </Col>
        </Row>
      </Container>
          
          <Carousel {items} bind:activeIndex>
            <CarouselIndicators bind:activeIndex {items} />
          
            <div class="carousel-inner">
              {#each items as item, index}
                <CarouselItem bind:activeIndex itemIndex={index}>
                  {#if activeIndex==0}
                  <div class="carousel-wrapper" style="background-image:url('assets/quote.jpeg');">
                    <div id="quotecopy">
                    
                      <p><i>"The current divisive picture of old growth logging has been, and continues to be, exacerbated by the B.C. government fostering an economic dependence on logging for First Nations through limited revenue-sharing, joint ventures, employment, and tenures in contentious areas where First Nations face limited alternate economic opportunities as a result of years of colonialism and racism."</i></p>
                      <p><a href="https://assets.nationbuilder.com/ubcic/pages/132/attachments/original/1655425546/2022_CC06_Combined_Resolutions.pdf?1655425546">Resolution no. 2022-28</a></p>  
                      <p style="font-size:11px;"><i>Image credit: Alex Tsui, Wilderness Committee.</i></p>
                  </div>
                  </div>
                  {/if}
                  {#if activeIndex==1}
                  <div class="carousel-wrapper2" style="background-image:url('assets/quote2.jpeg');">
                    <div id="quotecopy">
                    
                      <p><i>"The evidence of the scale and severity of ongoing logging in proposed deferral areas means that, at best, provincial officials are completely unaware of what’s happening and trusting the word of corporations who profit from cutting down these forests. At worst, the province is engaging in a disinformation campaign to convince constituents that it is fulfilling its promises to protect old growth forests while actually avoiding meaningful action to curtail the industry."</i></p>
                      <p><b>Angeline Robertson, Senior Research, Stand.earth Research Group and Senior Forest Campaigner Tegan Hansen, Stand.earth</b></p>  
                  </div>
                  </div>
                  {/if}
                  
                </CarouselItem>
              {/each}
            </div>
          

          </Carousel>
  </div>
</section>







<Footer />


<style>
  .cover { 
          background-position:cover;
          width:100%;
          min-width:200px;
          background-position: center; /* Center the image */
          background-repeat: no-repeat; /* Do not repeat the image */
          background-size: cover;
      }

  .image {
    padding:100px;
    text-align:center;
  }

  .cover .overlay {
    width:100%;
    height:100%;
    background:linear-gradient(rgba(18, 138, 18, 0.1),rgba(255,255,255,1));
  }

  .carousel-wrapper {
    
    background-position: center; /* Center the image */
    background-repeat: no-repeat; /* Do not repeat the image */
    background-size: cover;
    min-height:700px;
  }

#evidence-header {
    background-position: top; /* Center the image */
    background-repeat: no-repeat; /* Do not repeat the image */
    background-size: cover;
    width:100%;
    min-height:400px;
    padding-top:50px;
    padding-bottom:50px;
    margin-bottom:20px;
}

#evidence-copy {
    width:80%;
    margin-left:auto;
    margin-right:auto;
    padding:40px;
    background:rgba(255,255,255,0.8)
    }

  .carousel-wrapper2 {
    
    background-position: top; /* Center the image */
    background-repeat: no-repeat; /* Do not repeat the image */
    background-size: cover;
    min-height:700px;
  }

  .carousel-inner {
    width:100%;
  }

  #quotecopy {
    width:50%;
    float:right;
    margin:50px;

    background:rgba(255,255,255,0.7);
    padding:50px 50px 30px 30px;
  }

  .cover-content {
      padding-top:30%;
  }

  .timeline {
    background:#F2F2F2;
  }

  .timeline-content {
    padding-top:50px;
  }

  .clearcut {
    width:90%;
    margin:auto;
  }

  .video {
    text-align:center;
  }

  .evidence {
    padding-bottom:100px;
  }

  #bdry-left {
    width:50%;
    float:left;
    margin-top:-10px;
  }
  #bdry-right {
    width:50%;
    float:right;
    margin-top:-10px;
  }

.report {
  width:100%;
  text-align:center;
  padding-top:50px;
}

.report h2 {
  max-width:550px;
  margin:auto;
}

.report img {
  max-width:450px;
  margin:auto;
}

.report a {
  text-decoration:none;
  max-width:550px;
  color:var(--stand-primary);
}

  @media (max-width:530px) {
    #bdry-left,#bdry-right {
      display:none;
    }

    #quotecopy {
    width:80%;
    float:right;
    margin:50px;
    }
  }


  .intro {
    padding-bottom:150px;
  }

  #highlight {
   font-weight:bold;
  }

  .map {
    background:#2B2B2B;
    color:var(--white);
  }

  .map h2 {
    padding-top:50px;
  }

  .deferral {
    background:#F2F2F2;
    border:2px solid var(--stand-primary);
    color:#212529;
    padding:50px;
  }


  .primary-nav {
    font-size:20px;
    padding-top:60px;
    text-align:right;
  }

  @media (max-width:766px) {
    .primary-nav {
      padding-top:30px;
    }

    .cover .overlay {
    width:100%;
    height:100%;
  }
  }

  .primary-nav a {
    display:block;
    width:100%;
    color:var(--stand-primary);
    text-transform:uppercase;
    text-decoration:underline;
    font-family:'Gotham';
    padding-bottom:10px;
  }

  .primary-nav a:hover {
    text-decoration:none;
  }

  .social-share {
    margin-top:20px;
    text-align:right;
    }

  .social-share a {
    display:inline;
  }

  .social-share button {
    padding:2px 10px 5px 10px;
    border-radius:50%;
  }


  button.facebook {
      background:#4267B2;
      font-size:30px;
  }
    button.twitter {
        background:#1DA1F2;
        font-size:30px;
    }

    button:hover {
        background:var(--stand-secondary);
    }


    #form-wrap .inner_wrapper {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    }

    @media (min-width: 992px) {
      #form-wrap {
          min-height: 1300px !important;
          clear:both;
      }
    }

    #form-wrap {
      width:100%;
      clear: both;
      position: relative;
      min-height: 1300px;
      overflow: hidden;
      display: block;
    }

</style>