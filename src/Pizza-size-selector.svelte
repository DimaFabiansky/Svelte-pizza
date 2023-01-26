<script>
  import { onMount } from "svelte";

  export let size = [];

  let selectedValue = size[0].value;

  $: windowPosition = getPosition(selectedValue);

  function getPosition(selectedValue) {
    let value = size.findIndex((fn) => {
      if (fn.value == selectedValue) {
        return true;
      }
    });

    return (33.3333 * value).toString() + "%";
  }

  onMount(function () {
    if (Boolean(size[0])) {
      selectedValue = size[0].value;
    }
  });
</script>

<div class="selector">
  <div class="type" />

  <div class="size">
    <span class="window" style="left" : {windowPosition} />
    <label>
      <input type="radio" bind:group={selectedValue} name="size" value="1" />
      20 см
    </label>
    <label>
      <input type="radio" bind:group={selectedValue} name="size" value="2" />
      30 см
    </label>
    <label>
      <input type="radio" bind:group={selectedValue} name="size" value="3" />
      40 см
    </label>
  </div>
</div>
