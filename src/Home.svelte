<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  function loginClick() {
    dispatch("login", {});
  }
</script>

<style>
  main {
    background-color: red;
    height: 100vh;
  }

  .container {
    margin: auto;
    width: 80%;
  }

  nav {
    display: flex;
    justify-content: space-between;
    padding: 1em 0;
  }
</style>

<main>
  <div class="container">
    <nav>
      <h1><a href="/">Resume Craft</a></h1>
      <button on:click={loginClick}>Login with Google</button>
    </nav>
  </div>
</main>
