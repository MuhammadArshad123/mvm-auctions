<script>
  import { Router, Link, Route } from "svelte-navigator";
  import Home from "./routes/Home.svelte";
  import Cart from "./routes/Cart.svelte";
  import Items from "./routes/Items.svelte";
  import Signup from "./routes/Signup.svelte";

  import firebase from "firebase/app";
  import "firebase/auth";

  export const firebaseConfig = {
    apiKey: "AIzaSyB--fOUZOfaiiHVRQ5mgzjdC0jiGe669lI",
    authDomain: "final-mobile-apps-59a14.firebaseapp.com",
    projectId: "final-mobile-apps-59a14",
    storageBucket: "final-mobile-apps-59a14.appspot.com",
    messagingSenderId: "592657491455",
    appId: "1:592657491455:web:03d27a57ab0d3bd25333ca",
    measurementId: "G-C3HFEPBMTP",
  };

  firebase.initializeApp(firebaseConfig);
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

  nav li {
    margin-left: 1rem;
  }
</style>
