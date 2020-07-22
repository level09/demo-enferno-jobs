<template>
    <div id="app">
        <Nav></Nav>
        <Hero></Hero>
        <Jobs></Jobs>
        <Footer></Footer>
    </div>
</template>

<script>
    import Nav from './components/Nav'
    import Jobs from './components/Jobs';
    import Hero from './components/Hero';
    import Footer from './components/Footer'
    export default {
        name: 'app',
        data: () => ({}),
        components: {
            Nav,
            Hero,
            Jobs,
            Footer
        }
    }
</script>
