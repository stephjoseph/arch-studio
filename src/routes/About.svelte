<script>
  import AboutHero from "../lib/AboutHero.svelte";
</script>

<main>
  <h1>Arch Studio | About</h1>
  <AboutHero />
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
