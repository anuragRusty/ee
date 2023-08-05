<script>
    export let options = [];
    export let selectedOption;
    export let placeholder = "";

    function handleChange(event) {
      selectedOption = event.target.value;
    }
  </script>
  
  <select bind:value={selectedOption} on:change={handleChange}>
    <option value="" disabled selected hidden>{placeholder}</option>
    {#each options as option}
      <option value={option}>{option}</option>
    {/each}
  </select>
  
  <style>
    select {
      width: auto;
      padding: 5px;
      border: 1px solid #ccc;
      border-radius: 5px;
      font-size: 16px;
    }
  </style>