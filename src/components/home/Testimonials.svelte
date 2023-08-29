<script lang="ts">
    import Section from "../Section.svelte";
    import Testimonial from "./Testimonial.svelte";
</script>

<!-- Hero Section -->
<Section id="testimonials">
    <h2 class="fade-in">What Our Customers Say</h2>
    <div class="testimonial-slider fade-in">
        <Testimonial
            content="I absolutely love the selection of clothes on this website. The
        quality is outstanding and the prices are great. Highly
        recommended!"
            author="Sarah Johnson"
            stars={5}
            maxStars={5}
        />
        <Testimonial
            content="I've never seen a high shool offering such stylish clothing
            options. The convenience of online shopping makes it even
            better!"
            author="David Martinez"
            stars={5}
            maxStars={5}
        />
        <Testimonial
            content="The e-commerce platform is easy to use, and the checkout
            process is seamless. I've become a loyal customer since my first
            purchase!"
            author="Emily Williams"
            stars={5}
            maxStars={5}
        />
    </div>
</Section>

<style lang="scss">
    /* Hero section styles */
    :global(#testimonials) {
        background-color: var(--testimonial-bg-color);
        text-align: center;
        padding: 50px 0;

        h2 {
            font-family: "Caveat", "DancingScript";
            font-size: 4vw;
        }

        .testimonial-slider {
            display: flex;
            justify-content: center;
            align-items: center;
        }

        @media (max-width: 768px) {
            & {
                display: none;
            }
        }
    }
</style>
