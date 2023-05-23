<script>
  import firebase from "firebase/compat/app";
  import "firebase/compat/auth";

  const firebaseConfig = {
    apiKey: "AIzaSyA1yl7xr4j09Wess3two6ZLvxYvPHZf4O4",
    authDomain: "svelte-a5a99.firebaseapp.com",
    databaseURL: "https://svelte-a5a99-default-rtdb.firebaseio.com",
    projectId: "svelte-a5a99",
    storageBucket: "svelte-a5a99.appspot.com",
    messagingSenderId: "742835877390",
    appId: "1:742835877390:web:eb0375e961470ea5d56e5f",
    measurementId: "G-XNBX4Y74HH",
  };

  firebase.initializeApp(firebaseConfig);

  import { onMount } from "svelte";

  let email = "";
  let password = "";

  const login = async () => {
    try {
      await firebase.auth().signInWithEmailAndPassword(email, password);
      // User logged in successfully
      console.log("User logged in successfully");
    } catch (error) {
      // Handle login error
      console.log(error.message);
    }
  };

  onMount(() => {
    const loginForm = document.getElementById("loginForm");
    loginForm.addEventListener("submit", login);
  });
</script>

<main>
  <div class="flex-container">
    <div class="login-wrapper">
      <h1>Login</h1>
      <form id="loginForm">
        <label for="email">Email</label>
        <input type="email" id="email" bind:value={email} required />
        <label for="password">Password</label>
        <input type="password" id="password" bind:value={password} />
        <button type="submit">Login</button>
      </form>
      <p>
        <br />
        <a href="#">Terms and Condition</a> and <a href="#">Policy Privacy</a>
      </p>
    </div>
  </div>
</main>

<style>
  .login-wrapper {
    width: 360px;
    height: 620px;
    margin: auto;
    background-color: white;
    border-radius: 3px;
  }

  h1 {
    text-align: center;
    padding-top: 15px;
  }

  form {
    width: 300px;
    margin-left: 20px;
  }

  form label {
    display: flex;
    margin-top: 20px;
    font-size: 18px;
  }

  form input {
    width: 100%;
    padding: 7px;
    border: none;
    border: 1px solid gray;
    border-radius: 6px;
    outline: none;
  }

  p {
    text-align: center;
    padding-top: 20px;
    font-size: 15px;
  }

  button {
    width: 320px;
    height: 35px;
    margin-top: 20px;
    border: none;
    background-color: #49c1a2;
    color: white;
    font-size: 18px;
  }

  a {
    color: black;
  }
</style>
