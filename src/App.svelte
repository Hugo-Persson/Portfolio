<script>
  export let name;
  import Portfolio from "./Portfolio.svelte";
  import Skills from "./Skills.svelte";
  import * as animateScroll from "svelte-scrollto";
  import { quadOut } from "svelte/easing";
  let showPortfolio = true;

  animateScroll.setGlobalOptions({
    easing: quadOut
  });
  function scrollDown() {
    //alert(window.orientation);
    animateScroll.scrollTo({
      element: "nav",
      offset: -10,
      duration: 300
    });
  }
</script>

<style>
  header {
    background-image: url(./headerBackground.jpg);
    height: 85vh;
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
    font-size: 5rem;
  }

  @-webkit-keyframes pulse {
    0% {
      -webkit-box-shadow: 0 0 0 0 rgba(255, 255, 255, 0.4);
      background-color: rgba(255, 255, 255, 0.4);
    }
    70% {
      -webkit-box-shadow: 0 0 0 25px rgba(255, 255, 255, 0);
      background-color: rgba(255, 255, 255, 0);
    }
    100% {
      -webkit-box-shadow: 0 0 0 0 rgba(255, 255, 255, 0);
    }
  }
  @keyframes pulse {
    0% {
      -moz-box-shadow: 0 0 0 0 rgba(255, 255, 255, 0.4);
      box-shadow: 0 0 0 0 rgba(255, 255, 255, 0.4);
      background-color: rgba(255, 255, 255, 0.4);
    }
    70% {
      -moz-box-shadow: 0 0 0 10px rgba(255, 255, 255, 0);
      box-shadow: 0 0 0 25px rgba(255, 255, 255, 0);

      background-color: rgba(255, 255, 255, 0);
    }
    100% {
      -moz-box-shadow: 0 0 0 0 rgba(255, 255, 255, 0);
      box-shadow: 0 0 0 0 rgba(255, 255, 255, 0);
    }
  }

  header i {
    font-size: 5rem;
    cursor: pointer;
    border-radius: 50%;
  }
  main {
    height: 200vh;
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
    backdrop-filter: blur(10px);
    background-color: transparent;
    color: white;
    border: none;
    cursor: pointer;
    font-weight: bold;
    font-size: 1.5rem;
    border-radius: 0.3rem;

    border: solid white 1px;
  }
  nav button::selection {
    color: none;
    background: none;
    border: none;
  }
</style>

<header>
  <h1>Mitt Portfolio</h1>
  <div id="scrollDownContainer">
    <i on:click={scrollDown} class="icofont-scroll-double-down" />
  </div>
  <nav>
    <button on:click={() => (showPortfolio = true)}>Portfolio</button>
    <button on:click={() => (showPortfolio = false)}>Färdigheter</button>
  </nav>
</header>
<main id="main">

  {#if showPortfolio}
    <Portfolio />
  {:else}
    <Skills />
  {/if}
</main>
