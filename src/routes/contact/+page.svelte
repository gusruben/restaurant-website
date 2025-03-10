<script>

	import Footer from "$lib/Footer.svelte";
import Navbar from "$lib/Navbar.svelte";

</script>
<Navbar />

<div class="screen-section gap-12 bg-[url(/wood-2.png)]">
    <h1 class="text-7xl font-script text-accent">Contact</h1>

    <div class="flex flex-col max-w-[60vw] text-xl gap-4">
        <textarea placeholder="Message" class="w-full bg-[url(/wood-3.png)] bg-[length:50vw] bg-[30%] rounded-xl px-4
        py-2 inset-shadow-sm inset-shadow-tertiary/30 placeholder:text-[#36342b]/70 text-[#36342b] h-32
        resize-none focus:outline-2 focus:outline-tertiary/90"></textarea>
        <div class="flex flex-row w-full gap-4 flex-wrap">
            <input type="text" placeholder="First Name" class="bg-[url(/wood-3.png)] bg-[length:50vw] rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-tertiary/30 shrink placeholder:text-[#36342b]/70 text-[#36342b] w-full lg:w-auto">
            <input type="text" placeholder="Last Name" class="bg-[url(/wood-3.png)] bg-[length:50vw] bg-[20%] rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-tertiary/30 shrink placeholder:text-[#36342b]/70 text-[#36342b] w-full lg:w-auto">
        </div>
        <input type="email" placeholder="Email Address" class="w-full bg-[url(/wood-3.png)] bg-[length:50vw] bg-[50%] rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-tertiary/30 placeholder:text-[#36342b]/70 text-[#36342b] focus:outline-2 focus:outline-tertiary/90">
        <button class="bg-tertiary text-secondary rounded-xl px-4 py-2 inset-shadow-sm inset-shadow-primary/25 cursor-pointer hover:bg-[#5c5a50] active:bg-[#4b483d]">Submit</button>
    </div>
</div>

<Footer />