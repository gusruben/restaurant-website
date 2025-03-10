<script lang="ts">
    import Footer from "$lib/Footer.svelte";
	import Navbar from "$lib/Navbar.svelte";
    import { onMount } from "svelte";

    let embed = false;

    onMount(() => {
        embed = window.self !== window.top;
    });
</script>


{#if !embed}
    <Navbar />
{/if}

<div class="screen-section justify-start pt-28 pb-22 h-auto min-h-screen">
    {#if !embed}
        <h1 class="text-7xl font-script text-accent">Menu</h1>
    {/if}

    <div class="bg-[url(/button-primary.png)] bg-contain px-4 pt-7 pb-9 bg-no-repeat bg-center hover:brightness-125 pointer-events-none my-8">
        <a href="/Menu.pdf" class="text-white pointer-events-auto px-10 py-6 cursor-pointer text-xl">
            View PDF
        </a>
    </div>

    <div class="w-full max-w-[80vw] h-max relative">
        <div class="grid grid-cols-1 lg:grid-cols-2 shadow-2xl">
            <img src="/menu-images/menu-2.png" alt="Menu Page 2">
            <img src="/menu-images/menu-3.png" alt="Menu Page 3">
        </div>
        <img src="/menu-images/menu-1.png" alt="" class="absolute top-0 left-0 -translate-x-1/2 -z-1 scale-75 shadow-xl h-1/2 lg:h-full">
        <img src="/menu-images/menu-4.png" alt="" class="absolute top-0 right-0 translate-x-1/2 -z-1 scale-75 shadow-xl h-1/2 lg:h-full">
    </div>
</div>

<Footer />