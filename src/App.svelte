<script>
import { Router, Link, Route } from 'svelte-navigator';
import Home from "./pages/Home.svelte";
import Footer from "./layouts/Footer.svelte";
import Header from "./layouts/Header.svelte";
    import Count from './pages/Count.svelte';



</script>

<main>
    <Router>
        <Header/>
        <Route path="/">
        </Route>
        <Route path="/home" component={Home}>
        </Route>
        <Footer/>
    </Router>
</main>

