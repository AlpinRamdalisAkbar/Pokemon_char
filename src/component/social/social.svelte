<script lang="ts">
    export let socialsjson: Array<{
        name: string;
    }>;
</script>

<div class="flex items-start p-2.5">
    {#each socialsjson as social}
        <p class="ubuntu-light text-2xl pr-4 flex items-center gap-1 text-gray-500 hover:text-black transition-colors duration-300 ease-in-out">{social.name}</p>
    {/each}
</div>
