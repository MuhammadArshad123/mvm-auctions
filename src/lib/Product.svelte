<script>
  export let imgLink = "";
  export let name = "";
  export let category = "";
  export let description = "";
  export let price = 0;
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
  function addToCart() {
    dispatch("add-to-cart", {
      imgLink,
      name,
      category,
      description,
      price,
    });
  }
</script>

<main>
  <div class="item">
    <img src={imgLink} alt="" />
    <div class="header">
      <h2>{name}</h2>
      <h3>{category}</h3>
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
    justify-content: center;
    align-items: center;
    font-family: Arial, sans-serif;
  }

  .item {
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 20px;
    width: 300px;
    text-align: center;
    background-color: #f9f9f9;
  }

  .header {
    margin-bottom: 10px;
  }

  h2 {
    font-size: 1.5rem;
    margin-bottom: 5px;
  }

  h3 {
    font-size: 1rem;
    color: #777;
    margin: 0;
  }

  p {
    margin-bottom: 10px;
  }

  img {
    width: 100%;
    max-height: 200px;
    object-fit: cover;
    border-radius: 5px;
    margin-bottom: 10px;
  }

  .addToCart {
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    padding: 10px 20px;
    cursor: pointer;
  }

  .addToCart:hover {
    background-color: #0056b3;
  }
</style>
