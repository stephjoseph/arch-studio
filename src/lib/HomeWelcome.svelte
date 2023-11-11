<script>
</script>

<section class="home-welcome">
  <div class="home-welcome__eyebrow"></div>
  <div class="home-welcome__content">
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
        of each project. This allows us to work in harmony the surrounding area
        to create truly stunning projects that will stand the test of time.
      </p>
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
  }
</style>
