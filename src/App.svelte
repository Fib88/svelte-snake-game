<script>
  import Snake from "./Snake.svelte";
  import Food from "./Food.svelte";

  function isCollide(a, b) {
    return !(
      a.top < b.top ||
      a.top > b.top ||
      a.left < b.left ||
      a.left > b.left
    );
  }

  function getDirectionFromKeyCode(keyCode) {
    if (keyCode === 38) {
      return "up";
    } else if (keyCode === 39) {
      return "right";
    } else if (keyCode === 37) {
      return "left";
    } else if (keyCode === 40) {
      return "down";
    }

    return false;
  }
</script>

<style>
  main {
    width: 1000px;
    height: 700px;
    border: solid black 1px;
    position: relative;
    margin: 20px auto;
    background-image: url("../background.jpg");
    background-size: cover;
  }
  h2,
  h1 {
    text-align: center;
  }
</style>

<h1>Snake Game</h1>
<main>
  <Snake />
  <Food />
</main>
<h2>Score</h2>
