<script>
  import { fade, slide } from "svelte/transition";
  import Spinner from "./Spinner.svelte";
  let form;

  async function sendForm(e) {
    e.preventDefault();
    console.log(new URLSearchParams(new FormData(form)).toString());
    try {
      const init = {
        method: "GET"
      };
      loading = true;
      await fetch(
        "https://script.google.com/macros/s/AKfycbwCH_cUwycqejVUST-FoMibz3LrGqukONR56csPTkKlS7tk4r8Y/exec?" +
          new URLSearchParams(new FormData(form)).toString()
      );
      loading = false;
      window = 1;
    } catch (err) {
      loading = false;
      console.log(err);
      window = 2;
    }
  }
  let window = 0;
  let loading = false;
</script>

<style>
  .sheet {
    width: 80%;
    height: 80%;

    border-radius: 1rem;
    background-color: #f4faff;
    display: block;
    color: black;
    padding: 1rem;
  }
  label {
  }
  input,
  textarea {
    border-radius: 0.8rem;
    border: solid 1px black;
    padding: 1rem 0.5rem;
    width: 96.5%;
    margin: 0.5rem auto;
    font-size: 1.5em;
    transition: width 0.5s;
  }

  form > div {
    width: 95%;
    margin: auto;
    text-align: center;
  }

  textarea {
    width: 96.5%;
    height: 100%;
  }

  input:focus,
  textarea:focus {
    outline: none;
    width: 100%;
  }
  #messageWrap {
    height: 20%;
    margin-bottom: 5rem;
  }
  #formWrapper,
  #successWindow,
  #failWindow {
    background-color: #df2935;
    width: 100%;

    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  h2 {
    text-align: center;
  }
  button {
    background-color: transparent;
    border: 1px black solid;
    padding: 1rem 3rem;
    border-radius: 0.8rem;
    cursor: pointer;
  }
  button:hover {
    background-color: #0f1316;
    color: white;
  }
  #successWindow {
    background-color: #28a745;
  }
  .formResponse {
    text-align: center;
  }
  .innerContainer {
    text-align: left;
    width: 96.5%;
    margin: auto;
  }
  #spinnerWrapper {
    width: 96.5;
    margin: auto;

    text-align: left;
  }
</style>

{#if window === 0}
  <div transition:fade id="formWrapper">

    <form action="" class="sheet" bind:this={form} on:submit={sendForm}>
      <h2>Kontakta mig</h2>
      <div>
        <div class="innerContainer">
          <label for="name">Namn:</label>

        </div>
        <input type="text" name="name" id="name" placeholder="Namn" />
      </div>
      <div>
        <div class="innerContainer">
          <label for="email">Email:</label>
        </div>

        <input type="email" name="email" id="email" placeholder="Email" />
      </div>
      <div id="messageWrap">
        <div class="innerContainer">
          <label for="message">Meddelande</label>
        </div>

        <textarea name="message" id="message" />
      </div>

      <div>
        <button type="submit">Skicka</button>
      </div>
      {#if loading}
        <div id="spinnerWrapper" transistion:slide>
          <Spinner />
        </div>
      {/if}

    </form>

  </div>
{:else if window == 1}
  <div transition:fade id="successWindow" class="formResponse">
    <div class="sheet">
      <h2>Tack för ditt meddelande</h2>
      <button on:click={() => (window = 0)}>Skicka ett nytt meddelande</button>
    </div>

  </div>
{:else}
  <div transition:fade id="failWindow" class="formResponse">
    <div class="sheet">
      <h2>Något gick fel</h2>
      <button>Skapa nytt meddelande</button>
    </div>

  </div>
{/if}
