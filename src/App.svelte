<script>
    import { Router, Link, Route } from "svelte-navigator";
    import Home from "./pages/Home.svelte";
    import Footer from "./layouts/Footer.svelte";
    import Header from "./layouts/Header.svelte";
    import People from "./pages/People.svelte";
    import Contact from "./pages/Contact.svelte";
    import About from "./pages/About.svelte";
</script>

<main>
    <Router>
        <Header />
        <Route path="/">
            <Home />
        </Route>
        <Route path="/home" component={Home} />
        <Route path="/people" component={People} />
        <Route path="/contact" component={Contact} />
        <Route path="/about" component={About} />
        <Footer />
    </Router>
</main>
