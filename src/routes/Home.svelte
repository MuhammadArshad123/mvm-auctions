<script>
  import { Link } from "svelte-navigator";
</script>

<main>
  <div class="hero">
    <h1>Welcome to My Ecommerce Website!</h1>
    <p>Shop our latest collections and find great deals.</p>
    <button><Link to="items">Shop Now</Link></button>
  </div>
  <footer>
    <p>&copy; MVM Sports Auctions.</p>
  </footer>
</main>

<style>
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

  .hero button {
    background-color: #333;
    padding: 1rem 2rem;
    border-radius: 0.5rem;
    text-decoration: none;
    font-size: 1.5rem;
    font-weight: bold;
  }

  footer {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 1rem;
  }
</style>
