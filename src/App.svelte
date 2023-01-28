<script>
  import Header from "./Header.svelte";
  import PizzaCart from "./Pizza-Cart.svelte";

  let arrayPizza = [
    {
      image: "/img/Pizza-img/pizza-one.jpg",
      name: "Чізбургер-піца",
      price: 395,
      size: [
        {
          name: "26 см.",
          value: 26,
        },
        {
          name: "30 см.",
          value: 30,
        },
        {
          name: "40 см.",
          value: 40,
        },
      ],
      type: [
        {
          name: "тонке",
          value: 1,
        },
        {
          name: "традиційне",
          value: 2,
        },
      ],
    },

    {
      image: "/img/Pizza-img/pizza-two.jpg",
      name: "Сирна",
      price: 450,
      size: [
        {
          name: "26 см.",
          value: 26,
        },
        {
          name: "30 см.",
          value: 30,
        },
        {
          name: "40 см.",
          value: 40,
        },
      ],
      type: [
        {
          name: "тонке",
          value: 1,
        },
        {
          name: "традиційне",
          value: 2,
        },
      ],
    },

    {
      image: "/img/Pizza-img/pizza-three.jpg",
      name: "Креветки по-азіатськи",
      price: 290,
      size: [
        {
          name: "26 см.",
          value: 26,
        },
        {
          name: "30 см.",
          value: 30,
        },
        {
          name: "40 см.",
          value: 40,
        },
      ],
      type: [
        {
          name: "тонке",
          value: 1,
        },
        {
          name: "традиційне",
          value: 2,
        },
      ],
    },

    {
      image: "/img/Pizza-img/pizza-four.jpg",
      name: "Сирна з куркою",
      price: 385,
      size: [
        {
          name: "26 см.",
          value: 26,
        },
        {
          name: "30 см.",
          value: 30,
        },
        {
          name: "40 см.",
          value: 40,
        },
      ],
      type: [
        {
          name: "тонке",
          value: 1,
        },
        {
          name: "традиційне",
          value: 2,
        },
      ],
    },

    {
      image: "/img/Pizza-img/pizza-one.jpg",
      name: "Чізбургер-піца",
      price: 395,
      size: [
        {
          name: "26 см.",
          value: 26,
        },
        {
          name: "30 см.",
          value: 30,
        },
        {
          name: "40 см.",
          value: 40,
        },
      ],
      type: [
        {
          name: "тонке",
          value: 1,
        },
        {
          name: "традиційне",
          value: 2,
        },
      ],
    },

    {
      image: "/img/Pizza-img/pizza-two.jpg",
      name: "Сирна",
      price: 450,
      size: [
        {
          name: "26 см.",
          value: 26,
        },
        {
          name: "30 см.",
          value: 30,
        },
        {
          name: "40 см.",
          value: 40,
        },
      ],
      type: [
        {
          name: "тонке",
          value: 1,
        },
        {
          name: "традиційне",
          value: 2,
        },
      ],
    },

    {
      image: "/img/Pizza-img/pizza-three.jpg",
      name: "Креветки по-азіатськи",
      price: 290,
      size: [
        {
          name: "26 см.",
          value: 26,
        },
        {
          name: "30 см.",
          value: 30,
        },
        {
          name: "40 см.",
          value: 40,
        },
      ],
      type: [
        {
          name: "тонке",
          value: 1,
        },
        {
          name: "традиційне",
          value: 2,
        },
      ],
    },

    {
      image: "/img/Pizza-img/pizza-four.jpg",
      name: "Сирна з куркою",
      price: 385,
      size: [
        {
          name: "26 см.",
          value: 26,
        },
        {
          name: "30 см.",
          value: 30,
        },
        {
          name: "40 см.",
          value: 40,
        },
      ],
      type: [
        {
          name: "тонке",
          value: 1,
        },
        {
          name: "традиційне",
          value: 2,
        },
      ],
    },
  ];
</script>

<!-- Header -->
<Header />

<!-- Pizza-cart -->
<section id="menu">
  <div class="container">
    {#each arrayPizza as pizza}
      <PizzaCart {...pizza} />
    {/each}
  </div>
</section>
