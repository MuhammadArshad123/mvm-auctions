<script>
  import Signupbutton from "../lib/Signupbutton.svelte";
</script>

<main>
  <div class="signup-box">
    <h1>Sign Up</h1>
    <h4>DO IR RNNNN</h4>
    <form>
      <label>First Name</label>
      <input type="text" placeholder="" />
      <label>Last Name</label>
      <input type="text" placeholder="" />
      <label>Email</label>
      <input type="email" placeholder="" />
      <label>Password</label>
      <input type="password" placeholder="" />
      <label>Confirm Password</label>
      <input type="password" placeholder="" />
      <Signupbutton />
      <closeform />
    </form>
    <p>
      RAHHHHHHHHHHHHHHHHHHHH <br />
      <a href="#">Terms and Condition</a> and <a href="#">Policy Privacy</a>
    </p>
  </div>
  <p class="para-2">
    Already have an account? <a href="login.svelte">Login here</a>
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

  h4 {
    text-align: center;
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
