<script lang="ts">
    export let stars: number = 0;
    export let maxStars: number = 0;

    let count = 0;
</script>

<div class="star-rating">
    {#each Array(maxStars) as _, i}
        <span
            class="star"
            class:active={i < stars}
            class:hovered={i < count}
            tabindex="0"
            role="button"
            on:mouseover={() => (count = i + 1)}
            on:mouseout={() => (count = 0)}
            on:focus={() => (count = i + 1)}
            on:blur={() => (count = 0)}
            style="animation-delay: {i * 0.1}s"
        >
            &#9733;
        </span>
    {/each}
</div>

<style lang="scss">
    .star-rating {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 10px;

        .star {
            font-size: 1.8vw;
            color: var(--main-bg-color);
            transition: transform 0.3s, filter 0.3s;
            animation: none;

            &.active {
                color: var(--accent-color);
            }

            &.hovered {
                transform: scale(1.5);
                animation: glint 1s;
            }

            @keyframes glint {
                0%,
                100% {
                    filter: brightness(100%);
                }

                50% {
                    filter: brightness(150%);
                }
            }
        }
    }
</style>
