<script>
  let email = "";
  let firstName = "";
  let lastName = "";
  let company = "";
  let apartment = "";
  let city = "";
  let country = "";
  let state = "";
  let zipcode = "";
  let phone = "";
</script>

<div class="checkout-form">
  <h1>Checkout Form</h1>

  <h3>Contact Information</h3>
  <input type="email" placeholder="Email" bind:value={email} />

  <h3>Shipping Address</h3>
  <input type="text" placeholder="First Name" bind:value={firstName} />
  <input type="text" placeholder="Last Name" bind:value={lastName} />
  <input type="text" placeholder="Company" bind:value={company} />
  <input type="text" placeholder="Apartment/Suite" bind:value={apartment} />
  <input type="text" placeholder="City" bind:value={city} />
  <input type="text" placeholder="Country" bind:value={country} />
  <input type="text" placeholder="State" bind:value={state} />
  <input type="text" placeholder="Zipcode" bind:value={zipcode} />
  <input type="text" placeholder="Phone" bind:value={phone} />

  <button>Complete Order</button>
</div>

<style>
  .checkout-form {
    max-width: 400px;
    margin: 0 auto;
  }

  .checkout-form h2 {
    font-size: 24px;
    margin-bottom: 16px;
  }

  .checkout-form h3 {
    font-size: 18px;
    margin-top: 24px;
    margin-bottom: 12px;
  }

  .checkout-form p {
    margin-bottom: 12px;
  }

  .checkout-form input,
  .checkout-form button {
    width: 100%;
    padding: 8px;
    margin-bottom: 12px;
    border: 1px solid #ccc;
    border-radius: 4px;
  }

  .checkout-form button {
    background-color: #007bff;
    color: #fff;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
  }

  .checkout-form button:hover {
    background-color: #0056b3;
  }
</style>
