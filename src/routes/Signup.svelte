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

  let email = "";
  let password = "";

  const signUp = async () => {
    try {
      await firebase.auth().createUserWithEmailAndPassword(email, password);
      // User signed up successfully
      console.log("User signed up successfully");
    } catch (error) {
      // Handle signup error
      console.log(error.message);
    }
  };
</script>

<main>
  <div class="signup-box">
    <h1>Sign Up</h1>
    <form on:submit|preventDefault={signUp}>
      <label for="first-name">First Name</label>
      <input type="text" id="first-name" placeholder="" />
      <label for="last-name">Last Name</label>
      <input type="text" id="last-name" placeholder="" />
      <label for="email">Email</label>
      <input type="email" id="email" bind:value={email} required />
      <label for="password">Password</label>
      <input type="password" id="password" bind:value={password} required />
      <button id="submit" type="submit">Sign Up</button>
    </form>
    <p>
      <br />
      <a href="#">Terms and Condition</a> and <a href="#">Policy Privacy</a>
    </p>
  </div>
  <p class="para-2">
    Already have an account? <a href="/login">Login here</a>
  </p>
</main>

<style>
  .signup-box {
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
  .para-2 {
    text-align: center;
    color: rgb(0, 0, 0);
    font-size: 15px;
    margin-top: -10px;
  }
  .para-2 a {
    color: #49c1a2;
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
