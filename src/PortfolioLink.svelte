<script>
  export let link;
</script>

<style>
  li {
    padding: 10px;
    width: 100%;
    display: block;
    margin: 0;
    width: 10rem;
  }
  a {
    text-decoration: none;
    color: white;
    background-color: black;
    display: inline-block;
    width: 69%;
    text-align: center;
    padding: 1em;
    background-color: transparent;
    border: solid white 1px;
    border-radius: 0.3em;
  }
  a:hover {
    background-color: rgb(26, 32, 36);
  }
</style>

<li>
  <a href={link.url}>{link.name}</a>
</li>
