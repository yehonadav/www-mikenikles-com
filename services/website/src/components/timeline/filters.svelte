<script>
  import { filteredFilters, selectedFilters, allFiltersForDisplay } from "../../stores/timeline";
</script>

<style>
  #filters {
    scroll-margin-top: 4em;
  }
</style>

<div id="filters" class="mt-10 px-2 grid grid-cols-2 gap-4 md:mt-20 md:mb-10 md:flex md:justify-between">
  {#each $allFiltersForDisplay as filter}
    <div class="relative flex items-center text-{filter}">
      <div class="flex items-center h-6 md:h-10">
        <input
          id="filter_{filter}"
          type="checkbox"
          checked={$filteredFilters.includes(filter)}
          bind:group={$selectedFilters}
          value={filter}
          class="focus:ring-indigo-500 h-5 w-5 border-gray-300 rounded md:h-10 md:w-10" />
      </div>
      <div class="ml-2 text-lg md:ml-3 md:text-2xl">
        <label
          for="filter_{filter}"
          class="font-medium uppercase">{filter}</label>
      </div>
    </div>
  {/each}
</div>
