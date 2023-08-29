<script lang="ts">
    import Section from "../Section.svelte";
</script>

<!-- Best Selling Products Section -->
<Section id="shop">
    <h2 class="fade-in">Best Selling Products</h2>
    <div class="product-container fade-in">
        <div class="product">
            <img src="images/OIP (1).jpeg" alt="Product 1" />
            <div class="text1 product-name">Product Name 1</div>
        </div>
        <div class="product">
            <img src="images/OIP.jpeg" alt="Product 2" />
            <div class="text1 product-name">Product Name 2</div>
        </div>
    </div>
</Section>

<style lang="scss">
    /* Best Selling Products section styles */
    :global(#shop) {
        h2 {
            font-family: "Caveat", "DancingScript";
            font-size: 4vw;
        }

        .text1 {
            font-family: "DancingScript", "Caveat";
            font-size: 1.2rem;
        }

        background-color: var(--alt-section-bg-color);
        text-align: center;
        padding: 50px 0;

        .product-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
        }

        .product {
            position: relative;
            background-color: #f9f9f9;
            border: 1px solid #ddd;
            border-radius: 10px;
            margin: 10px;
            min-width: 40vw;
            max-width: 40vw;
            min-height: 50vh;
            overflow: hidden;
            cursor: pointer;

            img {
                max-width: 100%;
                height: auto;
            }

            &:hover {
                .product-name {
                    opacity: 1;
                    /* Fade-in on hover */
                }
            }
            .product-name {
                position: absolute;
                bottom: 0;
                left: 0;
                width: 100%;
                background-color: rgba(0, 0, 0, 0.7);
                color: white;
                padding: 10px;
                font-weight: bold;
                text-align: center;
                opacity: 0;
                /* Hidden by default */
                transition: opacity 0.3s;
            }
        }

        @media (max-width: 768px) {
            .product {
                max-width: 300px;
                height: 300px;
                /* Fixed height */
                width: 300px;
                margin: 10px auto;
            }

            .product-name {
                opacity: 1;
            }
        }
    }
</style>
