<script>
  export let skill;
</script>

<style>
  div {
    font-size: 1.5rem;
    padding: 0.5rem;
    display: flex;
    justify-content: space-between;
    width: 80%;
    text-align: center;
  }
  img {
    width: 2rem;
    height: 2rem;
  }
</style>

<div>
  {#if skill.icon.substr(0, 7) !== 'devicon'}
    <img src={skill.icon} alt="" />
  {:else}
    <i class={skill.icon} />
  {/if}
  <span>{skill.name}</span>
</div>
