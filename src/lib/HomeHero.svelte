<script>
  import { register } from "swiper/element/bundle";
  import { link } from "svelte-routing";
  import iconArrowWhite from "../assets/icons/icon-arrow-white.svg";

  register();

  let activeIndex = 0;
  let projects = [
    {
      title: "Project Paramour",
      description:
        "Project made for an art museum near Southwest London. Project Paramour is a statement of bold, modern architecture.",
      image: {
        mobile: "/src/assets/home/mobile/image-hero-paramour.jpg",
      },
    },
    {
      title: "Seraph Station",
      description:
        "The Seraph Station project challenged us to design a unique station that would transport people through time. The result is a fresh and futuristic model inspired by space stations.",
      image: {
        mobile: "/src/assets/home/mobile/image-hero-seraph.jpg",
      },
    },
    {
      title: "Federal II Tower",
      description:
        "A sequel theme project for a tower originally built in the 1800s. We achieved this with a striking look of brutal minimalism with modern touches.",
      image: {
        mobile: "/src/assets/home/mobile/image-hero-federal.jpg",
      },
    },
    {
      title: "Trinity Bank Tower",
      description:
        "Trinity Bank challenged us to make a concept for a 84 story building located in the middle of a city with a high earthquake frequency. For this project we used curves to blend design and stability to meet our objectives.",
      image: {
        mobile: "/src/assets/home/mobile/image-hero-trinity.jpg",
      },
    },
  ];

  const onSlideChange = (e) => {
    console.log("slide changed");
    activeIndex = e.detail[0].activeIndex;
  };
</script>

<div class="home-hero">
  <swiper-container
    class="swiper-container"
    slides-per-view={1}
    autoplay={{ delay: 5000, disableOnInteraction: false }}
    on:swiperslidechange={onSlideChange}
  >
    {#each projects as project, index (project)}
      <swiper-slide
        ><div
          class="swiper-slide"
          style="background-image: url({window.innerWidth >= 768
            ? project.image.tablet
            : project.image.mobile})"
        >
          <div class="swiper-slide__content">
            <h2>{project.title}</h2>
            <p>{project.description}</p>
          </div>
          <a class="swiper-slide__button" href="/portfolio" use:link
            >See Our Portfolio <img src={iconArrowWhite} alt="arrow icon" /></a
          >
        </div></swiper-slide
      >
    {/each}
  </swiper-container>
</div>

<style lang="scss">
  .home-hero {
    width: 100vw;
    height: 560px;

    .swiper {
      &-slide {
        width: 100%;
        height: 560px;
        padding: 116px 32px 110px 32px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        background: rgba(0, 0, 0, 0.35);
        background-repeat: no-repeat;
        background-size: 100%;
        background-position: bottom;
        background-blend-mode: multiply;
        transition-property: background-size;
        transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
        transition-duration: 1000ms;

        &:hover {
          background-size: 120%;
        }

        &__content {
          display: flex;
          flex-direction: column;
          width: 100%;
          gap: 12px;

          h2 {
            color: #fff;
            font-size: 48px;
            font-style: normal;
            font-weight: 700;
            line-height: 48px;
            letter-spacing: -1.2px;
          }

          p {
            color: #fff;
            font-size: 18px;
            font-style: normal;
            font-weight: 500;
            line-height: 24px;
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
    }
  }
</style>
