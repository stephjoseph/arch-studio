<script>
  import { onMount } from "svelte";
  import { register } from "swiper/element/bundle";
  import { link } from "svelte-routing";
  import iconArrowWhite from "../assets/icons/icon-arrow-white.svg";

  register();

  let activeIndex = 0;
  let windowWidth = window.innerWidth;
  let projects = [
    {
      title: "Project Paramour",
      description:
        "Project made for an art museum near Southwest London. Project Paramour is a statement of bold, modern architecture.",
      image: {
        mobile: "/src/assets/home/mobile/image-hero-paramour.jpg",
        tablet: "/src/assets/home/tablet/image-hero-paramour.jpg",
        desktop: "/src/assets/home/desktop/image-hero-paramour.jpg",
      },
    },
    {
      title: "Seraph Station",
      description:
        "The Seraph Station project challenged us to design a unique station that would transport people through time. The result is a fresh and futuristic model inspired by space stations.",
      image: {
        mobile: "/src/assets/home/mobile/image-hero-seraph.jpg",
        tablet: "/src/assets/home/tablet/image-hero-seraph.jpg",
        desktop: "/src/assets/home/desktop/image-hero-seraph.jpg",
      },
    },
    {
      title: "Federal II Tower",
      description:
        "A sequel theme project for a tower originally built in the 1800s. We achieved this with a striking look of brutal minimalism with modern touches.",
      image: {
        mobile: "/src/assets/home/mobile/image-hero-federal.jpg",
        tablet: "/src/assets/home/tablet/image-hero-federal.jpg",
        desktop: "/src/assets/home/desktop/image-hero-federal.jpg",
      },
    },
    {
      title: "Trinity Bank Tower",
      description:
        "Trinity Bank challenged us to make a concept for a 84 story building located in the middle of a city with a high earthquake frequency. For this project we used curves to blend design and stability to meet our objectives.",
      image: {
        mobile: "/src/assets/home/mobile/image-hero-trinity.jpg",
        tablet: "/src/assets/home/tablet/image-hero-trinity.jpg",
        desktop: "/src/assets/home/desktop/image-hero-trinity.jpg",
      },
    },
  ];

  onMount(() => {
    // swiper setup
    const swiperEl = document.querySelector("swiper-container");

    const params = {
      injectStyles: [
        `
        .swiper-pagination {
          display: none;
        }

        @media screen and (min-width: 1280px) {
          .swiper-pagination {
            display: flex;
          }

          .swiper {
            position: static;
          }

          .swiper-pagination-bullet {
            width: 80px;
            height: 80px;
            color: #7D828F;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            font-style: normal;
            font-weight: 700;
            line-height: 25px;
            opacity: 1;
            background: rgba(255, 255, 255, 1);
            margin: 0;
            border: none;
            border-radius: 0;
            transition-property: color, background-color, border-color, text-decoration-color, fill, stroke;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 300ms;
          }

        .swiper-pagination-bullet-active {
            color: #fff;
            background: #1B1D23;
          }
        }

        .swiper-horizontal > 
          .swiper-pagination-bullets 
          .swiper-pagination-bullet, 
          .swiper-pagination-horizontal.swiper-pagination-bullets 
          .swiper-pagination-bullet {
            margin: 0;
            z-index: 9999;
        }

        .swiper-horizontal > 
        .swiper-pagination-bullets, 
        .swiper-pagination-bullets.swiper-pagination-horizontal, 
        .swiper-pagination-custom, 
        .swiper-pagination-fraction {
          width: auto;
          left: -80px;
          bottom:0;
        }
        `,
      ],
      slidesPerView: 1,
      autoplay: {
        delay: 5000,
        disableOnInteraction: false,
      },

      pagination: {
        clickable: true,
        renderBullet: function (index, className) {
          return (
            '<span class="' + className + '">' + "0" + (index + 1) + "</span>"
          );
        },
      },
    };

    Object.assign(swiperEl, params);
    swiperEl.initialize();

    // Update window width when the window is resized
    window.addEventListener("resize", () => {
      windowWidth = window.innerWidth;
    });

    return () => {
      window.removeEventListener("resize", () => {});
    };
  });
</script>

<section class="home-hero">
  <swiper-container class="mySwiper" init="false">
    {#each projects as project, index (project)}
      <swiper-slide
        ><div
          class="swiper-slide"
          style="background-image: url({windowWidth >= 1280
            ? project.image.desktop
            : windowWidth >= 768
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
</section>

<style lang="scss">
  .home-hero {
    width: 100%;
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

        &:hover,
        &:active {
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

  @media screen and (min-width: 768px) {
    .home-hero {
      height: 720px;
      padding: 0px;

      .swiper {
        &-slide {
          height: 720px;
          padding: 0 56px;
          justify-content: center;
          gap: 40px;

          &__content {
            h2 {
              font-size: 96px;
              line-height: 80px;
              letter-spacing: -2px;
            }
          }
        }
      }
    }
  }

  @media screen and (min-width: 1280px) {
    .home-hero {
      .swiper {
        &-slide {
          padding: 0 376px 0px 190px;
          gap: 16px;
        }
      }
    }
  }
</style>
