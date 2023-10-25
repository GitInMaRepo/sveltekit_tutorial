<script>
    let numbers = [0, 1, 2];
    export let sum = 0;

    const addNumber = () => {
        numbers = [...numbers, numbers.length]
    }

    $: sum = numbers.reduce((total, current) => total + current, 0);
</script>

<p>{ numbers.join('+') } equals {sum}</p>

<button on:click={addNumber}>
    Add one more
</button>