<script lang="ts">
  import StepDropdown from './StepDropdown.svelte';
  import type { ComponentType } from 'svelte';

  export let title: string;
  export let steps: string[];
  export let ingredients: { name: string; ingredients: string }[];
  export let icon: ComponentType;
  export let notes: string[];

  const getBorderColor = (title: string): string => {
    if (title.includes('Tea')) return '#8B5CF6';
    if (title.includes('Mojito')) return '#10B981';
    return '#F59E0B';
  };
</script>

<div class="card mb-6 border-l-4" style="border-left-color: {getBorderColor(title)}">
  <div class="p-6">
    <div class="flex items-center gap-3 mb-4">
      <svelte:component this={icon} size={24} class="flex-shrink-0" />
      <h2 class="text-xl font-bold">{title}</h2>
    </div>

    <div class="grid md:grid-cols-2 gap-6">
      <div class="space-y-4">
        <h3 class="font-semibold text-base">Preparation Steps</h3>
        <div class="space-y-2">
          {#each steps as step, index}
            <StepDropdown {step} stepNumber={index + 1} />
          {/each}
        </div>
        {#if notes}
          <div class="mt-4 p-3 bg-yellow-50 rounded-lg">
            <p class="text-sm font-medium text-yellow-800">Important Notes:</p>
            <ul class="text-sm text-yellow-700 list-disc pl-4 mt-1">
              {#each notes as note}
                <li>{note}</li>
              {/each}
            </ul>
          </div>
        {/if}
      </div>

      <div class="space-y-4">
        <h3 class="font-semibold text-base">Variations</h3>
        <div class="space-y-3">
          {#each ingredients as item}
            <div class="p-3 bg-gray-50 rounded-lg">
              <p class="font-medium mb-1">{item.name}</p>
              <p class="text-sm text-gray-600">{item.ingredients}</p>
            </div>
          {/each}
        </div>
      </div>
    </div>
  </div>
</div>

<style>
  .card {
    background: white;
    border-radius: 0.5rem;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  }
</style>