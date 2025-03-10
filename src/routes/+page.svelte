<script lang="ts">
	import Footer from "$lib/Footer.svelte";
    import { onMount } from "svelte";

    let navbar: HTMLDivElement;
    let navOpen = false;

    let overlayOpen = false;

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

{#if overlayOpen}
    <!-- svelte-ignore a11y_no_static_element_interactions -->
    <!-- svelte-ignore a11y_click_events_have_key_events -->
    <div class="fixed w-full h-full inset-0 bg-black/30 z-[100]" onclick={() => overlayOpen = false}>
        <div class="fixed md:max-w-[30%] bg-[url(/wood.png)] bg-cover rounded-xl top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 px-6 py-8 flex flex-col gap-2 shadow-3xl">
            <h1 class="font-extrabold text-accent text-5xl text-center mb-4">TSA Information</h1>
            <a href="/reference" class="text-2xl bg-tertiary text-secondary rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-primary/25 cursor-pointer hover:bg-[#5c5a50] active:bg-[#4b483d] w-[80vw] md:max-w-[100%] text-center">Reference Page</a>
            <a href="/work-log.pdf" class="text-2xl bg-tertiary text-secondary rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-primary/25 cursor-pointer hover:bg-[#5c5a50] active:bg-[#4b483d] w-[80vw] md:max-w-[100%] text-center">Work Log</a>
            <p class="text-lg mt-3 text-center">Made by Gus Ruben & Ruadhan Keller-Mcleer</p>

        </div>
    </div>
    
    <!-- svelte-ignore a11y_consider_explicit_label -->
    <button class="fixed top-8 right-8 bg-[url(/wood.png)] bg-[length:50vw] rounded-xl p-4 w-16 h-16 z-[101] cursor-pointer" onclick={() => overlayOpen = false}>
        <svg data-slot="icon" aria-hidden="true" fill="none" stroke-width="1.5" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path d="M6 18 18 6M6 6l12 12" stroke-linecap="round" stroke-linejoin="round"></path>
        </svg>
    </button>
{/if}

<div class="fixed w-full flex flex-row py-5 px-8 lg:px-12 items-center gap-10 z-50 text-lg xl:text-xl transition-all
    group data-scrolled:bg-secondary/75 data-scrolled:backdrop-blur-3xl data-scrolled:py-2" bind:this={navbar}>
    <img src="/logo.png" alt="Azur" class="h-16 xl:h-20 xl:group-data-scrolled:h-14 mr-auto text-4xl lg:text-5xl font-script transition-all z-50">
    <a href="/#hero" class="mt-[0.3em] hover:text-accent hidden md:block">Home</a>
    <a href="/about" class="mt-[0.3em] hover:text-accent hidden md:block">About</a>
    <a href="/menu" class="mt-[0.3em] hover:text-accent hidden md:block">Menu</a> 
    <a href="/contact" class="mt-[0.3em] hover:text-accent hidden md:block">Contact</a> 
    <!-- <a href="/#hero" class="mt-[0.3em] hover:text-accent">Service</a> -->
    <div class="w-[calc(30vw-2.5rem)]"></div>
    <button onclick={() => overlayOpen = true} class="mt-[0.3em] text-secondary hover:text-primary absolute right-48 group-data-scrolled:text-tertiary group-data-scrolled:hover:text-[#4c7b8a] transition-all hidden md:block cursor-pointer">TSA Information</button>
    <a href="/#reserve" class="mt-[0.3em] text-secondary hover:text-primary absolute right-16 group-data-scrolled:text-tertiary group-data-scrolled:hover:text-[#4c7b8a] transition-all hidden md:block">Reserve</a>
    <button class="md:hidden absolute right-4 w-16 h-16 p-4 cursor-pointer z-50" onclick={toggleNav}>
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
            <button onclick={() => overlayOpen = true} class="mt-[0.3em] hover:text-accent py-2 px-4 w-full text-left">TSA Information</button> 
            <a href="/#reserve" class="mt-[0.3em] hover:text-accent py-2 px-4 w-full">Reserve</a>
        </div>
    {/if}
</div>

<div class="w-full h-screen bg-[url(/hero-bg.png)] bg-cover overflow-x-hidden" id="hero">
    <div class="absolute w-7/12 px-8 lg:px-30 h-full flex flex-col items-start justify-center translate-y-[2rem] z-10">
        <h1 class="text-5xl lg:text-7xl font-script mb-3">Authentic<br>Mediterranean<br>Taste</h1>
        <h3 class="text-2xl lg:text-3xl opacity-70">Experience the Mediterranean,<br>right on your plate.</h3>
        <div class="flex flex-col md:flex-row">
            <div class="bg-[url(/button-primary.png)] bg-contain px-4 pt-7 pb-9 mt-4 md:mt-0 bg-no-repeat bg-center hover:brightness-125 pointer-events-none">
                <a href="/#reserve" class="text-white pointer-events-auto px-8 py-4 cursor-pointer text-lg">
                    Reserve
                </a>
            </div>
            <div class="bg-[url(/button-secondary.png)] bg-contain px-3 pt-7 pb-9 bg-no-repeat bg-center hover:brightness-110 pointer-events-none">
                <button onclick={() => overlayOpen = true} class="text-white pointer-events-auto px-8 cursor-pointer text-lg">
                    TSA&nbsp;Information
                </button>
            </div>
        </div>
    </div>
    
    <div class="absolute bg-[url(/map.png)] w-[80%] h-[80%] top-[100vh] -translate-y-full left-0 opacity-50 "></div>
    <!-- <div class="absolute w-full lg:h-screen overflow-hidden pointer-events-none lg:transform-none
                transform-[rotate(90deg)_translate(8rem,100%)] h-[100vw] origin-bottom-right transition-all duration-[2000ms]"> -->
    <div class="absolute w-full h-screen overflow-hidden pointer-events-none hidden lg:block">
        <div class="bg-[url(/blue.png)] absolute h-full w-full left-[calc(70vw+10rem)] bg-contain bg-repeat -scale-x-100"></div>
        <div class="bg-[url(/blue-edge.png)] absolute left-[70vw] translate-x-[calc(-1rem-10vh)] h-full w-full bg-contain"></div>
    </div>
    <div class="bg-[url(/plate.png)] absolute left-[70vw] top-[calc(50%+2rem)] -translate-x-1/2 -translate-y-1/2 w-[50vw] h-[70vh] bg-contain bg-no-repeat bg-center hidden lg:block"></div>
</div>
<div class="screen-section h-auto lg:h-screen p-12 lg:p-0" id="about">
    <img src="/wood-3.jpg" alt="" class="absolute inset-0 object-cover -z-1 opacity-5">

    <img src="/olives-1.png" alt="" class="absolute top-[6vh] left-0 -rotate-[30] w-[20vw] -translate-x-1/6">
    <img src="/michelin.png" alt="" class="absolute -top-[8vh] right-0 rotate-[30] w-[30vw] translate-x-5/12">
    <img src="/olives-2.png" alt="" class="absolute top-[60vh] right-0 -rotate-[90] w-[12vw] translate-x-1/6">

    <div class="h-full w-full max-w-[72rem] mx-36 flex flex-col items-center justify-center self-center">
        <h1 class="text-5xl 2xl:text-6xl font-script text-[#545147] mb-8 2xl:mb-16">About Us</h1>
        <div class="flex flex-col md:flex-row justify-center w-full gap-12 2xl:gap-30 max-w-[64rem] px-6">
            <div class="flex flex-col items-center text-center lg:max-w-[30vw]">
                <h2 class="text-2xl 2xl:text-3xl font-bold">John Chef</h2>
                <img src="/chef1.jpg" alt="" class="rounded-full w-[30vh] h-[30vh] object-cover mb-4 2xl:mt-6">
                <p class="opacity-70 text-lg 2xl:text-xl [line-height:1.3em]">“Cooking is at once child’s play and adult joy. And cooking done with care is an act of love.”</p>
            </div>
            <div class="flex flex-col items-center text-center lg:max-w-[30vw]">
                <h2 class="text-2xl 2xl:text-3xl font-bold">Remi Ratatouille</h2>
                <img src="/chef2.jpg" alt="" class="rounded-full w-[30vh] h-[30vh] object-cover mb-4 2xl:mt-6">
                <p class="opacity-70 text-lg 2xl:text-xl [line-height:1.3em]">“Everything happens in the kitchen. Life happens in the kitchen.”</p>
            </div>
        </div>
        <p class="text-center md:max-w-7/12 mt-8 text-lg 2xl:text-xl [line-height:1.3em]">
            Azur was born from the culinary partnership of John Chef and Remi Ratatouille, two chefs united by their passion for Mediterranean cuisine and sustainable dining.
        </p>
        <a href="/about#hero" class="text-xl mt-12 bg-tertiary text-secondary rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-primary/25 cursor-pointer hover:bg-[#5c5a50] active:bg-[#4b483d]">Read Our Story</a>
        <!-- <div class="bg-[url(/button-primary.png)] bg-contain px-4 pt-7 pb-9 bg-no-repeat bg-center hover:brightness-125 pointer-events-none mt-8">
            <button class="text-white pointer-events-auto px-8 py-4 cursor-pointer text-xl">
                Read Our Story
            </button>
        </div> -->
    </div>
</div>
<div class="screen-section bg-[url(/wood.png)]" id="menu">
    <h1 class="text-5xl 2xl:text-6xl font-script text-accent">Menu</h1>
    <a href="/menu" class="text-xl my-4 bg-tertiary text-secondary rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-primary/25 cursor-pointer hover:bg-[#5c5a50] active:bg-[#4b483d]">View Full</a>
    <embed src="/Menu.pdf" type="application/pdf" class="h-8/12 w-9/12 border-tertiary border-8 rounded-xl">
</div>
<div class="screen-section bg-[url(/wood-2.png)] gap-6" id="reserve">
    <img src="/plate-2.png" alt="" class="absolute -top-1/6 left-0 w-[40vw] -translate-x-1/2">
    <img src="/flour.png" alt="" class="absolute bottom-0 right-0 w-[35vw] translate-x-5/12">
    
    <h1 class="text-5xl 2xl:text-6xl font-scriptmb-8 2xl:mb-16 text-tertiary font-script">Book a Reservation</h1>
    <div class="flex flex-col max-w-[60vw] text-xl gap-4">
        <div class="flex flex-row w-full gap-4 flex-wrap">
            <input type="text" placeholder="First Name" class="bg-[url(/wood-3.png)] bg-[length:50vw] rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-tertiary/30 shrink placeholder:text-[#36342b]/70 text-[#36342b] w-full lg:w-auto">
            <input type="text" placeholder="Last Name" class="bg-[url(/wood-3.png)] bg-[length:50vw] bg-[20%] rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-tertiary/30 shrink placeholder:text-[#36342b]/70 text-[#36342b] w-full lg:w-auto">
        </div>
        <input type="email" placeholder="Email Address" class="w-full bg-[url(/wood-3.png)] bg-[length:50vw] bg-[50%] rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-tertiary/30 placeholder:text-[#36342b]/70 text-[#36342b]">
        <button class="bg-tertiary text-secondary rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-primary/25 cursor-pointer hover:bg-[#5c5a50] active:bg-[#4b483d]">Find a Table</button>
    </div>
</div>
<div class="screen-section bg-[url(/wood.png)]" id="map">
    <h1 class="text-5xl 2xl:text-6xl font-script text-accent mb-4 2xl:mb-6">Find Us</h1>
    <iframe class="h-9/12 w-9/12 border-tertiary border-8 rounded-xl" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" src="https://maps.google.com/maps?width=100%25&amp;height=600&amp;hl=en&amp;q=1600%20Pennsylvania%20Avenue,%20Washington,%20District%20of%20Columbia+(Azur%20Restaurant)&amp;t=&amp;z=14&amp;ie=UTF8&amp;iwloc=B&amp;output=embed" title="Azur Map"></iframe>
</div>
<Footer />