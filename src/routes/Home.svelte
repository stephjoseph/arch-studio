<script>
  import HomeHero from "../lib/HomeHero.svelte";
  import HomeWelcome from "../lib/HomeWelcome.svelte";
  import HomeSmallTeam from "../lib/HomeSmallTeam.svelte";
  import HomeFeatured from "../lib/HomeFeatured.svelte";
</script>

<main>
  <h1>Arch Studio</h1>
  <HomeHero />
  <HomeWelcome />
  <HomeSmallTeam />
  <HomeFeatured />
</main>

<style lang="scss">
  main {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    background: #fff;

    h1 {
      position: absolute;
      visibility: hidden;
      width: 0;
      height: 0;
    }
  }
</style>
