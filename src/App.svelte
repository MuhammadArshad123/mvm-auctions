<script>
  import { Router, Link, Route } from "svelte-navigator";
  import Home from "./routes/Home.svelte";
  import Cart from "./routes/Cart.svelte";
  import Items from "./routes/Items.svelte";
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
        </ul>
      </div>
    </nav>

    <Route path="/" component={Home} />
    <Route path="/cart" component={Cart} />
    <Route path="/items" component={Items} />
  </Router>

  <div class="hero">
    <h1>Welcome to My Ecommerce Website!</h1>
    <p>Shop our latest collections and find great deals.</p>
    <a href="shop.html" class="cta">Shop Now</a>
  </div>
  <footer>
    <p>&copy; MVM Sports Auctions.</p>
  </footer>
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

  .hero {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    background-image: url("https://images.pexels.com/photos/163452/basketball-dunk-blue-game-163452.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1");
    background-size: cover;
    background-position: center;
    color: #fff;
    text-align: center;
  }

  .hero h1 {
    font-size: 3rem;
    margin-bottom: 1rem;
  }

  .hero p {
    font-size: 1.5rem;
    margin-bottom: 2rem;
  }

  footer {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 1rem;
  }

  .cta {
    background-color: #fff;
    color: #333;
    padding: 1rem 2rem;
    border-radius: 0.5rem;
    text-decoration: none;
    font-size: 1.5rem;
    font-weight: bold;
    transition: all 0.3s ease;
  }

  .cta:hover {
    background-color: #333;
    color: #fff;
    cursor: pointer;
  }
</style>
