<script>
</script>

<main>
  <div class="flex-container">
    <div class="login-wrapper">
      <h1>Login</h1>
      <form>
        <label for="email">Email</label>
        <input type="email" id="email" placeholder="" />
        <label for="password">Password</label>
        <input type="password" id="password" placeholder="" />
        <button class="login">Login</button>
        <closeform />
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
  .para-2 {
    text-align: center;
  }

  a {
    color: black;
  }
</style>
