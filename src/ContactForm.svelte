<script>
  let form;

  async function sendForm(e) {
    e.preventDefault();
    console.log(new URLSearchParams(new FormData(form)).toString());
    try {
      const init = {
        method: "GET"
      };
      await fetch(
        "https://script.google.com/macros/s/AKfycbwCH_cUwycqejVUST-FoMibz3LrGqukONR56csPTkKlS7tk4r8Y/exec?" +
          new URLSearchParams(new FormData(form)).toString()
      );
      window = 1;
    } catch (err) {
      console.log(err);
      window = 2;
    }
  }
  let window = 0;
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
    width: 100%;
    margin: 0.5rem 0 1rem 0;
    font-size: 1.5em;
  }

  form div {
    width: 95%;
    margin: auto;
  }

  textarea {
    width: 100%;
    height: 100%;
  }

  input:focus,
  textarea:focus {
    outline: none;
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
</style>

{#if window === 0}
  <div id="formWrapper">

    <form action="" class="sheet" bind:this={form} on:submit={sendForm}>
      <h2>Kontakta mig</h2>
      <div>
        <label for="name">Namn:</label>
        <input type="text" name="name" id="name" placeholder="Namn" />
      </div>
      <div>
        <label for="email">Email:</label>
        <input type="email" name="email" id="email" placeholder="Email" />
      </div>
      <div id="messageWrap">
        <label for="message">Meddelande</label>
        <textarea name="message" id="message" />
      </div>
      <div>
        <button type="submit">Skicka</button>
      </div>

    </form>

  </div>
{:else if window == 1}
  <div id="successWindow" class="formResponse">
    <div class="sheet">
      <h2>Tack för ditt meddelande</h2>
      <button on:click={() => (window = 0)}>Skicka ett nytt meddelande</button>
    </div>

  </div>
{:else}
  <div id="failWindow" class="formResponse">
    <div class="sheet">
      <h2>Något gick fel</h2>
      <button>Skapa nytt meddelande</button>
    </div>

  </div>
{/if}
