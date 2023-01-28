<script>
  import PizzaSizeSelector from "./Pizza-size-selector.svelte";

  export let image = "";
  export let name = "Pizza";
  export let price = 100;
  export let size = [];
  export let type = [];
</script>

<div class="pizza-cart">
  <div class="img"><img src={image} alt="pizza-one" /></div>
  <div class="name">{name}</div>

  <PizzaSizeSelector {type} {size} />

  <div class="price-block">
    <div class="price">від {price} грн</div>
    <button class="button pizza" type="button">+ Додати</button>
  </div>
</div>
