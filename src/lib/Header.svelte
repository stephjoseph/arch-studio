<script>
  import { link } from "svelte-routing";
  import logo from "../assets/logo.svg";
</script>

<header class="header">
  <a href="/" class="header__logo" use:link>
    <img src={logo} alt="logo" />
  </a>
  <nav class="header__nav">
    <ul>
      <li>
        <a href="/portfolio" use:link>Portfolio</a>
      </li>
      <li>
        <a href="/about" use:link>About Us</a>
      </li>
      <li>
        <a href="/contact" use:link>Contact</a>
      </li>
    </ul>
  </nav>
</header>

<style lang="scss">
  .header {
    display: none;
    width: 100%;
    padding: 56px 96px;
    align-items: center;
    gap: 80px;
    background: #fff;
    max-width: 1920px;

    &__logo {
      width: 96px;
      height: 40px;

      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }

    &__nav {
      ul {
        list-style-type: none;
        display: flex;
        align-items: center;
        gap: 56px;

        li {
          a {
            color: var(--medium-grey);
            font-size: 18px;
            font-style: normal;
            font-weight: 700;
            line-height: 25px;
          }

          a:hover,
          a:active {
            color: var(--very-dark-blue);
          }
        }
      }
    }
  }

  @media screen and (min-width: 768px) {
    .header {
      display: flex;
    }
  }

  @media screen and (min-width: 1280px) {
    .header {
      padding: 56px 165px;
    }
  }
</style>
