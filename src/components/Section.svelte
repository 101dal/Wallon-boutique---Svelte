<script lang="ts">
    export let first: boolean = false;
    export let id: string;
    let navbar_spacing = "";
    if (first == true) {
        navbar_spacing = "navbar-spacing";
    }
</script>

<section {id} class:first-element={first}>
    <slot />
</section>

<style lang="scss">
    :global(section) {
        width: -webkit-fill-available;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        position: relative;
        z-index: 2;

        &.first-element {
            padding-top: 120px;
            min-height: calc(100vh - 120px);
        }
    }
</style>
