<script>
  export let item;
  import PortfolioLink from "./PortfolioLink.svelte";
  import PortfolioSkill from "./PortfolioSkill.svelte";
</script>

<style>
  .portfolioItemContainer {
    background-color: #f4faff;
    border-radius: 1rem;

    color: black;
    margin: 10rem auto;
    width: 80%;
    padding: 2rem;
    text-align: left !important;
  }
  .name {
    text-align: center;
  }
  .links,
  .skills {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    height: 100%;
    width: 100%;

    align-items: center;
  }
  .wrap {
    display: inline-block;
  }
</style>

<div class="wrap">
  <div class="portfolioItemContainer">
    <div class="links ">
      {#each item.links as link}
        <PortfolioLink {link} />
      {/each}
    </div>

    <div class="name">
      <h2>{item.name}</h2>
    </div>
    <div class="description">
      {@html item.description}
    </div>
    <div class="skills">

      {#each item.skills as skill}
        <PortfolioSkill {skill} />
      {/each}

    </div>
  </div>
</div>
