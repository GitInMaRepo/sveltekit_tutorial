<script>
    import Annoyance from "./annoyance.svelte";
	import Arrayextension from "./arrayextension.svelte";

    const name = "Blorpo";

    let count = 0;
    let someothervalue = 0;
    let reactivevalue = 0;

    $: {
        reactivevalue = count + someothervalue;
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
{#if count > 10 && count < 15}
<p>The counter is kinda big</p>
{/if}
{#if count > 15}
<p>The counter is VERY big</p>
{/if}
<p>{reactivevalue}</p>

<style>
    h1 {
        color: turquoise;
    }
</style>

<Arrayextension sum={count}></Arrayextension>