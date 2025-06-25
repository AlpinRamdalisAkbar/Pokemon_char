<script lang="ts">
    import { dragscroll, type DragScrollParameters  } from "@svelte-put/dragscroll";

    export let imagesjson: Array<{
        image: string;
        name: string;
        type: string;
        gradient: string;
    }>;


    const getGradientClass = (gradient: string) => {
        switch (gradient.toLowerCase()) {
            case "yellow":
                return "bg-gradient-to-t from-yellow-400 to-yellow-100";
            case "pink":
                return "bg-gradient-to-t from-pink-400 to-pink-100";
            case "blue":
                return "bg-gradient-to-t from-blue-400 to-blue-100";
            case "purple":
                return "bg-gradient-to-t from-purple-400 to-purple-100";
            default:
                return "bg-gradient-to-t from-red-400 to-red-100";
        }
    };
    
</script>
<div class="flex flex-row overflow-y-auto gap-8 p-4  hide-scrollbar" use:dragscroll={{event:'mouse'}}>
    <div class="flex flex-row overflow-x-auto gap-8 p-4 hide-scrollbar">
        {#if imagesjson.length == 0}
            <h1 class="text-6xl ubuntu-light text-gray-400">No Cards data here</h1>
        {:else}
            {#each imagesjson as card}
                <div class="min-w-[300px] rounded-4xl {getGradientClass(card.gradient)} shadow-lg flex flex-col items-center p-4 ">
                    
                    <div class="relative z-10">
                        <img
                            class="w-2xs mx-auto mt-4 hover:animate-bounce hover:scale-110 transition-transform duration-300 ease-in-out"
                            src={card.image}
                            alt={`${card.name} with type ${card.type}`} title={card.name}
                        />
                    </div>
                    <p class="text-center ubuntu-light text-4xl text-white">{card.name}</p>
                    <p class="text-center ubuntu-light text-2xl text-white">{card.type}</p>
                </div>
            {/each}
        {/if}
    </div>
    
</div>


<style lang="postcss">
    @reference "tailwindcss";
    .hide-scrollbar {
        scrollbar-width: none;
        -ms-overflow-style: none;
    }

    .hide-scrollbar::-webkit-scrollbar {
        display: none;
    }
</style>