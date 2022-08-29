<script>
  import wordmark from "$svg/stand/logo_white.svg";
</script>

<header>
  <div class="wordmark">
    <span class="s">
      <a href="https://stand.earth" target="_new">{@html wordmark}</a>
    </span>
  </div>
</header>

<style>
  header { 
    min-width:310px;
    height:60px;
    background: rgb(0,0,0);
    background: linear-gradient(0deg, rgba(0,0,0,0) 0%, rgba(0,0,0,0.4) 100%);
  }

  .wordmark {
    max-width: 100%;
    text-align:center;
  }

  .wordmark a {
    border: none;
    color: var(--fg);
  }

  .wordmark .d, .wordmark .s {
    width:200px;
    height:60px;
  }

  .d img {
    width:200px;
    display:inline;
    margin-left:20px;
    margin-top:5px;
  }



  .wordmark a:hover {
    background-color: transparent;
  }
</style>
