<script lang="ts">
    import "../global.css";
    import "../scroll.css";
    import { assets } from "$app/paths";
</script>

<svelte:head>
    <title>Portal</title>
    <link rel="manifest" href={`${assets}/manifest.json`} />
</svelte:head>

<slot />

<style lang="scss">
    
</style>