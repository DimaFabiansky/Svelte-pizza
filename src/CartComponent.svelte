<script>
  import { createEventDispatcher } from "svelte";

  export let img = "/img/Pizza-img/pizza-one.jpg";
  export let name = "";
  export let size = "0";
  export let number = 0;

  export let startPrice = 100;

  let dispatcher = createEventDispatcher();

  $: countPrice = startPrice * number;
</script>

<div class="item cart">
  <div class="image">
    <img src={img} alt="pizza-one" />
  </div>

  <div class="info">
    <div class="name">{name}</div>
    <div class="type">{size} см</div>
  </div>

  <!-- Number -->
  <div class="number">
    <!-- Button - -->
    <div
      class="button"
      on:click={() => {
        number--;
        dispatcher("change", {
          count: number,
        });
      }}
    >
      -
    </div>

    <!-- Number -->
    <div class="count">{number}</div>

    <!-- Button + -->
    <div
      class="button"
      on:click={() => {
        number++;
        dispatcher("change", {
          count: number,
        });
      }}
    >
      +
    </div>
  </div>

  <!-- Price -->
  <div class="price">{countPrice} грн.</div>

  <!-- Delete -->
  <div
    class="delete"
    on:click={() => {
      dispatcher("delete");
    }}
  >
    &times;
  </div>
</div>
