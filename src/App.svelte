<script>
  export let name;
  import Portfolio from "./Portfolio.svelte";
  import Skills from "./Skills.svelte";
  import * as animateScroll from "svelte-scrollto";
  let showPortfolio = true;

  function scrollDown() {
    console.log("HEY");
    animateScroll.scrollTo({ element: "#main", duration: 400 });
  }
</script>

<style>
  header {
    background-image: url(./headerBackground.jpg);
    height: 80vh;
    background-size: cover;
    color: white;
    position: relative;
  }
  header h1 {
    position: absolute;
    top: 5%;
    left: 35%;
    text-align: center;
  }
  header i {
    position: absolute;
    top: 55%;
    left: 45%;
    font-size: 5rem;
    cursor: pointer;
  }
  main {
    height: 200vh;
  }
</style>

<header>
  <h1>Välkommen till mitt Portfolio</h1>
  <i on:click={scrollDown} class="icofont-scroll-double-down" />
</header>
<main id="main">
  <button>Portfolio</button>
  <button>Färdigheter</button>
  {#if showPortfolio}
    <Portfolio />
  {:else}
    <Skills />
  {/if}
</main>
