<script>
  import { link } from "svelte-routing";
  import iconArrowWhite from "../assets/icons/icon-arrow-white.svg";

  const projects = [
    {
      title: "Project Del Sol",
      image: { mobile: "/src/assets/portfolio/mobile/image-del-sol.jpg" },
    },
    {
      title: "228B Tower",
      image: { mobile: "/src/assets/portfolio/mobile/image-228b.jpg" },
    },
    {
      title: "Le Prototype",
      image: { mobile: "/src/assets/portfolio/mobile/image-prototype.jpg" },
    },
  ];
</script>

<section class="home-featured">
  <h2>Featured</h2>
  <div class="home-featured__container">
    <div class="home-featured__projects">
      {#each projects as project, index (project)}
        <div
          class="home-featured__project"
          style="background-image: url({window.innerWidth >= 768
            ? project.image.tablet
            : project.image.mobile})"
        >
          <h3>{project.title}</h3>
          <a href="/portfolio" use:link>View All Projects</a>
        </div>
      {/each}
    </div>
    <a class="home-featured__button" href="/portfolio" use:link
      >See All <img src={iconArrowWhite} alt="arrow icon" /></a
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

    h2 {
      color: var(--very-dark-blue);
      font-size: 48px;
      font-style: normal;
      font-weight: 700;
      line-height: 52px;
      letter-spacing: -1.714px;
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

      &:hover {
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
      width: 100%;
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
    }
  }
</style>
