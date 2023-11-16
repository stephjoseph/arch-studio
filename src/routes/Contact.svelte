<script>
import ContactHero from "../lib/ContactHero.svelte";
</script>

<main>
    <h1>Contact</h1>
    <ContactHero/>
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

