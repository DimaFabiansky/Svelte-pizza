<script>
  import { onMount } from "svelte";
  import FiltrationList from "./FiltrationList.svelte";
  import Header from "./Header.svelte";
  import PizzaCart from "./Pizza-Cart.svelte";
  import SorterList from "./SorterList.svelte";
  import axios from "axios";

  let url = "http://localhost:3000/pizzas";

  let arrayPizza = [];

  let arrayFilter = [
    {
      name: "Всі",
      value: "",
    },
    {
      name: "М'ясні",
      value: "0",
    },
    {
      name: "Вегетеріанські",
      value: "1",
    },
    {
      name: "Гриль",
      value: "2",
    },
    {
      name: "Гострі",
      value: "3",
    },
    {
      name: "Закриті",
      value: "4",
    },
  ];

  let selectFilter = arrayFilter[0].value;

  let selectSort = 0;

  $: updatePizzas(selectFilter, selectSort);

  function updatePizzas(filter, sort) {
    let newUrl = url;
    if (selectFilter !== "") {
      newUrl += "?category=" + filter;
    }

    let partl = "&";
    if (selectFilter == "") {
      partl = "?";
    }
    switch (selectSort) {
      case 0:
        newUrl += partl + "_sort=rating&_order=desc";
        break;
    }

    axios({
      method: "get",
      url: newUrl,
    })
      .then((response) => {
        arrayPizza = response.data;
      })
      .catch((e) => {
        console.warn(e);
      });
  }

  function getSorter(e) {
    selectSort = e.detail.value;
  }
</script>

<!-- Header -->
<Header />

<!-- Pizza-cart -->
<section id="menu">
  <div class="container filter">
    <FiltrationList arrayList={arrayFilter} bind:selectFilter />
    <SorterList on:select={getSorter} />
  </div>

  <div class="container">
    {#each arrayPizza as pizza (pizza.id)}
      <PizzaCart {...pizza} />
    {/each}
  </div>
</section>
