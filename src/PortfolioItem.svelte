<script>
  export let item;
  import PortfolioLink from "./PortfolioLink.svelte";
  import PortfolioSkill from "./PortfolioSkill.svelte";
</script>

<style>

</style>

<div class="portfolioItemContainer">
  <div class="links ">
    <ul class="noDot">
      {#each item.links as link}
        <PortfolioLink {link} />
      {/each}
    </ul>
  </div>

  <div class="name">
    <h2>{item.name}</h2>
  </div>
  <div class="description">{item.description}</div>
  <div class="skills">
    <ul class="noDot">
      {#each item.skills as skill}
        <PortfolioSkill {skill} />
      {/each}
    </ul>
  </div>
</div>
