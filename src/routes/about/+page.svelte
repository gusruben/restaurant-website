<script lang="ts">
	import Footer from "$lib/Footer.svelte";
	import Navbar from "$lib/Navbar.svelte";
</script>

<Navbar />


<div class="screen-section h-screen" id="hero">
    <div class="absolute h-1/2 w-full top-0 -z-10 overflow-hidden">
        <div class="flex h-full">
            <img src="/images-1.png" class="h-full max-w-[1000%] animate-move-left" alt="">
            <img src="/images-1.png" class="h-full max-w-[1000%] animate-move-left" alt="">
        </div>
    </div>
    <div class="absolute h-1/2 w-full bottom-0 -mb-[calc(4000%/3341)] -z-10 overflow-hidden">
        <div class="flex h-full">
            <img src="/images-2.png" class="h-full max-w-[1000%] animate-move-right" alt="">
            <img src="/images-2.png" class="h-full max-w-[1000%] animate-move-right" alt="">
        </div>
    </div>
    <div class="absolute w-full h-full inset-0 -z-1 bg-primary/80"></div>
    <h1 class="font-script text-8xl text-black/90">Our Story</h1>
</div>
<div class="screen-section h-auto py-22 bg-primary -z-10">
    <img src="/hero-bg.png" alt="" class="absolute w-full h-full inset-0 -z-10 opacity-40">
    <div class="absolute bg-[url(/map.png)] w-[80%] h-[80%] bottom-0 left-0 -z-1 bg-contain bg-[left_bottom] bg-no-repeat opacity-50"></div>

    <div class="h-full w-full max-w-[72rem] mx-36 flex flex-col items-center justify-center self-center">
        <h1 class="text-5xl 2xl:text-6xl font-script text-[#545147] mb-8 2xl:mb-16">Who We Are</h1>
        <div class="flex flex-col md:flex-row justify-center w-full gap-22 2xl:gap-30 max-w-[64rem] px-6">
            <div class="flex flex-col items-center text-center md:max-w-[30vw]">
                <h2 class="text-2xl 2xl:text-3xl font-bold">John Chef</h2>
                <p class="opacity-70 text-lg 2xl:text-xl [line-height:1.3em]">Chef Chef has written a best-selling cookbook and won multiple James Beard Awards for his innovative Mediterranean cuisine.</p>
                <div class="w-[30vh] h-[30vh] relative">
                    <img src="/chef1-paint.png" alt="" class="rounded-full w-[30vh] h-[30vh] object-cover mt-4 2xl:mt-6 scale-125">
                    <img src="/olives-2.png" alt="" class="absolute -z-1 -top-[10%] right-[55%] w-full scale-50">
                </div>
            </div>
            <div class="flex flex-col items-center text-center md:max-w-[30vw]">
                <h2 class="text-2xl 2xl:text-3xl font-bold">Remi Ratatouille</h2>
                <p class="opacity-70 text-lg 2xl:text-xl [line-height:1.3em]">Chef Ratatouille has received the prestigious Bocuse d’Or medal and opened five critically acclaimed restaurants.</p>
                <div class="w-[30vh] h-[30vh] relative">
                    <img src="/chef2-paint.png" alt="" class="rounded-full w-[30vh] h-[30vh] object-cover mt-4 2xl:mt-6 scale-125">
                    <img src="/olives-1.png" alt="" class="absolute -z-1 top-[10%] left-[40%] w-full scale-75">
                </div>
            </div>
        </div>
        <p class="text-center max-w-7/12 mt-24 2xl:mt-18 text-lg 2xl:text-xl [line-height:1.3em]">
            Azur is the creative vision of acclaimed chefs John Chef and Remi Ratatouille. Both culinarians had spent
            years working in high-end restaurants across Greece, Italy, and Spain, but after their paths crossedin
            2010, they realized their mutual dream: creating a dining experience that honors both the Earth and the rich
            culinary heritage of the Mediterranean basin.
            <br><br>
            In 2011, Azur opened it’s doors, bringing authentic Mediterranean cuisine to the heart of Washington, DC.
        </p>
        <!-- <p class="text-center max-w-7/12 mt-8 2xl:mt-18 text-lg 2xl:text-xl [line-height:1.3em]">Azur was established in 2011 by John Chef and Remi Ratatouille. They both wanted to share their love for Mediterranean cuisine with the world, so they came together to form a restaurant.</p> -->
    </div>
</div>
<div class="screen-section h-auto py-22 bg-[url(/wood-2.png)] bg-cover px-20">
    <h1 class="text-5xl 2xl:text-6xl font-script text-tertiary mb-22 2xl:mb-24">Our Process</h1>
    <div class="container mx-auto grid grid-cols-1 md:grid-cols-3 gap-16 2xl:gap-20 max-w-7xl">
        <div class="flex flex-col items-center text-center">
            <div class="mb-16 relative w-32 h-32">
                <img src="/herbs.png" alt="Herbs" class="w-32 h-32 object-contain mb-4 scale-250 drop-shadow-md">
            </div>
            <h2 class="text-2xl font-bold text-tertiary mb-2">House-Made Everything</h2>
            <p class="text-lg text-tertiary/80">
                From our signature flatbread to our hand-rolled pasta, we make everything in-house using the freshest ingredients.
            </p>
        </div>
        
        <div class="flex flex-col items-center text-center">
            <div class="mb-16 relative w-32 h-32">
                <img src="/pan.png" alt="Pan" class="w-32 h-32 object-contain mb-4 scale-250 drop-shadow-md">
            </div>
            <h2 class="text-2xl font-bold text-tertiary mb-2">Traditional Methods</h2>
            <p class="text-lg text-tertiary/80">
                We incorporate time-honored Mediterranean cooking techniques to deliver authentic flavors in every dish.
            </p>
        </div>
        
        <div class="flex flex-col items-center text-center">
            <div class="mb-16 relative w-32 h-32">
                <img src="/salad.png" alt="Salad" class="w-32 h-32 object-contain mb-4 scale-250 drop-shadow-md">
            </div>
            <h2 class="text-2xl font-bold text-tertiary mb-2">Zero Waste</h2>
            <p class="text-lg text-tertiary/80">
                Nothing goes to waste in our kitchen. compost food scraps for our garden and use biodegradable packaging to minimize our impact on the environment.
            </p>
        </div>
    </div>
</div>
<div class="screen-section bg-[url(/wood.png)] pb-48 px-8 h-auto">
    <h1 class="text-5xl 2xl:text-6xl font-script text-tertiary mb-14 md:mb-22 2xl:mb-24 pt-20">Our Philosophy</h1>

    <p class="max-w-2xl text-center text-lg">
        At Azur, we know that to make the best food requires the best ingredients. This is why we partner with local
        farmers and run our own herb garden: to make sure that every dish we serve is fresh and environmentally friendly.
        We receive new shipments of produce daily, which means our ingredients are often harvested only a few hours
        before they end up on the your plate.
        <br><br>
        Our sustainability efforts don’t stop at the menu: from energy-efficient kitchen equipment to our composting
        program to our minimal-waste policies, we’re dedicated to leaving the smallest possible environmental footprint
        while simultaneously offering the highest quality dining experience.
    </p>

    <div class="absolute bottom-0 w-full h-48 bg-[url(/leaves.png)] bg-repeat-x bg-left-bottom bg-contain"></div>
</div>
<div class="absolute w-full z-10 shadow-[0px_0px_40px_rgba(0,0,0,0.5)]">
    <Footer />
</div>


<style>
    :global(html) {
        scroll-behavior: auto;
    }
</style>