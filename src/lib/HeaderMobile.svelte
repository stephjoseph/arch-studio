<script>
  import { Link } from "svelte-routing";
</script>

<header class="header">
  <nav class="header__nav">
    <Link to="/">Home</Link>
    <Link to="/portfolio">Portfolio</Link>
    <Link to="/about">About</Link>
    <Link to="/contact">Contact</Link>
  </nav>
</header>

<style lang="scss">
  .header {
    display: flex;
    width: 100%;
    align-items: center;
    justify-content: space-between;
    padding: 32px;

    &__nav {
      position: absolute;
      display: none;

      &.active {
        display: block;
      }
    }
  }

  @media screen and (min-width: 1280px) {
    .header {
      display: none;
    }
  }
</style>
