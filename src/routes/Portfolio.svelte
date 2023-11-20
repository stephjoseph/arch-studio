<script>
  import PortfolioProjects from "../lib/PortfolioProjects.svelte";
  import PageName from "../lib/PageName.svelte";
</script>

<main>
  <h1>Arch Studio | Portfolio</h1>
  <PortfolioProjects />
  <PageName name="Portfolio" />
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

  @media screen and (min-width: 1280px) {
    main {
      padding: 0 165px;
    }
  }
</style>
