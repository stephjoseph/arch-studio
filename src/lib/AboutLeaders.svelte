<script>
  import iconLinkedIn from "../assets/icons/icon-linkedin.svg";
  import iconTwitter from "../assets/icons/icon-twitter.svg";
  const leaders = [
    {
      name: "Jake Richards",
      jobTitle: "Chief Architect",
      img: "/assets/about/desktop/avatar-jake.jpg",
    },
    {
      name: "Thompson Smith",
      jobTitle: "Head of Finance",
      img: "/assets/about/desktop/avatar-thompson.jpg",
    },
    {
      name: "Jackson Rourke",
      jobTitle: "Lead Designer",
      img: "/assets/about/desktop/avatar-jackson.jpg",
    },
    {
      name: "Maria Simpson",
      jobTitle: "Senior Architect",
      img: "/assets/about/desktop/avatar-maria.jpg",
    },
  ];
</script>

<section class="about-leaders">
  <h2>The Leaders</h2>
  <div class="about-leaders__cards">
    {#each leaders as leader, index (leader)}
      <div class="about-leaders__card">
        <div class="about-leaders__card-img">
          <img src={leader.img} alt={leader.name} />
          <div class="about-leaders__card-socials">
            <a href="/"><img src={iconLinkedIn} alt="linkedin icon" /></a>
            <a href="/"><img src={iconTwitter} alt="twitter icon" /></a>
          </div>
        </div>
        <div class="about-leaders__card-details">
          <h3>{leader.name}</h3>
          <span>{leader.jobTitle}</span>
        </div>
      </div>
    {/each}
  </div>
</section>

<style lang="scss">
  .about-leaders {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 56px;
    padding: 0px 32px 172px;

    h2 {
      color: var(--very-dark-blue);
      font-size: 48px;
      font-style: normal;
      font-weight: 700;
      line-height: 52px; /* 108.333% */
      letter-spacing: -1.714px;
    }

    &__cards {
      width: 100%;
      display: grid;
      grid-template-columns: repeat(1, minmax(0, 1fr));
      gap: 80px;
    }

    &__card {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 16px;

      &-img {
        width: 100%;
        height: 75vw;
        position: relative;

        &:hover,
        &:active {
          .about-leaders__card-socials {
            opacity: 1;
          }
        }

        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
          object-position: top;
        }
      }

      &-socials {
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        justify-content: center;
        align-items: center;
        gap: 32px;
        display: flex;
        background: rgba(0, 0, 0, 0.5);
        opacity: 0;
        transition: opacity 0.3s ease;

        a {
          width: 40px;
          display: inline-block;

          img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
        }
      }

      &-details {
        width: 100%;
        display: flex;
        flex-direction: column;

        h3 {
          color: var(--very-dark-blue);
          font-size: 32px;
          font-style: normal;
          font-weight: 700;
          line-height: 40px;
        }

        span {
          color: var(--very-dark-blue);
          font-size: 18px;
          font-style: normal;
          font-weight: 500;
          line-height: 24px;
        }
      }
    }
  }

  @media screen and (min-width: 768px) {
    .about-leaders {
      padding: 0px 0px 240px;

      h2 {
        font-size: 72px;
        line-height: 64px;
        letter-spacing: -2px;
      }

      &__cards {
        grid-template-columns: repeat(2, minmax(0, 1fr));
        gap: 104px 12px;
      }

      &__card {
        &-img {
          height: 33.33vw;
        }
      }
    }
  }

  @media screen and (min-width: 1280px) {
    .about-leaders {
      flex-direction: row;
      justify-content: space-between;
      padding: 0px 0px 160px;

      h2 {
        width: 29.1%;
      }

      &__cards {
        width: 65.77%;
        gap: 64px 32px;
      }

      &__card {
        &-img {
          height: 22.22vw;
          max-height: 456px;
        }
      }
    }
  }
</style>
