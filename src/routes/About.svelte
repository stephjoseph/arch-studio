<script>
  import AboutHero from "../lib/AboutHero.svelte";
  import AboutOurHeritage from "../lib/AboutOurHeritage.svelte";
  import AboutLeaders from "../lib/AboutLeaders.svelte";
  import PageName from "../lib/PageName.svelte";
</script>

<main>
  <h1>Arch Studio | About</h1>
  <AboutHero />
  <AboutOurHeritage />
  <AboutLeaders />
  <PageName name="About Us" />
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

  @media screen and (min-width: 768px) {
    main {
      padding: 0 96px;
    }
  }
</style>
