<script>
  import iconArrow from "../assets/icons/icon-arrow.svg";
  import { link } from "svelte-routing";

  const offices = [
    {
      name: "Main Office",
      email: "archone@mail.com",
      address: "1892  Chenoweth Drive TN",
      phone: "123-456-3451",
    },
    {
      name: "Office II",
      email: "archtwo@mail.com",
      address: "3399  Wines Lane TX",
      phone: "832-123-4321",
    },
  ];
</script>

<section class="contact-details">
  <div class="contact-details__eyebrow"></div>
  <div class="contact-details__content">
    <h2>Contact Details</h2>
    <div class="contact-details__offices">
      {#each offices as office, index (office)}
        <div class="contact-details__office">
          <div class="contact-details__office-wrapper">
            <h3>{office.name}</h3>
            <div class="contact-details__office-details">
              <div class="contact-details__office-detail">
                <span>Mail :</span>
                <span>{office.email}</span>
              </div>
              <div class="contact-details__office-detail">
                <span>Address :</span>
                <span>{office.address}</span>
              </div>
              <div class="contact-details__office-detail">
                <span>Phone :</span>
                <span>{office.phone}</span>
              </div>
            </div>
          </div>
          <a href="#map">View on Map <img src={iconArrow} alt="arrow icon" /></a
          >
        </div>
      {/each}
    </div>
  </div>
</section>

<style lang="scss">
  .contact-details {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 68px;
    padding: 0px 32px 72px;

    &__eyebrow {
      width: 64px;
      height: 1px;
      background: var(--light-grey);
    }

    &__content {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 40px;

      h2 {
        color: var(--very-dark-blue);
        font-size: 48px;
        font-style: normal;
        font-weight: 700;
        line-height: 52px;
        letter-spacing: -1.714px;
      }
    }

    &__offices {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 40px;
    }

    &__office {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 44px;

      a {
        display: flex;
        align-items: center;
        gap: 24px;
        color: var(--very-dark-blue);
        font-size: 18px;
        font-style: normal;
        font-weight: 700;
        line-height: 25px;
      }

      &-wrapper {
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 14px;

        h3 {
          color: var(--dark-grey);
          font-size: 18px;
          font-style: normal;
          font-weight: 700;
          line-height: 35px;
        }
      }

      &-details {
        display: flex;
        flex-direction: column;
      }

      &-detail {
        span {
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
    .contact-details {
      gap: 48px;
      padding: 0px 0px 224px;

      &__content {
        h2 {
          font-size: 72px;
          line-height: 64px;
          letter-spacing: -2px;
        }
      }

      &__office {
        flex-direction: row;
        justify-content: space-between;
        align-items: flex-end;
        gap: 72px;

        a {
          margin-bottom: 12px;
        }

        &-wrapper {
          max-width: 350px;
        }
      }
    }
  }
</style>
