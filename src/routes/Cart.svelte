<script>
  import { cartItems } from "../cart.js";
  import { onMount } from "svelte";
  let cart = [];

  cartItems.subscribe((items) => {
    cart = items;
    console.log("Cart inside cart" + cart);
  });

  function removeFromCart(index) {
    cart = [...cart.slice(0, index), ...cart.slice(index + 1)];
    cartItems.set(cart); // Update the cartItems store with the updated cart array
  }

  onMount(() => {
    cartItems.set(cart);
  });
</script>

<main>
  <section id="banner" />
  <div class="shopping-cart">
    <div class="title"><h1>Cart</h1></div>
    <div class="flex-container">
      {#each cart as item, index}
        <div class="item">
          <h1>{item.name}</h1>
          <p>{item.category}</p>
          <p>{item.description}</p>
          <p>${item.price}</p>
          <button on:click={() => removeFromCart(index)}>Remove</button>
        </div>
      {/each}
    </div>
    <div class="checkout">
      <h1 class="checkOut">
        Total: ${cart.reduce((acc, item) => acc + item.price, 0)}
      </h1>
      <button class="checkOut"><h2>Checkout</h2></button>
    </div>
  </div>
</main>

<style>
  .shopping-cart {
    width: 750px;
    height: 423px;
    margin: 80px auto;
    display: flex;
    flex-direction: column;
  }

  .title {
    text-align: center;
  }

  .checkout {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
  }

  .checkOut {
    padding: 20px;
  }
</style>
