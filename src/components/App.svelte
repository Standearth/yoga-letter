<script>
  import Meta from "./Meta.svelte"
  import Header from "./stand/Header.svelte"
  import Icon from "./helpers/Icon.svelte"
  import Footer from "./stand/Footer.svelte"
  import inView from "$actions/inView.js";
  import content from "$data/copy.json"
  
  import {fade,fly} from 'svelte/transition';
  import {Container,Row,Col,Collapse,Button,Card} from 'sveltestrap'
  import viewport from "$stores/viewport.js"
  import Boundary from "../components/helpers/Boundary.svelte"
  let isInView;
  let isOpen;

</script>

<Meta />

<section class="cover" style="height:{$viewport.height-8}px;background-image:url('assets/cover.jpeg')">
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
        <h1>Practice what you preach: Open Letter to Lululemon</h1>
        <h3>As yoga teachers and practitioners concerned with the health of the planet, climate and human communities, we ask lululemon to publicly commit to phase out coal and switch to 100% renewable energy for its supply chain by 2030.</h3>
      </Col>
      <Col sm=12 md=4 lg=4>
        <div class="primary-nav">
          <a href="#letter">READ THE OPEN LETTER</a>
          <a href="#signup">ADD YOUR NAME</a>
          <div class="social-share">
            <a target="_new" href="https://www.facebook.com/sharer.php?u=https%3A%2F%2Fpublications.stand.earth%2Fyoga-letter"><button class="facebook"><Icon name="facebook" stroke="var(--white)" stroke-width=2 width="30" /></button></a>
            <a target="_new" href="https://twitter.com/intent/tweet?url=https%3A%2F%2Fpublications.stand.earth%2Fyoga-letter%2F&via=standearth"><button class="twitter"><Icon name="twitter" stroke="var(--white)" stroke-width=2 width="30"/></button></a>
          </div>
      </div>
      </Col>
    </Row>
</Container>
</section>


<section class="letter">
  <div class="letter-content">
    <a name="letter"></a>
    <Container>
      <Row>
        <Col sm=12 md=8 lg=8>
          <p>To Glenn K. Murphy, Chairman of the Board, lululemon</p>

          <p>Dear Mr. Murphy,</p>

<p><b>As yoga teachers, we ask lululemon to commit to phase out coal and source 100 percent renewable energy across its supply chain.</b></p>

<p>lululemon is one of the largest, fastest growing and most profitable fitness apparel brands in the world.</p>

<p>lululemon’s marketing claims its clothes are ‘designed by yogis’ and offers connection to a global community of mindfulness practitioners, sporting leaders and health and wellness professionals.</p>

<p><b><u>Yet almost half of the energy powering lululemon factories comes from burning coal.</u></b></p>

<p><b>lululemon’s reliance on coal as a source of energy is extremely harmful to people and the environment, particularly in countries like Vietnam, Cambodia, China, Sri Lanka, and Bangladesh, where its products are made.</b> Fossil fuels like coal cause dangerous climate change and air pollution that is responsible for the deaths of millions of people around the world each year. Nearly one in five premature deaths globally are attributed to air pollution that’s caused by fossil fuels, according to a 2018 Harvard study.</p>

<p><b>lululemon’s current climate commitments fail to adequately address its pollution.</b> In fact, its total GHG emissions are increasing due to the company’s rapid growth. In order for the company to meet the Paris agreement targets, lululemon has to take immediate action to phase out coal and other fossil fuels from its supply chain.</p>

<p><b>lululemon: Please commit to immediately phase out coal and source 100 percent renewable energy such as solar and wind for your factories and across your supply chain.</b></p>

<p>Sincerely,</p>

<Button color="light" on:click={() => (isOpen = !isOpen)}>
  <h3>47 yoga teachers signed representing 3 continents</h3>
  View signatories
</Button>

<Collapse {isOpen}>
  <Card body>

    <ol>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Frank Jesse, Senior Iyengar Teacher, Griffins Hill Yoga Retreat, Australia&nbsp;</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Amanda Hood, Senior Iyengar Teacher, Hamilton Yoga, Australia&nbsp;</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Simon Joannou, Senior Iyengar Teacher, Marickville Yoga, Australia&nbsp;</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Julie Hodges PhD, Senior Iyengar Teacher, Lismore Yoga School, Australia&nbsp;</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Pixie Lillas, Director, Balmain Iyengar Yoga School, Australia&nbsp;</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Arjun von Caemmerer, Senior Teacher, Hobart School of Iyengar Yoga, Australia&nbsp;</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Simon Marrocco, Founder and Director, St Kilda Iyengar Yoga School, Australia&nbsp;</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Ashlea Wilken, Manager, YogaWest, Australia&nbsp;</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Akhila Hughes, The Yoga Workshop, Australia&nbsp;</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Bronwyn Rust, Senior Iyengar Teacher, Yogaville, Australia.</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Joanna Benn, Every Body Yoga, United Kingdom</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Nikki Calonge, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Aileen Epstein-Ignadiou, Las Vegas, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Galen Tromble, ClimateYogi.org, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Sharon Steffensen, Yoga Chicago Magazine, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Ingela Abbott, Founder-Yoga Northwest, Bellingham WA, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Nancy Gilgoff, The House of Yoga and Zen, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Annie Piper, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Dass Padmani, Golden Bridge Yoga, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Margi Young, Nest Yoga Center, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Michael Cecconi, Running Yoga, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Shiva Rea, Samudra, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">David Miliotis, Samjiva Nilayam, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Andrea Mullen, Tranquility, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Joan White, Iyengar Yoga School of Philadelphia, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Leslie Howard, Nest Yoga, Oakland CA, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Andrew Hillam, Jois Yoga, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Cyndi Lee, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Jane DoCampo, Sarasota Scoliosis &amp; Backcare, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Tias and Surya Little, PrajnaYoga, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Sarah Wilner, Nest, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Penny Dedel, Innerstellar, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Dafna Sarnoff, Shala, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Eddie Stern, Ashtanga Yoga New York, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">David E Morreno, Yoga Alliance, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Sarah Trelease, Sola School, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Caron James, Margo Young Yoga, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Linda Collery, Independent Yoga Teacher, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Erika Trice, Yoga Works, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Tias Little, Prajna Yoga, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Annie Carpenter, SmartFlow Yoga, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Rachel Nicks, MIRROR and lululemon Ambassador, United States&nbsp;</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Kim Stabbe, Blue Yoga &amp; Wellness, United States</p>
      </li>
      <li aria-level="1" dir="ltr">
      <p dir="ltr" role="presentation">Josh Schrei, Tapta Marg Productions, United States</p>
      </li>
    </ol>
  </Card>
</Collapse>
        </Col>
      </Row>
    </Container>
  </div>
</section>

<section class="quotes">
  <Container>
    <Row>
      <Col sm=12 md=6 lg=4 >
          <div class="headshot" id="quote1" style="background-image:url('assets/quote1.jpeg')">
          <p>Sierra Hollister, Living Yoga, US</p>
        </div>
        <div class="quote">
        <p>
          "Right action, recognizing all manifestations of life as equal – this is true devotion. To care for earth and each other is a fundamental part of living our yoga. I’m calling on lululemon to embody right action and quit coal and commit to renewable energy. All life is imperiled by climate change and lululemon is well-positioned as one of the largest yoga apparel manufacturers in the world to have an impact on climate and change industry standards. That’s a win / win by any standard."
        </p>
      </div>
      </Col>
      <Col sm=12 md=6 lg=4 >
        <div class="headshot" id="quote2" style="background-image:url('assets/quote2.jpg')">
          <p>Joanna Benn, Every Body Yoga, UK</p></div>
          <div class="quote"><p>"We need to halve global emissions in the next 8 years if we are to have a liveable Earth. We must, as yoga practitioners, lead through ahimsa, non-harming and make every effort along the supply chain and in all our actions to do the right, if sometimes, more challenging thing. Coal is not clean. It’s time to go 100% renewable."</p></div>
      </Col>
      <Col sm=12 md=6 lg=4 >
        <div class="headshot" id="quote3" style="background-image:url('assets/quote3.jpeg')"><p>Galen Thromble, Climate Yogi, US</p></div>
        <div class="quote"><p>"To end the climate crisis, everything matters, even how our clothes are made. I urge lululemon to bring its supply chain’s climate impacts in line with its environmental and social values by committing to quit coal and transition to 100% renewable by 2030."</p></div>
      </Col>
    </Row>
  </Container>

</section>

<section class="signup">
  <Container>
    <Row>
      <Col sm=12 md={{size:8,offset:2}}>
        <a name="signup"></a>
        <h2>Add your name</h2>
        <iframe src="https://act.stand.earth/page/43909/survey/1" width="100%" height="1050"></iframe>
      </Col>
    </Row>
  </Container>
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
    background:linear-gradient(rgba(18, 138, 18, 0.0),rgba(255,255,255,0.9));
  }


  .cover-content {
      padding-top:30%;
  }

  .letter-content {
    padding:50px;
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

  .headshot {
    min-height:500px;
    border-radius:30px;
    background-position: top; /* Center the image */
    background-repeat: no-repeat; /* Do not repeat the image */
    background-size: cover;
    position:relative;
  }

  .headshot p {
    color:#fff;
    background:rgba(0,0,0,0.3);
    text-align:center;
    position:absolute;
    padding-top:10px;
    padding-bottom:10px;
    bottom:18px;
    width:100%;
  }

  .quote {
    width:80%;
    border-radius:10px;
    margin:auto;
    background:rgb(236, 236, 236);
    padding:20px;
    margin-top:-15px;
    position:relative;
    top:-20px;
  }

  @media (max-width:530px) {
    #bdry-left,#bdry-right {
      display:none;
    }


  }


  .intro {
    padding-bottom:150px;
  }

  .signup {
    padding-top:40px;
    text-align:center;
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