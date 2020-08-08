<script>
  export let link;
</script>

<style>
  a {
    padding: 10px;
    width: 100%;

    margin: 0;
    width: 60%;
    color: black;
    border: solid black 1px;
  }
</style>

<a class="button" href={link.url}>{link.name}</a>
