<script>
  import ContactHero from "../lib/ContactHero.svelte";
  import ContactDetails from "../lib/ContactDetails.svelte";
  import ContactMap from "../lib/ContactMap.svelte";
  import ContactForm from "../lib/ContactForm.svelte";
  import PageName from "../lib/PageName.svelte";
</script>

<main>
  <h1>Contact</h1>
  <ContactHero />
  <ContactDetails />
  <ContactMap />
  <ContactForm />
  <PageName name="contact" />
</main>

<style lang="scss">
  main {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    background: #fff;
    max-width: 1920px;

    h1 {
      position: absolute;
      visibility: hidden;
      width: 0;
      height: 0;
    }
  }

  @media screen and (min-width: 768px) {
    main {
      padding: 0 96px;
    }
  }

  @media screen and (min-width: 1280px) {
    main {
      padding: 0 165px;
    }
  }
</style>
