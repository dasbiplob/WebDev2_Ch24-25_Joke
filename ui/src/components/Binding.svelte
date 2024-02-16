<script>
    let text = $state("");
    let disabled = $state(false);
    let selected = $state("");
  
    const resetVariables = () => {
      text = "";
      disabled = false;
      selected = "";
    };
  
    const keyUp = (event) => {
      if(event.key === "Enter") {
        resetVariables();
      }
    };
  </script>
  
  <input type="text" bind:value={text} {disabled} on:keyup={keyUp} />
  Typing disabled <input type="checkbox" bind:checked={disabled} />
  <button on:click={resetVariables}>Reset</button>
  
  <p>
    Text: {text}, Selected: {selected}
  </p>
  
  <select bind:value={selected}>
    <option value="">Select an option</option>
    <option value="1">Option 1</option>
    <option value="2">Option 2</option>
  </select>
