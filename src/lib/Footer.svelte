<script>
  import { link } from "svelte-routing";
  import logoWhite from "../assets/logo-white.svg";
  import iconArrowWhite from "../assets/icons/icon-arrow-white.svg";
</script>

<footer class="footer">
  <a class="footer__logo" href="/" use:link
    ><img src={logoWhite} alt="logo white" /></a
  >
  <nav class="footer__nav">
    <ul>
      <li>
        <a href="/portfolio" use:link>Portfolio</a>
      </li>
      <li>
        <a href="/portfolio" use:link>About Us</a>
      </li>
      <li>
        <a href="/portfolio" use:link>Contact</a>
      </li>
    </ul>
  </nav>
  <a class="footer__button" href="/portfolio" use:link
    >See Our Portfolio <img src={iconArrowWhite} alt="arrow icon" /></a
  >
</footer>

<style lang="scss">
  .footer {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 32px;
    margin-top: -60px;
    padding-bottom: 48px;
    width: 100%;
    background: transparent;

    &__logo {
      width: 120px;
      height: 120px;
      background: var(--very-dark-blue);
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 48px 32px;
    }

    &__nav {
      ul {
        list-style-type: none;
        display: flex;
        flex-direction: column;
        gap: 32px;

        li {
          a {
            color: var(--medium-grey);
            font-size: 18px;
            font-style: normal;
            font-weight: 700;
            line-height: 25px;
          }
        }
      }
    }

    &__button {
      width: max-content;
      height: 72px;
      padding: 24px 32px 24px 37px;
      color: #fff;
      font-size: 18px;
      font-style: normal;
      font-weight: 700;
      line-height: 25px; /* 138.889% */
      background: var(--very-dark-blue);
      display: flex;
      align-items: center;
      gap: 24px;

      &:hover {
        background: var(--dark-grey);
      }

      &:active {
        background: var(--light-grey);
      }
    }
  }
</style>
