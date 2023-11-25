<script>
    import { base } from '$app/paths';
    import '../app.css'
</script>
<svelte:head>


    <link rel="icon" href="{base}/logo.png" type="image/x-icon">

    <!-- Google tag (gtag.js) -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-BSNVENJNC4"></script>
    <script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());

    gtag('config', 'G-BSNVENJNC4');
    </script>
</svelte:head>

<main class='md:flex md:flex-col md:h-screen'>
    <slot />
</main>
