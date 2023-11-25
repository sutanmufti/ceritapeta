<script lang="ts">
    import { base } from "$app/paths";
    import Fa from 'svelte-fa'
    import { faFlag, faMap, faLink, faCodeCompare } from '@fortawesome/free-solid-svg-icons'
    import { faGithub, faInstagram, faLinkedin } from '@fortawesome/free-brands-svg-icons';

    import { onMount } from "svelte";

    let bannernames = ['banner.jpg','banner.gif','iso.gif' , 'bannerm.jpeg']
    let imgdiv: HTMLImageElement
    let n = 0
    $: bannername = bannernames[n]
    onMount(()=>{
        setInterval(()=>{
            if (imgdiv !== null){
                imgdiv.classList.add('opacity-0')
                setTimeout(()=>{
                    if (n+1<bannernames.length){
                        n+=1
                    } else {
                        n =0
                    }
                    imgdiv.classList.remove('opacity-0')
                }, 1000)
            }
        }, 4000)
    })
</script>

<svelte:head>
    <title>Ceritapeta.co.uk</title>
    <meta name="description" content="Cerita Peta is a platform to create and explore stories with maps & graphs. 
    A sprinkle of visualisation techniques can transform reports into stories that everyone enjoy.">
    <meta name="keywords" content="cerita peta, story maps, story map, webgis, spatial data science, geospatial, gis">

    <meta property="og:title" content="Ceritapeta.co.uk">
    <meta property="og:description" content="Cerita Peta is a platform to create and explore stories with maps & graphs.">
    <meta property="og:url" content="https://ceritapeta.co.uk">
    <meta property="og:image" content="https://https://ceritapeta.co.uk/meta.png">

    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Ceritapeta.co.uk">
    <meta name="twitter:description" content="Cerita Peta is a platform to create and explore stories with maps & graphs.">
    <meta name="twitter:image" content="https://https://ceritapeta.co.uk/meta.png">


</svelte:head>

<header class='py-2 px-5  z-50 flex items-center'>
    <div class='mr-5 flex items-center mx-5 '>
        <img src="{base}/logo.png" alt="" class='h-16 mr-2'>
        <div class='text-slate-600 border-r pr-2 max-md:hidden'>
            Rekayasa Data Spasial
        </div>
        <div class='mx-4'>
            <a href="{base}">
                Home
            </a>
        </div>
        <div class='mx-4'>
            <a href="https://rekayasadata.co.uk">
                Blog
            </a>
        </div>
    </div>
</header>

<!-- banner -->
<!-- mobile -->
<div class='z-0 h-[50vh] block md:hidden relative'>
    <img src="{base}/{bannername}" class='h-full w-full object-cover absolute top-0 left-0 z-[-1]' alt="">
    <div class='z-0 w-full h-full flex justify-center items-center'>
        <div class='m-2 text-center bg-white/60 p-2 rounded-md backdrop-blur-sm'>
            <h1 class='text-2xl font-semibold'>
                Cerita Peta by RDS
            </h1>
            <p class='mt-5 text-gray-500/80'>
                <b>Cerita Peta</b> means story map. 
                Cerita Peta is a platform to create and explore stories with maps & graphs. 
                A sprinkle of visualisation techniques can transform reports into stories that everyone enjoy.
            </p>
            <p class='my-5 text-blue-600/80 hover:underline'>
                <a href="https://jakarta.sutan.co.uk" target="_blank">
                    <Fa class='inline mr-1' icon={faLink}/> Check this story out! 
                </a>
            </p>
        </div>
    </div>
</div>

<!-- banner web -->
<div class='z-0 hidden md:flex py-5 '>
    <div class='w-1/2  flex flex-col justify-center p-10 px-20'>
        <h1 class='text-4xl font-semibold'>
            Cerita Peta by RDS
        </h1>
        <p class='mt-5 text-gray-500/80'>
            <b>Cerita Peta</b> means story map. 
            Cerita Peta is a platform to create and explore stories with maps & graphs. 
            A sprinkle of visualisation techniques can transform reports into stories that everyone enjoy.
        </p>
        <p class='my-5 text-blue-600/80 hover:underline'>
            <a href="https://jakarta.sutan.co.uk" target="_blank">
                <Fa class='inline mr-1' icon={faLink}/> Check this story out! 
            </a>
        </p>
    </div>
    <div class='w-1/2  rounded-lg flex items-center justify-center'>
        <div class='relative border  z-[99]'>
            <div class='hover:scale-110 transition-all absolute top-0 right-0 translate-x-56 translate-y-2 p-5 bg-white/80 backdrop-blur-sm shadow-xl rounded-xl w-[20vw] hover:shadow-2xl'>
                <div class='flex items-center'>
                    <div>
                        <div>
                            Stories that make sense
                        </div>
                        <div class='text-gray-500/90 text-sm mt-1'>
                            We communicate data and insight not as reports, but as stories. What makes sense to you?
                        </div>
                    </div>
                    <div class='mx-2 fill-blue-700'>
                        <Fa icon={faMap} class='text-lg text-blue '  color='#3b82f6'/>
                    </div>
                </div>
            </div>
            <!-- <div class='hover:scale-110 transition-all absolute bottom-0 left-0 -translate-y-28 translate-x-52 p-5 bg-white/80 backdrop-blur-sm shadow-xl rounded-xl w-[20vw] hover:shadow-2xl'>
                <div class='flex flex-row items-center'>
                    <div class='flex-grow'>
                        <div>
                            Advanced Analysis Techniques
                        </div>
                        <div class='text-gray-500/90 text-sm mt-1'>
                            Open source, reproducible, and bespoke.
                        </div>
                    </div>
                    <div class='mx-2 fill-blue-700'>
                        <Fa icon={faCodeCompare} class='text-lg text-blue '  color='#3b82f6'/>
                    </div>
                </div>
            </div> -->
        </div>
        <div class='w-[50vh] h-[50vh]  '>
            <img src="{base}/{bannername}" class='z-10 h-full w-full object-cover rounded-xl transition-opacity duration-1000 ease-in-out' bind:this={imgdiv} alt="">
        </div>
    </div>
</div>



<!-- content -->

<div class='flex p-5 w-screen max-md:flex-col h-fit'>
    <a href="https://towardsdatascience.com/spatial-data-science-javascript-python-60464cbe908d" class='bg-sky-200/20 hover:shadow-2xl transition-shadow hover:underline shadow-md flex-grow mx-4 p-5 rounded-lg my-2'>
        <div >
            <h1 class='text-sky-950 font-bold text-xl mb-2'>
                Cartography
            </h1>
            <p class='text-gray-900/70'>
                We are map specialists.
            </p>
        </div>
    </a>
    <a href="https://rekayasadata.co.uk/spatial-data-science-advanced-tools-2ec7f758cdb8" class='bg-sky-200/20 hover:shadow-2xl transition-shadow hover:underline shadow-md flex-grow mx-4 p-5 rounded-lg my-2'>
        <div >
            <h1 class='text-sky-950 font-bold text-xl mb-2'>
                Network & Data Analytics
            </h1>
            <p class='text-gray-900/70'>
                Network and data analytics technique.
            </p>
        </div>
    </a>
    <a href="https://towardsdatascience.com/presenting-spatial-data-interactively-with-story-maps-2-17363598208f" class='bg-sky-200/20 hover:shadow-2xl transition-shadow hover:underline shadow-md flex-grow mx-4 p-5 rounded-lg my-2'>
        <div >
            <h1 class='text-sky-950 font-bold text-xl mb-2'>
                Interactive Reports
            </h1>
            <p class='text-gray-900/70'>
                Using javascript, we make things interactive.
            </p>
        </div>
    </a>
</div>


<div class='md:flex-grow'>

</div>

<!-- footer -->
<footer class='py-10 bg-gray-100 flex items-center'>
    <div class='mx-5'>
        &copy 2023 Rekayasa Data Spasial 
    </div>
    <div>
        <a href="https://github.com/sutanmufti/ceritapeta">
            <Fa icon={faGithub} class='inline mx-2' size='1.5em'/>
        </a>
        <a href="https://www.instagram.com/rekayasadataspasial">
            <Fa icon={faInstagram} class='inline mx-2' size='1.5em'/>
        </a>

        <a href="https://www.linkedin.com/company/91567273/admin/feed/posts/">
            <Fa icon={faLinkedin} class='inline mx-2' size='1.5em'/>
        </a>
    </div>
</footer>