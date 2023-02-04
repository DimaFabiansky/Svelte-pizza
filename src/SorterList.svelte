<script>
  import { fade } from "svelte/transition";
  import { createEventDispatcher } from "svelte";

  let dispatcher = createEventDispatcher;

  let sorterList = [
    {
      name: "популярністю",
      value: 0,
    },
    {
      name: "ціною",
      value: 1,
    },
    {
      name: "алфавітом",
      value: 2,
    },
  ];

  let selectSort = 0;

  let openList = false;

  $: selectName = sorterList[selectSort].name;

  function sendSelectSort(index) {
    selectSort = index;

    dispatcher("select", {
      value: sorterList[index].value,
    });
  }
</script>

<div class="sorter-list">
  <div class="selected">
    Сортувати за: <span
      class="name"
      on:click={() => {
        openList = !openList;
      }}>{selectName}</span
    >
  </div>

  {#if openList}
    <div class="list" transition:fade={{ duration: 200 }}>
      <ul>
        {#each sorterList as sorter, index}
          <li
            class:active={selectSort === index}
            on:click={() => {
              sendSelectSort(index);
            }}
          >
            {sorter.name}
          </li>
        {/each}
      </ul>
    </div>
  {/if}
</div>
