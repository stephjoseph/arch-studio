<script>
import { Router, Link, Route } from "svelte-routing";
import Home from "./routes/Home.svelte";
import Portfolio from "./routes/Portfolio.svelte";
import About from "./routes/About.svelte";
import Contact from "./routes/Contact.svelte";

export let url = "";
</script>

<Router {url}>
  <nav>
    <Link to="/">Home</Link>
    <Link to="/portfolio">Portfolio</Link>
    <Link to="/about">About</Link>
    <Link to="/contact">Contact</Link>
  </nav>
  <div>
    <Route path="/"><Home /></Route>
    <Route path="/portfolio" component={Portfolio} />
    <Route path="/about" component={About} />
    <Route path="/contact" component={Contact} />
  </div>
</Router>

<style lang="scss">
</style>
