<script lang="ts">
  export let step: string;
  export let stepNumber: number;
  
  let isOpen = false;
  
  function toggleDropdown() {
    isOpen = !isOpen;
  }
</script>

<div class="step-container">
  <button 
    class="flex items-start gap-2 w-full text-left p-2 hover:bg-gray-50 rounded-lg transition-colors"
    on:click={toggleDropdown}
  >
    <span class="flex-shrink-0 w-6 h-6 rounded-full bg-gray-200 flex items-center justify-center text-sm font-medium">
      {stepNumber}
    </span>
    <p class="text-sm">{step}</p>
  </button>
  
  {#if isOpen}
    <div class="mt-2 p-4 bg-gray-50 rounded-lg">
      <div class="w-[100px] h-[100px] bg-gray-200 flex items-center justify-center">
        <p class="text-gray-500 text-xs">Step {stepNumber} Image</p>
      </div>
    </div>
  {/if}
</div>

<style>
  .step-container {
    border: 1px solid #e5e7eb;
    border-radius: 0.5rem;
    overflow: hidden;
  }
  
  button {
    background: none;
    border: none;
    cursor: pointer;
  }
  
  button:focus {
    outline: 2px solid #e5e7eb;
  }
</style>