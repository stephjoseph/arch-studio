<script>
  // your script goes here
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
  </form>
</section>

<style lang="scss">
  .contact-form {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 40px;
    padding: 72px 32px 132px;

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
    }
  }
</style>
