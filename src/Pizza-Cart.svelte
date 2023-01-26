<script>
  import PizzaSizeSelector from "./Pizza-size-selector.svelte";

  export let image = "";
  export let name = "Pizza";
  export let price = 100;

  export let size = [];
</script>

<div class="pizza-cart">
  <div class="img">
    <img src={image} alt="pizza-one" />
    <div class="name">{name}</div>
    <div class="size" />
    <div class="price-block">
      <div class="price">{price}</div>
      <button class="button orange" type="button">Додати</button>
    </div>
  </div>
</div>

<PizzaSizeSelector />
