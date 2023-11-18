<script>
  import { onMount } from "svelte";
  import imgHeroMobile from "../assets/about/mobile/image-hero.jpg";
  import imgHeroTablet from "../assets/about/tablet/image-hero.jpg";
  import imgHeroDesktop from "../assets/about/desktop/image-hero.jpg";

  let windowWidth = window.innerWidth;

  // Update window width when the window is resized
  onMount(() => {
    window.addEventListener("resize", () => {
      windowWidth = window.innerWidth;
    });

    return () => {
      window.removeEventListener("resize", () => {});
    };
  });

  // Define different image sources based on window width
  $: bgImgSrc =
    windowWidth >= 1280
      ? imgHeroDesktop
      : windowWidth >= 768
      ? imgHeroTablet
      : imgHeroMobile;
</script>

<section class="about-hero">
  <div class="about-hero__img" style="background-image: url({bgImgSrc})"></div>
  <div class="about-hero__content">
    <div class="about-hero__content-wrapper">
      <div class="about-hero__content-wrapper-eyebrow"></div>
      <h2>Your team of professionals</h2>
      <p>
        Our small team of world-class professionals will work with you every
        step of the way. Strong relationships are at the core of everything we
        do. This extends to the relationship our projects have with their
        surroundings.
      </p>
    </div>
  </div>
</section>

<style lang="scss">
  .about-hero {
    width: 100%;
    display: flex;
    flex-direction: column;

    &__img {
      width: 100%;
      height: 64vw;
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
    }

    &__content {
      width: 100%;
      padding-right: 32px;
      background: transparent;
      margin-top: -45px;

      &-wrapper {
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 20px;
        background: #fff;
        padding: 65px 0px 76px 32px;

        &-eyebrow {
          display: none;
        }

        h2 {
          color: var(--very-dark-blue);
          font-size: 48px;
          font-style: normal;
          font-weight: 700;
          line-height: 52px;
          letter-spacing: -1.2px;
        }

        p {
          color: #60636d;
          font-size: 18px;
          font-style: normal;
          font-weight: 500;
          line-height: 24px;
        }
      }
    }
  }

  @media screen and (min-width: 768px) {
    .about-hero {
      position: relative;
      margin-bottom: 200px;

      &__img {
        height: 720px;
      }

      &__content {
        position: absolute;
        bottom: 0;
        right: -56px;
        padding-right: 0px;

        &-wrapper {
          padding: 88px 56px 0px;
          gap: 40px;

          &-eyebrow {
            display: block;
            width: 64px;
            height: 1px;
            background: var(--light-grey);
            margin-bottom: 32px;
          }

          h2 {
            font-size: 72px;
            line-height: 64px;
            letter-spacing: -2px;
          }
        }
      }
    }
  }
</style>
