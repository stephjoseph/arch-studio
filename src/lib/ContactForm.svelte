<script>
  import iconArrowWhite from "../assets/icons/icon-arrow-white.svg";
</script>

<section class="contact-form">
  <h2>Connect with us</h2>
  <form class="contact-form__form">
    <input type="text" name="name" id="name" placeholder="Name" />
    <input type="email" name="email" id="email" placeholder="Email" />
    <textarea
      name="message"
      id="message"
      cols="15"
      rows="5"
      placeholder="Message"
    ></textarea>
    <button type="submit"><img src={iconArrowWhite} alt="arrow icon" /></button>
  </form>
</section>

<style lang="scss">
  .contact-form {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 40px;
    padding: 72px 32px 212px;

    h2 {
      color: var(--very-dark-blue);
      font-size: 48px;
      font-style: normal;
      font-weight: 700;
      line-height: 52px;
      letter-spacing: -1.714px;
    }

    &__form {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 44px;
      position: relative;

      input {
        width: 100%;
        background: transparent;
        border: none;
        border-bottom: 1px solid var(--very-dark-blue);
        color: var(--very-dark-blue);
        padding: 0px 24px 32px;
        font-size: 24px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: -0.312px;

        &:focus {
          outline: none;
        }

        &::placeholder {
          color: var(--light-grey);
        }
      }

      textarea {
        width: 100%;
        background: transparent;
        border: none;
        border-bottom: 1px solid var(--very-dark-blue);
        color: var(--very-dark-blue);
        padding: 0px 24px 32px;
        font-size: 24px;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: -0.312px;
        resize: none;

        &:focus {
          outline: none;
        }

        &::placeholder {
          color: var(--light-grey);
        }
      }

      button {
        width: 80px;
        height: 80px;
        display: flex;
        align-items: center;
        justify-content: center;
        border: none;
        position: absolute;
        bottom: -80px;
        right: 0;
        cursor: pointer;

        &:hover {
          background: var(--dark-grey);
        }

        &:active {
          background: var(--light-grey);
        }
      }
    }
  }

  @media screen and (min-width: 768px) {
    .contact-form {
      padding: 200px 0px 280px;
      gap: 64px;

      h2 {
        font-size: 72px;
        line-height: 64px;
        letter-spacing: -2px;
      }
    }
  }
</style>
