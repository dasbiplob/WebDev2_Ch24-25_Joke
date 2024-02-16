<script>
    let password = "";
    let checker = false;
  
    const resetVariables = () => {
      password = "";
      checker = false;
    };
  
    const show = () => {
      checker = true;
    };
  </script>
  
  <label for="password">Enter the secret password:</label>
  <input id="password" type="password" bind:value={password} />
  <button on:click={show} disabled={password !== "AW96B6" && password !== "Alohomora"}>
    Show
  </button>
  
  {#if checker && password === "AW96B6"}
    <p>Opening up!</p>
  {:else if checker && password === "Alohomora"}
    <p>Impossible!</p>
  {/if}
  