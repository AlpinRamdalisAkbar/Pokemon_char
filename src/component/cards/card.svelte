<script lang="ts">
    export let imagesjson: Array<{
        image: string;
        name: string;
        type: string;
        gradient: string;
    }>;
</script>
<div class="flex flex-row overflow-x-auto gap-8 p-4  hide-scrollbar">
    {#each imagesjson as card}
        <div class="min-w-[300px] rounded-4xl {card.gradient} overflow-hidden shadow-lg flex flex-col items-center p-4 ">
            
            <div class="relative z-10">
                <img
                    class="w-2xs mx-auto mt-4 hover:animate-bounce hover:scale-110 transition-transform duration-300 ease-in-out"
                    src={card.image}
                    alt="{card.name} from {card.type}"
                />
            </div>
            <p class="text-center ubuntu-light text-4xl text-white">{card.name}</p>
            <p class="text-center ubuntu-light text-2xl text-white">{card.type}</p>
        </div>
    {/each}
</div>


<style lang="postcss">
    @reference "tailwindcss";

    .ubuntu-light {
        font-family: "Ubuntu", sans-serif;
        font-weight: 500;
        font-style: normal;
    }

    .hide-scrollbar {
        scrollbar-width: none;
        -ms-overflow-style: none;
    }

    .hide-scrollbar::-webkit-scrollbar {
        display: none;
    }
</style>