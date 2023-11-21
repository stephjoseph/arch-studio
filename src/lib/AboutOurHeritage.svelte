<script>
  import imgHeritage from "../assets/about/desktop/image-heritage.jpg";
</script>

<section class="about-our-heritage">
  <div class="about-our-heritage__wrapper">
    <div class="about-our-heritage__eyebrow"></div>
    <div class="about-our-heritage__content">
      <h2>Our Heritage</h2>
      <div class="about-our-heritage__content-paragraphs">
        <p>
          Founded in 2007, we started as a trio of architects. Our complimentary
          skills and relentless attention to detail turned Arch into one of the
          most sought after boutique firms in the country.
        </p>
        <p>
          Speciliazing in Urban Design allowed us to focus on creating
          exceptional structures that live in harmony with their surroundings.
          We consider every detail from every surrounding element to inform our
          designs.
        </p>
        <p>
          Our small team of world-class professionals provides input on every
          project.
        </p>
      </div>
    </div>
  </div>
  <div class="about-our-heritage__img">
    <img src={imgHeritage} alt="heritage" />
  </div>
</section>

<style lang="scss">
  .about-our-heritage {
    width: 100%;
    padding: 0px 32px 112px 32px;
    display: flex;
    justify-content: space-between;

    &__wrapper {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 68px;
    }

    &__eyebrow {
      width: 64px;
      height: 1px;
      background: var(--light-grey);
    }

    &__content {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 24px;

      h2 {
        color: var(--very-dark-blue);
        font-size: 48px;
        font-style: normal;
        font-weight: 700;
        line-height: 52px;
        letter-spacing: -1.714px;
      }

      &-paragraphs {
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 24px;

        p {
          color: var(--dark-grey);
          font-size: 18px;
          font-style: normal;
          font-weight: 500;
          line-height: 24px;
        }
      }
    }

    &__img {
      display: none;
    }
  }

  @media screen and (min-width: 768px) {
    .about-our-heritage {
      padding: 0px 0px 232px;

      &__wrapper {
        gap: 48px;
      }

      &__content {
        gap: 64px;

        h2 {
          font-size: 72px;
          line-height: 64px;
          letter-spacing: -2px;
        }
      }
    }
  }
  @media screen and (min-width: 1280px) {
    .about-our-heritage {
      padding: 0px 0px 200px;

      &__wrapper {
        width: 40.18%;
        gap: 80px;
      }

      &__content {
        gap: 48px;
      }

      &__img {
        display: block;
        width: 48.65%;
        height: 569px;

        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
  }
</style>
