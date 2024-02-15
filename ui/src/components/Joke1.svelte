<script>
    let count = $state(0);
    const fetchJoke = async () => {
    const response = await fetch("https://simple-joke-api.deno.dev/random");
    return await response.json();
  };
  </script>
  
  <h1>Count: {count}</h1>
  <button on:click={() => (count += 1)}>Increment</button>
  <button on:click={() => (count = 0)}>Reset</button>
  
  {#if count === 1}
  {#await fetchJoke()}
  <p>Thinking...</p>
{:then joke}
  <p>{joke.setup} -- {joke.punchline}</p>
{/await}
  {:else if count === 0}
    <p>I know I'll get tired of these clicking exercises.</p>
  {/if}
  
