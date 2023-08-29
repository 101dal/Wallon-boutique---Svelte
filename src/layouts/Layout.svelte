<script lang="ts">
    export const ssr = true;
    import Navbar from "../components/utils/Navbar.svelte";
    import Footer from "../components/utils/Footer.svelte";

    export let pageTitle: String;
</script>

<head>
    <title>Wallon boutique - {pageTitle}</title>
</head>

<Navbar />

<main class="pageContent">
    <slot />

    <Footer />
</main>

<style>
    main.pageContent {
        width: 100%;
        position: absolute;
    }
</style>
