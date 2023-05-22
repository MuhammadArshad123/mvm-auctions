<script>
  import Signupbutton from "../lib/Signupbutton.svelte";
</script>

<main>
  <div class="signup-box">
    <h1>Sign Up</h1>
    <form>
      <label for="first-name">First Name</label>
      <input type="text" id="first-name" placeholder="" />
      <label for="last-name">Last Name</label>
      <input type="text" id="last-name" placeholder="" />
      <label for="email">Email</label>
      <input type="email" id="email" placeholder="" />
      <label for="password">Password</label>
      <input type="password" id="password" placeholder="" />
      <label for="confirm-password">Confirm Password</label>
      <input type="password" id="confirm-password" placeholder="" />
      <Signupbutton />
      <closeform />
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
    color: white;
    font-size: 15px;
    margin-top: -10px;
  }
  .para-2 a {
    color: #49c1a2;
  }
</style>
