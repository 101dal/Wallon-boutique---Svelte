<script lang="ts">
    import Section from "../Section.svelte";
</script>

<!-- Hero Section -->
<Section id="home" first={true}>
    <img src="images/wallon_image.jpg" alt="Wallon hero" />
    <h1>Welcome to The Wallon Atw Store</h1>
</Section>

<style lang="scss">
    /* Hero section styles */
    :global(#home) {
        position: relative;
        background-color: var(--section-bg-color);
        text-align: center;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        overflow: hidden;

        h1 {
            z-index: 1;
            font-family: "Lobster";
            font-size: 5vw;
        }

        img {
            position: absolute;
            top: 0;
            opacity: 0.5;
            object-fit: fill;
            z-index: 1;
            filter: brightness(110%);
            filter: contrast(110%);
        }
    }
</style>
