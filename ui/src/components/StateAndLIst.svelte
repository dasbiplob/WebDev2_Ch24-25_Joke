<script>
    let text = $state("");
    let items = $state([]);
  
    const addItem = () => {
      items[items.length] = text;
      text = "";
    }
  </script>
  
  <label for="item">Type in the item name:</label>
  <input id="item" type="text" bind:value={text} /><br/>
  <button on:click={addItem}>Add</button>
  
  <p>Items:</p>
  
  <ul>
  {#each items as item}
    <li>{item}</li>
  {/each}
  </ul>
  
  <p>The list has {items.length} item{items.length === 1? '':'s'}.</p>
