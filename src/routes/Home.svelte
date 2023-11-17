<script>
  import PageName from "../lib/PageName.svelte";
  import HomeHero from "../lib/HomeHero.svelte";
  import HomeWelcome from "../lib/HomeWelcome.svelte";
  import HomeSmallTeam from "../lib/HomeSmallTeam.svelte";
  import HomeFeatured from "../lib/HomeFeatured.svelte";
</script>

<main>
  <h1>Arch Studio</h1>
  <PageName name="Home" />
  <HomeHero />
  <HomeWelcome />
  <HomeSmallTeam />
  <HomeFeatured />
</main>

<style lang="scss">
  main {
    width: 100vw;
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
