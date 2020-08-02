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
    height: 2rem;
    vertical-align: middle;
  }
  a:hover {
    background-color: gray;
  }
</style>

<li>
  <a href={link.url}>{link.name}</a>
</li>
