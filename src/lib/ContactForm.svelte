<script>
  import iconArrowWhite from "../assets/icons/icon-arrow-white.svg";

  let formData = {
    name: "",
    email: "",
    message: "",
  };

  let errors = {};

  function handleSubmit() {
    errors = {}; // Reset errors

    // Validation checks
    if (!formData.name.trim()) {
      errors.name = "Can’t be empty";
    }

    if (!formData.email.trim()) {
      errors.email = "Can’t be empty";
    } else if (!isValidEmail(formData.email)) {
      errors.email = "Invalid email format";
    }

    if (!formData.message.trim()) {
      errors.message = "Can’t be empty";
    }

    // If there are no errors, log the form data
    if (Object.keys(errors).length === 0) {
      console.log(formData);
    }
  }

  function isValidEmail(email) {
    // Basic email validation regex
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return emailRegex.test(email);
  }
</script>

<section class="contact-form">
  <h2>Connect with us</h2>
  <form
    on:submit|preventDefault={handleSubmit}
    novalidate
    class="contact-form__form"
  >
    <div class="contact-form__input-group">
      <input
        bind:value={formData.name}
        type="text"
        name="name"
        id="name"
        placeholder="Name"
        class:invalid={errors.name}
        class:valid={!errors.name && formData.name.trim()}
      />
      {#if errors.name}<p class="contact-form__error">{errors.name}</p>{/if}
    </div>
    <div class="contact-form__input-group">
      <input
        bind:value={formData.email}
        type="email"
        name="email"
        id="email"
        placeholder="Email"
        class:invalid={errors.email}
        class:valid={!errors.email && formData.email.trim()}
      />
      {#if errors.email}<p class="contact-form__error">{errors.email}</p>{/if}
    </div>
    <div class="contact-form__input-group">
      <textarea
        bind:value={formData.message}
        name="message"
        id="message"
        cols="15"
        rows="5"
        placeholder="Message"
        class:invalid={errors.message}
        class:valid={!errors.message && formData.message.trim()}
      ></textarea>
      {#if errors.message}<p class="contact-form__error">
          {errors.message}
        </p>{/if}
    </div>
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
        padding: 0px 24px 24px;
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

        &.valid {
          border-width: 3px;
        }

        &.invalid {
          border-color: var(--red-error);

          &::placeholder {
            color: rgba(223, 86, 86, 0.5);
          }
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

        &.valid {
          border-width: 3px;
        }
        &.invalid {
          border-color: var(--red-error);

          &::placeholder {
            color: rgba(223, 86, 86, 0.5);
          }
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
        bottom: -76px;
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

    &__input-group {
      width: 100%;
      position: relative;
    }

    &__error {
      position: absolute;
      color: var(--red-error);
      font-size: 18px;
      font-weight: 700;
      letter-spacing: -0.281px;
      right: 16px;
      bottom: 16px;
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

  @media screen and (min-width: 1280px) {
    .contact-form {
      flex-direction: row;
      gap: 30px;
      padding: 125px 0px 240px;

      h2 {
        width: 31.53%;
      }

      &__form {
        width: 65.77%;
      }
    }
  }
</style>
