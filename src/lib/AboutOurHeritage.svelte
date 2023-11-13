<script>
</script>

<section class="about-our-heritage">
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
        Speciliazing in Urban Design allowed us to focus on creating exceptional
        structures that live in harmony with their surroundings. We consider
        every detail from every surrounding element to inform our designs.
      </p>
      <p>
        Our small team of world-class professionals provides input on every
        project.
      </p>
    </div>
  </div>
</section>

<style lang="scss">
  .about-our-heritage {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 68px;
    padding: 0px 32px 112px 32px;

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
