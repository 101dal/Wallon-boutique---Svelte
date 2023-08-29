<script lang="ts">
    export let content: string = "";
    export let author: string = "";
    export let stars: number = 0;
    export let maxStars: number = 0;

    import Stars from "./Stars.svelte";
</script>

<div class="testimonial">
    <p class="text3">
        "{content}"
    </p>
    <Stars {stars} {maxStars} />
    <p class="text2 testimonial-author">- {author}</p>
</div>

<style lang="scss">
    .testimonial {
        background-color: #f9f9f9;
        padding: 20px;
        margin: 0 10px;
        border-radius: 10px;
        max-width: 300px;
        transition: transform 0.3s;

        &:hover {
            transform: scale(1.1);
        }

        p {
            font-style: italic;
            color: #555;
        }

        .text2 {
            font-family: "DancingScript", "Caveat";
            font-weight: bold;
            font-size: 1.4rem;
        }

        .text3 {
            font-family: "Caveat", "Caveat";
            font-weight: bold;
            font-size: 1.6rem;
        }

        .testimonial-author {
            margin-top: 10px;
            font-weight: bold;
        }
    }
</style>
