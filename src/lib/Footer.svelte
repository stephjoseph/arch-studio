<script>
  import { link } from "svelte-routing";
  import logoWhite from "../assets/logo-white.svg";
  import iconArrowWhite from "../assets/icons/icon-arrow-white.svg";
</script>

<footer class="footer">
  <div class="footer__wrapper">
    <a class="footer__logo" href="/" use:link
      ><img src={logoWhite} alt="logo white" /></a
    >
    <nav class="footer__nav">
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
    <a class="footer__button" href="/portfolio" use:link
      >See Our Portfolio <img src={iconArrowWhite} alt="arrow icon" /></a
    >
  </div>
</footer>

<style lang="scss">
  .footer {
    width: 100%;
    max-width: 1920px;
    &__wrapper {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 32px;
      margin-top: -60px;
      padding-bottom: 48px;
      width: 100%;
      background: transparent;
      position: relative;
    }

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

            &:hover {
              color: var(--very-dark-blue);
            }
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

  @media screen and (min-width: 768px) {
    .footer {
      background-color: #fff;

      &__wrapper {
        width: 79.69%;
        margin-top: 0px;
        padding: 0;
        background-color: var(--very-light-grey);
        flex-direction: row;
        width: calc(100% - 156px);
        gap: 40px;
      }

      &__nav {
        ul {
          flex-direction: row;
          gap: 56px;
        }
      }

      &__button {
        position: absolute;
        right: -156px;
      }
    }
  }

  @media screen and (min-width: 1280px) {
    .footer {
      padding: 0 165px;

      &__wrapper {
        width: 88.65%;
        gap: 85px;
      }

      &__logo {
        width: 200px;
        height: 200px;
      }

      &__button {
        right: -126px;
      }
    }
  }
</style>
