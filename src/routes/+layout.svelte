<script>
    import { base } from '$app/paths';
    import '../app.css'
</script>
<svelte:head>


    <link rel="icon" href="{base}/logo.png" type="image/x-icon">
</svelte:head>

<main class='md:flex md:flex-col md:h-screen'>
    <slot />
</main>
