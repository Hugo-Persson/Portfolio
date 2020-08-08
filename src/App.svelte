<script>
  export let name;
  import Portfolio from "./Portfolio.svelte";
  import Skills from "./Skills.svelte";
  import * as animateScroll from "svelte-scrollto";
  import { quadOut } from "svelte/easing";
  import ContactForm from "./ContactForm.svelte";

  let showPortfolio = true;

  animateScroll.setGlobalOptions({
    easing: quadOut
  });
  function scrollDown() {
    //alert(window.orientation);
    console.log("Scroll");
    animateScroll.scrollTo({
      element: "main",

      duration: 300
    });
  }
</script>

<style>
  header {
    background-image: url(./original.jpg);
    height: 100vh;
    background-size: cover;
    color: white;
    position: relative;
    background-position: center;
  }

  @font-face {
    font-family: headerFont;
    src: url("Ailerons-Regular.otf");
  }
  header h1 {
    position: absolute;
    width: 100%;
    top: 1%;
    text-align: center;
    font-family: headerFont;
    font-size: 5em;
  }

  .scrollDown {
    font-size: 5rem;
    cursor: pointer;
    border-radius: 50%;
    margin: 1rem;
    font-style: italic;
  }

  #scrollDownContainer {
    position: absolute;
    top: 70%;
    width: 100%;
    text-align: center;
  }
  nav {
    position: absolute;
    bottom: 0%;
    display: flex;
    justify-content: space-evenly;
    width: 100%;
  }
  nav button {
    padding: 0.5rem;
    width: 10rem;

    font-weight: bold;
    font-size: 1.5rem;
  }
  nav button::selection {
    color: none;
    background: none;
    border: none;
  }
  main {
    background-color: #1098f7 !important;
    text-align: center;
  }
</style>

<header>
  <h1>Hugo's Portfolio</h1>
  <div on:click={scrollDown} id="scrollDownContainer">
    <span>Scroll down</span>
    <br />
    <i class="fad fa-chevron-double-down scrollDown" />
  </div>
  <!-- <nav>
    <button class="button" on:click={() => (showPortfolio = true)}>
      Portfolio
    </button>
    <button class="button" on:click={() => (showPortfolio = false)}>
      Färdigheter
    </button>
  </nav> -->
</header>
<main id="main">

  {#if showPortfolio}
    <Portfolio />
  {:else}
    <Skills />
  {/if}

</main>
<ContactForm />
