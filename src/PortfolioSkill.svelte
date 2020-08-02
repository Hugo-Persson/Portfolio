<script>
  export let skill;
</script>

<style>
  li {
    font-size: 1.5rem;
    padding: 0.5rem;
  }
</style>

<li>
  <i class={skill.icon} />
  {skill.name}
</li>
