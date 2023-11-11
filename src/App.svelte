<script>
  import { Router, Route } from "svelte-routing";

  import Home from "./routes/Home.svelte";
  import Portfolio from "./routes/Portfolio.svelte";
  import About from "./routes/About.svelte";
  import Contact from "./routes/Contact.svelte";
  import HeaderMobile from "./lib/HeaderMobile.svelte";

  export let url = "";
</script>

<Router {url}>
  <HeaderMobile />

  <Route path="/"><Home /></Route>
  <Route path="/portfolio" component={Portfolio} />
  <Route path="/about" component={About} />
  <Route path="/contact" component={Contact} />
</Router>

<style lang="scss">
</style>
