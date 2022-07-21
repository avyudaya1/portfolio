<script>
    import { fly, scale } from 'svelte/transition';
    import { quadOut } from 'svelte/easing';

    export let open;
    let scrollOff = false;

    function applyScrollOff() {
        // @ts-ignore
        document.body.style = "overflow:hidden;"
    }
    function applyScrollOn() {
        // @ts-ignore
        document.body.style = "overflow:auto;"
    }
</script>

{#if open}
    {@html applyScrollOff()}
    <section class="bg-red-500 h-screen fixed w-screen">
        <div class="my-10 mx-8">
            <div class="pt-24">
                {#each ['Home', 'Portfolio', 'Contact'] as link, i}
                    <h1 class="text-8xl uppercase font-semibold my-2 cursor-pointer" transition:fly={{ y: -15, delay: 50 * i }}>
                        {link}
                    </h1>
                {/each}
            </div>
        </div>
    
        <div class="fixed bottom-12 right-0 left-0">
            <div class="border-solid border-black border-2 h-0" transition:scale={{ duration: 750, easing: quadOut, opacity: 1 }} />
        </div>
    </section>

{:else}
{@html applyScrollOn()}
{/if}