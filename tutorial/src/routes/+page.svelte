<script>
    import Annoyance from "./annoyance.svelte";

    const name = "Blorpo";

    let count = 0;
    let someothervalue = 0;

    $: {
        alert(count);
        alert(someothervalue);
    }

    const increment = () => count++

</script>

<h1>Welcome to SvelteKit, {name.toUpperCase()}</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<Annoyance></Annoyance>
<button on:click={increment}>
    Clicked {count} {count === 1 ? 'time' : 'times' }
</button>
<button on:click={() => someothervalue = someothervalue + 2}>
    another clicky
</button>

<style>
    h1 {
        color: turquoise;
    }
</style>