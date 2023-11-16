<script>
  import { onMount } from "svelte";
  import { Link } from "svelte-routing";
  import logo from "../assets/logo.svg";
  import iconHamburger from "../assets/icons/icon-hamburger.svg";
  import { fly, fade } from "svelte/transition";

  let isNavOpen = false;

  const toggleNav = () => {
    isNavOpen = !isNavOpen;
    document.body.classList.toggle("noscroll");
  };

  onMount(() => {
    function handleClick(event) {
      const nav = document.querySelector(".header__nav");
      const button = document.querySelector(".header__hamburger");

      if (isNavOpen) {
        if (!nav.contains(event.target) && !button.contains(event.target)) {
          isNavOpen = false;
          document.body.classList.remove("noscroll");
        }
      }
    }

    document.addEventListener("click", handleClick);

    return () => {
      document.removeEventListener("click", handleClick);
    };
  });
</script>

<header class="header">
  <div class="header__logo">
    <Link to="/" on:click={() => (isNavOpen = false)}>
      <img src={logo} alt="logo" />
    </Link>
  </div>

  <button class="header__hamburger" on:click={toggleNav}>
    <img src={iconHamburger} alt="hamburger icon" />
  </button>

  {#if isNavOpen}
    <nav transition:fly={{ duration: 400, x: "100%" }} class="header__nav">
      <ul>
        <li>
          <Link to="/portfolio" on:click={toggleNav}>Portfolio</Link>
        </li>
        <li>
          <Link to="/about" on:click={toggleNav}>About</Link>
        </li>
        <li>
          <Link to="/contact" on:click={toggleNav}>Contact</Link>
        </li>
      </ul>
    </nav>
    <div transition:fade class="header__overlay"></div>
  {/if}
</header>

<style lang="scss">
  .header {
    display: flex;
    width: 100%;
    align-items: center;
    justify-content: space-between;
    padding: 32px;
    position: relative;
    &__logo {
      width: 77px;
      height: 32px;

      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }

      a {
        width: 100%;
        height: 100%;
      }
    }

    &__hamburger {
      background: none;
      border: none;
      width: 24px;
      height: 24px;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;

      img {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }

    &__nav {
      position: absolute;
      right: 0;
      top: 96px;
      transition:
        opacity 0.3s ease,
        transform 0.3s ease;

      padding: 40px 48px;
      background: var(--very-light-grey);
      width: 343px;
      z-index: 9999;

      ul {
        list-style-type: none;
        display: flex;
        flex-direction: column;
        gap: 16px;

        li {
          color: var(--very-dark-blue);
          font-size: 32px;
          font-style: normal;
          font-weight: 700;
          line-height: 40px;
        }
      }
    }

    &__overlay {
      display: block;
      position: fixed;
      top: 96px;
      right: 0;
      bottom: 0;
      left: 0;
      background-color: rgba(0, 0, 0, 0.5);
      opacity: 1;
      transition: opacity 0.3s ease-in-out;
      pointer-events: none;
      z-index: 10;
    }
  }

  @media screen and (min-width: 1280px) {
    .header {
      display: none;
    }
  }
</style>
