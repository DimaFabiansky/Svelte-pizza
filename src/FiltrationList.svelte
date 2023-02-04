<script>
  export let arrayList = [];

  export let selectFilter;
</script>

<div class="filter-list">
  {#each arrayList as filter}
    <label>
      <input
        type="radio"
        bind:group={selectFilter}
        name="filter"
        value={filter.value}
      />
      <span class="button black">{filter.name}</span>
    </label>
  {/each}
</div>
