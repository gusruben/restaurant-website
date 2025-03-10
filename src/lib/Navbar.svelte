<script lang="ts">
    import { onMount } from "svelte";

    let navbar: HTMLDivElement;
    let navOpen = false;

    function updateNavbar() {
        if (window.scrollY > 0) {
                navbar.setAttribute("data-scrolled", "true");
            } else {
                navbar.removeAttribute("data-scrolled");
            }
    }

    function toggleNav() {
        navOpen = !navOpen;
        if (navOpen) {
            navbar.setAttribute("data-scrolled", "true");
        } else if (window.scrollY == 0) {
            navbar.removeAttribute("data-scrolled");
        }
    }

    onMount(() => {
        updateNavbar();
        window.addEventListener("scroll", updateNavbar);
    });
</script>

<div class="fixed w-full flex flex-row px-12 items-center gap-10 z-50 text-lg xl:text-xl justify-center
    transition-all data-scrolled:bg-secondary/75 data-scrolled:backdrop-blur-3xl py-2 min-h-18" bind:this={navbar}>
    <!-- <img src="/logo.png" alt="Azur" class="h-16 xl:h-14 text-4xl lg:text-5xl font-script self-baseline"> -->
    <img src="/logo.png" alt="Azur" class="h-16 xl:h-14 text-4xl lg:text-5xl font-script transition-all left-5 absolute md:left-12 top-2 z-50 pb-2 md:pb-0">
    <a href="/#hero" class="mt-[0.3em] hover:text-accent hidden md:block">Home</a>
    <a href="/about" class="mt-[0.3em] hover:text-accent hidden md:block">About</a>
    <a href="/menu" class="mt-[0.3em] hover:text-accent hidden md:block">Menu</a> 
    <a href="/contact" class="mt-[0.3em] hover:text-accent hidden md:block">Contact</a> 
    <a href="/#reserve" class="mt-[0.3em] hover:text-accent hidden md:block">Reserve</a> 
    <!-- <a href="/#hero" class="mt-[0.3em] hover:text-accent">Service</a> -->
    <!-- <div class="w-[calc(30vw-2.5rem)]"></div> -->
    <!-- <a href="/#reserve" class="mt-[0.3em] text-secondary hover:text-primary absolute right-16 text-tertiary hover:text-[#4c7b8a] transition-all">Reserve</a> 
     -->

    <button class="md:hidden absolute right-4 top-2 w-16 h-16 p-4 cursor-pointer z-50" on:click={toggleNav}>
        {#if !navOpen}
            <svg data-slot="icon" aria-hidden="true" fill="none" stroke-width="1.5" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" stroke-linecap="round" stroke-linejoin="round"></path>
            </svg>
        {:else}
            <svg data-slot="icon" aria-hidden="true" fill="none" stroke-width="1.5" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path d="M6 18 18 6M6 6l12 12" stroke-linecap="round" stroke-linejoin="round"></path>
            </svg>
        {/if}
    </button>
    
    {#if navOpen}
        <div class="fixed left-0 w-full flex flex-col top-0 pt-20 bg-secondary/75 backdrop-blur-3xl pb-2 z-40">
            <a href="/#hero" class="mt-[0.3em] hover:text-accent py-2 px-4 w-full">Home</a>
            <a href="/about" class="mt-[0.3em] hover:text-accent py-2 px-4 w-full">About</a>
            <a href="/menu" class="mt-[0.3em] hover:text-accent py-2 px-4 w-full">Menu</a>
            <a href="/contact" class="mt-[0.3em] hover:text-accent py-2 px-4 w-full">Contact</a>
            <a href="/#reserve" class="mt-[0.3em] hover:text-accent py-2 px-4 w-full">Reserve</a>
        </div>
    {/if}
</div>