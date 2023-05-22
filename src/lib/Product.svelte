<script>
  export let name = "";
  export let category = "";
  export let description = "";
  export let price = 0;

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
    <h1>{name}</h1>
    <p>{category}</p>
    <p>{description}</p>
    <p>{price}</p>
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
    margin: 2rem;
    background: #f02c0a33;
    width: 20em;
    height: 20em;
    margin: 100px;
    border-radius: 10px;
    border: 4px;
    border-color: red;
  }
  h1 {
    font-size: 2rem;
  }
  p {
    font-size: 1.5rem;
  }

  button {
    margin: 10px;
  }
</style>
