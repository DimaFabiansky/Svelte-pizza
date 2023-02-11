<script>
  import Button from "./Button.svelte";
  import { link } from "svelte-spa-router";
  import { cart } from "./store/store.js";

  let cartList;
  let unsub = cart.subscribe((value) => {
    cartList = value;
  });

  $: sumPrice = countSumPrice(cartList);

  function countSumPrice(array) {
    let price = 0;

    array.forEach((element) => {
      price += element.price * element.count;
    });

    return price;
  }
</script>

<header>
  <div class="container">
    <div class="logo">
      <div class="img">
        <img src="/img/img-logo.svg" alt="X" />
      </div>
      <div class="text">
        <div class="name">Svelte Pizza</div>
        <div class="description">найсмачніша піца</div>
      </div>
    </div>
    <div class="card-button">
      <a href="/cart" class="button orange" use:link>
        <span>$ {sumPrice}</span> | <span>{cartList.length}</span>
      </a>
    </div>
  </div>
</header>
