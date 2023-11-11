<script>
  import HomeHero from "../lib/HomeHero.svelte";
  import HomeWelcome from "../lib/HomeWelcome.svelte";
</script>

<main>
  <h1>Arch Studio</h1>
  <HomeHero />
  <HomeWelcome />
</main>

<style lang="scss">
  main {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;

    h1 {
      position: absolute;
      visibility: hidden;
      width: 0;
      height: 0;
    }
  }
</style>
