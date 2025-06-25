<script lang="ts">
    import Card from "../component/cards/card.svelte";
    import Nav from "../component/nav.svelte";
    import Navbar from "../component/navbar/navbar.svelte";
    import Social from "../component/social/social.svelte";

    let headerName = "Pokèmon";

    let imagesjson = [
        {
            image: "/pokemon/pikachu_528098.png",
            name: "Pikachu",
            type: "Electric",
            gradient: "yellow"
        },
        {
            image: "/pokemon/avatar_1752713.png",
            name: "Jigglypuff",
            type: " Normal · Fairy",
            gradient: "pink"
        },
        {
            image: "/pokemon/avatar_1752813.png",
            name: "Snorlax",
            type: "Normal",
            gradient: "blue"
        },{
            image: "/pokemon/meoth.png",
            name: "Meowth",
            type: "Normal",
            gradient: "yellow"
        },
        {
            image: "/pokemon/avatar.png",
            name: "Ditto",
            type: "Normal",
            gradient: "pink"
        },
        {
            image: "/pokemon/rattata.png",
            name: "Rattata",
            type: "Dark · Normal",
            gradient: "purple"
        }
    ];

    let socialsjson = [
        { name: "Facebook" },
        { name: "Instagram" },
        { name: "X" }
    ];
</script>
<title>{headerName}</title>
<div class="min-h-screen bg-gray-100">
    <div class="container mx-auto px-4 py-8">
        <Navbar headerName={headerName} />

        <div class="flex flex-wrap justify-center gap-6 my-20">
            <Card {imagesjson} />
        </div>
        <div class="flex justify-between space-x-6 mt-10 text-gray-600 text-lg">
            <Social {socialsjson} />
            <Nav/>
        </div>
    </div>
</div>

<style lang="postcss">
    @reference "tailwindcss";

    :global(html) {
        @apply bg-gray-100;
    }
</style>
