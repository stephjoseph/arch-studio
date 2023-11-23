<script>
  import { onMount } from "svelte";
  import { link } from "svelte-routing";
  import iconArrowWhite from "../assets/icons/icon-arrow-white.svg";

  let windowWidth = window.innerWidth;
  const projects = [
    {
      title: "Project Del Sol",
      image: {
        mobile: "/src/assets/portfolio/mobile/image-del-sol.jpg",
        tablet: "/src/assets/portfolio/tablet/image-del-sol.jpg",
        desktop: "/src/assets/portfolio/desktop/image-del-sol.jpg",
      },
    },
    {
      title: "228B Tower",
      image: {
        mobile: "/src/assets/portfolio/mobile/image-228b.jpg",
        tablet: "/src/assets/portfolio/tablet/image-228b.jpg",
        desktop: "/src/assets/portfolio/desktop/image-228b.jpg",
      },
    },
    {
      title: "Le Prototype",
      image: {
        mobile: "/src/assets/portfolio/mobile/image-prototype.jpg",
        tablet: "/src/assets/portfolio/tablet/image-prototype.jpg",
        desktop: "/src/assets/portfolio/desktop/image-prototype.jpg",
      },
    },
  ];

  // Update window width when the window is resized
  onMount(() => {
    window.addEventListener("resize", () => {
      windowWidth = window.innerWidth;
    });

    return () => {
      window.removeEventListener("resize", () => {});
    };
  });
</script>

<section class="home-featured">
  <div class="home-featured__heading">
    <h2>Featured</h2>
    <a
      class="home-featured__button home-featured__button--desktop"
      href="/portfolio"
      use:link>See All <img src={iconArrowWhite} alt="arrow icon" /></a
    >
  </div>
  <div class="home-featured__container">
    <div class="home-featured__projects">
      {#each projects as project, index (project)}
        <div
          class="home-featured__project"
          style="background-image: url({windowWidth >= 1280
            ? project.image.desktop
            : windowWidth >= 768
            ? project.image.tablet
            : project.image.mobile})"
        >
          <h3>{project.title}</h3>
          <a href="/portfolio" use:link>View All Projects</a>
          <div class="home-featured__project-number">{index + 1}</div>
        </div>
      {/each}
    </div>
    <a
      class="home-featured__button home-featured__button--mobile"
      href="/portfolio"
      use:link>See All <img src={iconArrowWhite} alt="arrow icon" /></a
    >
  </div>
</section>

<style lang="scss">
  .home-featured {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 44px;
    padding: 72px 32px 132px;

    &__heading {
      display: flex;
      align-items: center;
      justify-content: space-between;

      h2 {
        color: var(--very-dark-blue);
        font-size: 48px;
        font-style: normal;
        font-weight: 700;
        line-height: 52px;
        letter-spacing: -1.714px;
      }
    }

    &__container {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 24px;
    }

    &__projects {
      width: 100%;
      display: grid;
      grid-template-columns: repeat(1, minmax(0, 1fr));
      gap: 24px;
    }

    &__project {
      width: 100%;
      height: 64vw;
      padding: 24px;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      background: rgba(0, 0, 0, 0.35);
      background-repeat: no-repeat;
      background-size: 100%;
      background-position: bottom;
      background-blend-mode: multiply;
      transition-property: background-size;
      transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
      transition-duration: 600ms;
      position: relative;

      &-number {
        display: none;
      }

      &:hover,
      &:active {
        background-size: 120%;
      }

      h3 {
        color: #fff;
        font-size: 32px;
        font-style: normal;
        font-weight: 700;
        line-height: 40px;
      }

      a {
        color: #fff;
        font-size: 18px;
        font-style: normal;
        font-weight: 500;
        line-height: 24px;
        opacity: 0.75;
      }
    }

    &__button {
      height: 72px;
      padding: 24px 32px 24px 37px;
      color: #fff;
      font-size: 18px;
      font-style: normal;
      font-weight: 700;
      line-height: 25px; /* 138.889% */
      background: var(--very-dark-blue);
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 24px;

      &:hover {
        background: var(--dark-grey);
      }

      &:active {
        background: var(--light-grey);
      }
      &--mobile {
        width: 100%;
      }

      &--desktop {
        display: none;
        width: 169px;
        padding: 24px 32px;
      }
    }
  }

  @media screen and (min-width: 768px) {
    .home-featured {
      gap: 88px;
      padding: 207px 0px 200px;

      &__project {
        height: 31.25vw;
        padding: 40px;

        &-number {
          display: block;
          position: absolute;
          top: 28px;
          right: 16px;
          color: #fff;
          font-size: 250px;
          font-style: normal;
          font-weight: 700;
          line-height: 200px;
          letter-spacing: -5px;
          opacity: 0.5;
        }
      }
      &__button {
        &--mobile {
          display: none;
        }

        &--desktop {
          display: flex;
        }
      }
    }
  }

  @media screen and (min-width: 1280px) {
    .home-featured {
      gap: 64px;

      &__heading {
        h2 {
          font-size: 72px;
          line-height: 64px;
          letter-spacing: -2px;
        }
      }

      &__projects {
        grid-template-columns: repeat(3, minmax(0, 1fr));
        gap: 30px;
      }

      &__project {
        height: 560px;
        background-size: 120%;

        &:hover,
        &:active {
          background-size: 140%;
        }

        &-number {
          top: 45px;
          right: -16px;
        }
      }
    }
  }
</style>
