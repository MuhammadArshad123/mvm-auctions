<script>
  export let name = "";
  export let category = "";
  export let description = "";
  export let price = 0;
  export let link = "";

  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
  function addToCart() {
    dispatch("add-to-cart", {
      name,
      category,
      description,
      price,
    });
  }
</script>

<main>
  <div class="item">
    <img src={link} alt="" />
    <div class="header">
      <h1>{name}</h1>
      <h2>{category}</h2>
    </div>
    <p>{description}</p>
    <p>${price}</p>
    <button class="addToCart" on:click={addToCart}>
      <p>Add to Cart</p>
    </button>
  </div>
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .item {
    display: flex;
    flex-direction: column;
    background: #f02c0a33;
    border-radius: 10px;
    border: 4px;
    border-color: red;
  }

  .header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
  .header h2 {
    color: darkgray;
  }

  h1 {
    font-size: 2rem;
  }
  p {
    font-size: 1.5rem;
  }

  button {
    align-self: center;
    margin: 10px;
  }
</style>
