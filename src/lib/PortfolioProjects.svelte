<script>
  import { onMount } from "svelte";

  let windowWidth = window.innerWidth;
  const projects = [
    {
      title: "Seraph Station",
      date: "September 2019",
      image: {
        mobile: "/assets/portfolio/mobile/image-seraph.jpg",
        tablet: "/assets/portfolio/tablet/image-seraph.jpg",
        desktop: "/assets/portfolio/desktop/image-seraph.jpg",
      },
    },
    {
      title: "Eebox Building",
      date: "August 2017",
      image: {
        mobile: "/assets/portfolio/mobile/image-eebox.jpg",
        tablet: "/assets/portfolio/tablet/image-eebox.jpg",
        desktop: "/assets/portfolio/desktop/image-eebox.jpg",
      },
    },
    {
      title: "Federal II Tower",
      date: "March 2017",
      image: {
        mobile: "/assets/portfolio/mobile/image-federal.jpg",
        tablet: "/assets/portfolio/tablet/image-federal.jpg",
        desktop: "/assets/portfolio/desktop/image-federal.jpg",
      },
    },
    {
      title: "Project Del Sol",
      date: "January 2016",
      image: {
        mobile: "/assets/portfolio/mobile/image-del-sol.jpg",
        tablet: "/assets/portfolio/tablet/image-del-sol.jpg",
        desktop: "/assets/portfolio/desktop/image-del-sol.jpg",
      },
    },
    {
      title: "Le Prototype",
      date: "October 2015",
      image: {
        mobile: "/assets/portfolio/mobile/image-prototype.jpg",
        tablet: "/assets/portfolio/tablet/image-prototype.jpg",
        desktop: "/assets/portfolio/desktop/image-prototype.jpg",
      },
    },
    {
      title: "228B Tower",
      date: "April 2015",
      image: {
        mobile: "/assets/portfolio/mobile/image-228b.jpg",
        tablet: "/assets/portfolio/tablet/image-228b.jpg",
        desktop: "/assets/portfolio/desktop/image-228b.jpg",
      },
    },
    {
      title: "Grand Edelweiss Hotel",
      date: "December 2013",
      image: {
        mobile: "/assets/portfolio/mobile/image-edelweiss.jpg",
        tablet: "/assets/portfolio/tablet/image-edelweiss.jpg",
        desktop: "/assets/portfolio/desktop/image-edelweiss.jpg",
      },
    },
    {
      title: "Netcry Tower",
      date: "August 2012",
      image: {
        mobile: "/assets/portfolio/mobile/image-netcry.jpg",
        tablet: "/assets/portfolio/tablet/image-netcry.jpg",
        desktop: "/assets/portfolio/desktop/image-netcry.jpg",
      },
    },
    {
      title: "Hypers",
      date: "January 2012",
      image: {
        mobile: "/assets/portfolio/mobile/image-hypers.jpg",
        tablet: "/assets/portfolio/tablet/image-hypers.jpg",
        desktop: "/assets/portfolio/desktop/image-hypers.jpg",
      },
    },
    {
      title: "SXIV Tower",
      date: "March 2011",
      image: {
        mobile: "/assets/portfolio/mobile/image-sxiv.jpg",
        tablet: "/assets/portfolio/tablet/image-sxiv.jpg",
        desktop: "/assets/portfolio/desktop/image-sxiv.jpg",
      },
    },
    {
      title: "Trinity Bank Tower",
      date: "September 2010",
      image: {
        mobile: "/assets/portfolio/mobile/image-trinity.jpg",
        tablet: "/assets/portfolio/tablet/image-trinity.jpg",
        desktop: "/assets/portfolio/desktop/image-trinity.jpg",
      },
    },
    {
      title: "Project Paramour",
      date: "February 2008",
      image: {
        mobile: "/assets/portfolio/mobile/image-paramour.jpg",
        tablet: "/assets/portfolio/tablet/image-paramour.jpg",
        desktop: "/assets/portfolio/desktop/image-paramour.jpg",
      },
    },
  ];

  // update window width when the window is resized
  onMount(() => {
    window.addEventListener("resize", () => {
      windowWidth = window.innerWidth;
    });

    return () => {
      window.removeEventListener("resize", () => {});
    };
  });
</script>

<section class="portfolio-projects">
  <div class="portfolio-projects__container">
    <div class="portfolio-projects__projects">
      {#each projects as project, index (project)}
        <div
          class="portfolio-projects__project"
          style="background-image: url({windowWidth >= 1280
            ? project.image.desktop
            : windowWidth >= 768
            ? project.image.tablet
            : project.image.mobile})"
        >
          <h2>{project.title}</h2>
          <span>{project.date}</span>
        </div>
      {/each}
    </div>
  </div>
</section>

<style lang="scss">
  .portfolio-projects {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 44px;
    padding: 56px 32px 132px;

    h2 {
      color: #fff;
      font-size: 32px;
      font-style: normal;
      font-weight: 700;
      line-height: 40px;
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

      span {
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

  @media screen and (min-width: 768px) {
    .portfolio-projects {
      padding: 0px 0px 200px;

      &__project {
        height: 31.25vw;
        padding: 40px;
      }
    }
  }

  @media screen and (min-width: 1280px) {
    .portfolio-projects {
      padding: 0px 0px 160px;

      &__projects {
        grid-template-columns: repeat(3, minmax(0, 1fr));
        gap: 32px;
      }

      &__project {
        height: 560px;
        background-size: 120%;

        &:hover {
          background-size: 140%;
        }
      }
    }
  }
</style>
