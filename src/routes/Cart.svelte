<script>
  import { cartItems } from "../cart.js";
  import { onMount } from "svelte";
  import { createEventDispatcher } from "svelte";
  import Checkout from "../lib/Checkout.svelte";
  import { Link } from "svelte-navigator";
  let cart = [];

  const dispatch = createEventDispatcher();
  let showCheckoutForm = false;

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

  function toggleCheckoutForm() {
    showCheckoutForm = !showCheckoutForm;
  }

  function handleCheckout() {
    toggleCheckoutForm();
    dispatch("checkout");
  }
</script>

<main>
  <section class="flex-container-1">
    <div class="shopping-cart">
      <div class="title"><h1>Cart</h1></div>
      <div class="flex-container-2">
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
        <button class="checkOut" on:click={handleCheckout}
          ><h2><Link to="order-complete">Checkout</Link></h2></button
        >
      </div>
    </div>
    {#if showCheckoutForm}
      <div id="checkout-form">
        <Checkout on:checkout={() => toggleCheckoutForm()} />
      </div>
    {/if}
  </section>
</main>

<style>
  .flex-container-1 {
    display: flex;
    flex-direction: row;
    align-items: center;
  }
  .shopping-cart {
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
