<script>
    import Menu from './Menu.svelte';
    import { Hamburger } from 'svelte-hamburgers';

    let open;
</script>

<nav class="flex justify-between items-center py-10 px-8 bg-red-500 fixed z-10 w-screen">
    <a class="text-2xl font-semibold" href="/">Avyudaya Acharya</a>
    <Hamburger bind:open --color="black"/>
</nav>

<Menu bind:open/>