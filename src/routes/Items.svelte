<script>
  import Product from "../lib/Product.svelte";
  import { cartItems } from "../cart.js";
  import { onMount } from "svelte";
  const sportsAuctionProducts = [
    {
      name: "Michael Jordan Autographed Basketball",
      category: "Basketball",
      description:
        "Official NBA basketball signed by Michael Jordan with a certificate of authenticity.",
      price: 5000,
    },
    {
      name: "Tom Brady Signed Jersey",
      category: "Football",
      description:
        "Authentic New England Patriots jersey signed by Tom Brady, the greatest quarterback of all time.",
      price: 3000,
    },
    {
      name: "Usain Bolt's Spikes",
      category: "Track and Field",
      description:
        "A pair of running spikes worn and signed by Usain Bolt, the fastest man in history.",
      price: 2000,
    },
    {
      name: "Wayne Gretzky Autographed Hockey Stick",
      category: "Hockey",
      description:
        "Genuine hockey stick used and signed by Wayne Gretzky, the legendary NHL player.",
      price: 4000,
    },
    {
      name: "Serena Williams' Tennis Racket",
      category: "Tennis",
      description:
        "Serena Williams' personal Wilson tennis racket used in multiple Grand Slam victories.",
      price: 2500,
    },
  ];
  let cart = [];
  let searchText = "";

  function addToCart(event) {
    const product = event.detail;
    cart = [...cart, product];
    cartItems.set(cart); // Update the cartItems store with the new cart array
    console.log("Cart inside items" + cart);
  }

  onMount(() => {
    cartItems.set(cart);
  });

  // Search functionality
  let filteredProducts = sportsAuctionProducts;

  function handleSearch(event) {
    searchText = event.target.value.toLowerCase();
  }

  $: {
    filteredProducts = sportsAuctionProducts.filter((product) => {
      const name = product.name.toLowerCase();
      const category = product.category.toLowerCase();
      return name.includes(searchText) || category.includes(searchText);
    });
  }
</script>

<main>
  <section id="banner">
    <div class="banner">
      <h1>Hot New Items</h1>
    </div>
  </section>

  <div class="search-wrapper">
    <label for="search">Search Products</label>
    <input
      type="search"
      id="search"
      placeholder="Search..."
      on:input={handleSearch}
    />
  </div>

  <section id="products">
    <div class="flex-container">
      {#each filteredProducts as product}
        <Product
          name={product.name}
          category={product.category}
          description={product.description}
          price={product.price}
          on:add-to-cart={addToCart}
        />
      {/each}
    </div>
  </section>
</main>

<style>
  .banner {
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(#e66465, #9198e5);
    height: 400px;
    width: 100%;
  }

  .flex-container {
    padding: 20px;
    display: flex;
    flex-wrap: wrap;
    height: 400px;
  }

  .search-wrapper {
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
    align-items: center;
    justify-content: center;
  }
</style>
