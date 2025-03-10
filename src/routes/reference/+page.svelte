<script>
	import Footer from "$lib/Footer.svelte";
    import Navbar from "$lib/Navbar.svelte";
</script>

<Navbar />

<div class="screen-section gap-12 bg-[url(/wood-2.png)] h-auto py-30">
    <h1 class="text-7xl font-script text-accent mb-6 text-center">Reference Page</h1>

    <div class="w-full max-w-[80vw] h-max relative">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-10">
            <div class="flex flex-col gap-6">
                <h3 class="font-extrabold text-3xl text-center">Student Copyright Checklist</h3>
                <a href="/student-copyright-checklist.pdf" class="text-2xl my-4 bg-tertiary text-secondary rounded-xl px-8 py-2 inset-shadow-sm inset-shadow-primary/25 cursor-pointer hover:bg-[#5c5a50] active:bg-[#4b483d] w-max mx-auto">View PDF</a>
                <embed src="/student-copyright-checklist.pdf" type="application/pdf" class="min-h-[80vh] border-tertiary border-8 rounded-xl">
            </div>
            <div class="flex flex-col gap-6">
                <h3 class="font-extrabold text-3xl text-center">Sources</h3>
                <a href="/sources.pdf" class="text-2xl my-4 bg-tertiary text-secondary rounded-xl px-8 py-2 inset-shadow-sm inset-shadow-primary/25 cursor-pointer hover:bg-[#5c5a50] active:bg-[#4b483d] w-max mx-auto">View PDF</a>
                <embed src="/sources.pdf" type="application/pdf" class="min-h-[80vh] border-tertiary border-8 rounded-xl">
            </div>
        </div>
    </div>
</div>

<Footer />