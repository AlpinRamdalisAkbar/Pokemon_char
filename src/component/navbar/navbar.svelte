<script lang="ts">
    import Menu from "../menu.svelte";

    let {headerName = "Pokemon"} = $props(); 
    let logo = "/pokemon/pokemon-go.png"
</script>

<nav class="flex items-start justify-between p-2.5 ubuntu-light">
    <p class="pl-4 font-bold flex justify-center items-center"><img class="size-9 pr-0.5" src="{logo}" alt="{headerName}"> {headerName}</p>
    <p class="pr-4 flex items-center gap-1 text-gray-500 hover:text-black transition-colors duration-300 ease-in-out">Menu <Menu class={"inline-flex"}/></p>
</nav>