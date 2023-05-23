<script>
  import { Router, Link, Route } from "svelte-navigator";
  import Home from "./routes/Home.svelte";
  import Cart from "./routes/Cart.svelte";
  import Items from "./routes/Items.svelte";
  import Signup from "./routes/Signup.svelte";
  import firebase from "firebase/compat/app";
  import "firebase/compat/auth";
  import Login from "./routes/Login.svelte";
  import OrderComplete from "./routes/OrderComplete.svelte";
</script>

<main>
  <Router>
    <nav>
      <div class="logo"><h1>MVM Auctions</h1></div>
      <div class="nav-links">
        <ul class="nav-list">
          <li><Link to="/">Home</Link></li>
          <li><Link to="cart">Cart</Link></li>
          <li><Link to="items">Items</Link></li>
          <li><Link to="signup">Signup</Link></li>
        </ul>
      </div>
    </nav>

    <Route path="/" component={Home} />
    <Route path="/cart" component={Cart} />
    <Route path="/items" component={Items} />
    <Route path="/signup" component={Signup} />
    <Route path="/login" component={Login} />
    <Route path="/order-complete" component={OrderComplete} />
  </Router>
</main>

<style>
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #333;
    color: #fff;
    padding: 1rem;
  }

  nav ul {
    display: flex;
    list-style: none;
  }

  li {
    margin-left: 1rem;
  }
</style>
