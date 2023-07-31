<script>
    import { Router, Link, Route } from "svelte-navigator";
    import Home from "./pages/Home.svelte";
    import Footer from "./layouts/Footer.svelte";
    import Header from "./layouts/Header.svelte";
    import People from "./pages/People.svelte";
    import Contact from "./pages/Contact.svelte";
    import About from "./pages/About.svelte";
    import Head from "./pages/Head.svelte";
    import Visitor from "./pages/Visitor.svelte";
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
        <Route path="/head" component={Head} />
        <Route path="/vistor'shelp" component={Visitor}></Route>
        <Footer />
    </Router>
</main>
