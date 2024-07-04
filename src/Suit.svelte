<script>
    import { writable } from 'svelte/store';
  
    // Define writable store for selected color
    const selectedColor = writable(null);
  
    // Function to handle color click
    function handleColorClick(color) {
      selectedColor.set(color);
    }
  
    // Function to handle form submission
    function handleSubmit() {
      alert('Form submitted!');
    }
  </script>
  
  {#each ['red', 'blue', 'green', 'yellow'] as color}
    <!-- Loop through each color -->
    <button
      on:click={() => handleColorClick(color)}
      style="
        background-color: {selectedColor === color ? color : 'white'};
        color: {selectedColor === color ? 'white' : 'black'};
      "
    >
      {color}
    </button>
  {/each}
  
  <button
    disabled={selectedColor === null}
    on:click={() => handleSubmit()}
    style="
      opacity: {selectedColor === null ? 0.4 : 1};
      cursor: {selectedColor === null ? 'auto' : 'pointer'}
    "
  >
    Submit
  </button>
  