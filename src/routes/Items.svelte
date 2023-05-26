<script>
  import Product from "../lib/Product.svelte";
  import { cartItems } from "../cart.js";
  import { onMount } from "svelte";
  const sportsAuctionProducts = [
    {
      imgLink:
        "https://upload.wikimedia.org/wikipedia/commons/thumb/7/72/Basketball_Clipart.svg/1024px-Basketball_Clipart.svg.png",
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

  <div class="flex-container">
    <div class="search-wrapper">
      <label for="search">Search Products</label>
      <input
        type="search"
        id="search"
        placeholder="Search..."
        on:input={handleSearch}
      />
    </div>
  </div>

  <div class="products">
    {#each filteredProducts as product}
      <div class="product-container">
        <Product
          imgLink={product.imgLink}
          name={product.name}
          category={product.category}
          description={product.description}
          price={product.price}
          on:add-to-cart={addToCart}
        />
      </div>
    {/each}
  </div>
</main>

<style>
  /* Styles for the banner section */
  #banner {
    background: linear-gradient(#e66465, #9198e5);
    height: 400px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  #banner h1 {
    font-size: 3rem;
    color: #fff;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
  }

  /* Styles for the search input */
  .search-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 80%;
    margin: 20px auto;
  }

  .search-wrapper label {
    font-size: 1.2rem;
    color: #555;
  }

  #search {
    width: 100%;
    height: 3rem;
    font-size: 1.5rem;
    padding: 0.5rem;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin-top: 0.5rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }

  /* Styles for the product cards */
  .products {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    align-items: stretch;
    width: 80%;
    margin: 0 auto;
  }
</style>
