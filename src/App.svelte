<script>
  export let name;
  import Portfolio from "./Portfolio.svelte";
  import Experience from "./Experience.svelte";
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
  header span {
    position: absolute;
    width: 60%;
    margin: auto;
    left: 20%;
    top: 20%;
    text-align: center;
  }
  .scrollDown {
    font-size: 5rem;
    cursor: pointer;
    border-radius: 50%;
    margin: 2rem;
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
  <h1>Portfolio</h1>
  <span>
    Hej, mitt namn är Hugo Persson och jag har haft programmering som en hobby i
    flera år, jag har tidigare jobbat mot kund och skapat flera hobby projekt.
    Nedan visar jag några av mina senaste projekt.
  </span>
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

  <Portfolio />

</main>
<Experience />
<ContactForm />
