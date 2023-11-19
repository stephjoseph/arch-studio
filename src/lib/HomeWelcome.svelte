<script>
  import imgWelcome from "../assets/home/desktop/image-welcome.jpg";
</script>

<section class="home-welcome">
  <div class="home-welcome__eyebrow"></div>

  <div class="home-welcome__content">
    <div class="home-welcome__content-wrapper">
      <span class="home-welcome__content-text">Welcome</span>

      <h2>Welcome to Arch Studio</h2>
      <div class="home-welcome__content-paragraphs">
        <p>
          We have a unique network and skillset to help bring your projects to
          life. Our small team of highly skilled individuals combined with our
          large network put us in a strong position to deliver exceptional
          results.
        </p>
        <p>
          Over the past 10 years, we have worked on all kinds of projects. From
          stations to high-rise buildings, we create spaces that inspire and
          delight.
        </p>
        <p>
          We work closely with our clients so that we understand the intricacies
          of each project. This allows us to work in harmony the surrounding
          area to create truly stunning projects that will stand the test of
          time.
        </p>
      </div>
    </div>
    <div class="home-welcome__content-img">
      <img src={imgWelcome} alt="welcome" />
    </div>
  </div>
</section>

<style lang="scss">
  .home-welcome {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 68px;
    padding: 72px 32px 112px 32px;
    position: relative;

    &__eyebrow {
      width: 64px;
      height: 1px;
      background: var(--light-grey);
    }

    &__content {
      &-text {
        display: none;
      }
      &-wrapper {
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 24px;
        position: relative;

        h2 {
          color: var(--very-dark-blue);
          font-size: 48px;
          font-style: normal;
          font-weight: 700;
          line-height: 52px;
          letter-spacing: -1.714px;
        }
      }

      &-img {
        display: none;
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
  }

  @media screen and (min-width: 768px) {
    .home-welcome {
      padding: 248px 0px 232px;

      &__eyebrow {
        display: none;
      }

      &__content {
        gap: 44px;

        &-text {
          display: block;
          position: absolute;
          top: -160px;
          left: 0px;
          color: var(--very-light-grey);
          font-size: 156px;
          font-style: normal;
          font-weight: 700;
          line-height: 200px;
          letter-spacing: -3px;
        }

        &-wrapper {
          h2 {
            width: 77.43%;
            font-size: 72px;
            line-height: 64px;
            letter-spacing: -2px;
          }
        }
      }
    }
  }

  @media screen and (min-width: 1280px) {
    .home-welcome {
      padding: 269px 0px 200px 190px;

      &__content {
        display: flex;
        align-items: flex-end;
        justify-content: space-between;
        gap: 125px;

        &-text {
          font-size: 250px;
          line-height: 200px;
          letter-spacing: -5px;
          left: -190px;
          top: -180px;
        }

        &-wrapper {
          margin-bottom: 12px;
          width: 48.48%;

          h2 {
            width: 100%;
          }
        }

        &-img {
          display: block;
          width: 38.04%;

          img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
        }
      }
    }
  }
</style>
