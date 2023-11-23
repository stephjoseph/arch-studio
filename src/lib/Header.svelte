<script>
  import { link } from "svelte-routing";
  import { writable, get } from "svelte/store";
  import logo from "../assets/logo.svg";

  let currentRoute = writable("");

  const navItems = [
    { text: "Portfolio", route: "/portfolio" },
    { text: "About Us", route: "/about" },
    { text: "Contact", route: "/contact" },
  ];

  $: currentRoute.set(window.location.pathname);

  const setRoute = (route) => {
    currentRoute.set(route);
  };
</script>

<header class="header">
  <a href="/" class="header__logo" on:click={() => setRoute("/")} use:link>
    <img src={logo} alt="logo" />
  </a>
  <nav class="header__nav">
    <ul>
      {#each navItems as { text, route }}
        <li>
          <a
            href={route}
            class:active={$currentRoute === route}
            on:click={() => setRoute(route)}
            use:link
          >
            {text}
          </a>
        </li>
      {/each}
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
            position: relative;
          }

          a.active {
            color: var(--very-dark-blue);

            &::after {
              content: "";
              width: 24px;
              height: 1px;
              position: absolute;
              bottom: -6px;
              right: 16px;
              background: var(--very-dark-blue);
            }
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
