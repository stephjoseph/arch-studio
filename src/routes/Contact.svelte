<script>
  import ContactHero from "../lib/ContactHero.svelte";
  import ContactDetails from "../lib/ContactDetails.svelte";
  import ContactMap from "../lib/ContactMap.svelte";
  import ContactForm from "../lib/ContactForm.svelte";
</script>

<main>
  <h1>Contact</h1>
  <ContactHero />
  <ContactDetails />
  <ContactMap />
  <ContactForm />
</main>

<style lang="scss">
  main {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    background: #fff;

    h1 {
      position: absolute;
      visibility: hidden;
      width: 0;
      height: 0;
    }
  }
</style>
