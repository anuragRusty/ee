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
    import News from "./pages/News.svelte";
    import Events from "./pages/Events.svelte";
    import Login from "./pages/Login.svelte";
    import Notice from "./pages/Notice.svelte";
    import Resource from "./pages/Resource.svelte";
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
        <Route path="/news" component={News} />
        <Route path="/vistor'shelp" component={Visitor}></Route>
        <Route path="/events" component={Events}></Route>
        <Route path="/login" component={Login}></Route>
        <Route path="/notice" component={Notice}></Route>
        <Route path="/resource" component={Resource}></Route>
        <Footer />
    </Router>
</main>
