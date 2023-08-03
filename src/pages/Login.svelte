<!-- Login.svelte -->
<script>
  let username = '';
  let password = '';

  function handleLogin() {
    // You can implement your login logic here
    console.log('Username:', username);
    console.log('Password:', password);
  }
</script>

<div class="container">
  <div class="login">
    <div class="input-group">
      <label for="username">Username</label>
      <input type="text" id="username" bind:value={username} />
    </div>
    <div class="input-group">
      <label for="password">Password</label>
      <input type="password" id="password" bind:value={password} />
    </div>
    <button class="submit-btn" on:click={handleLogin}>Log In</button>
  </div>
</div>

<style>
  .container {
    width: 100%;
    margin-bottom: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #f0f4f8;
  }

  .login {
    width: 300px;
    padding: 1.5rem;
    border-radius: 8px;
    background-color: #fff;
    box-shadow: 0px 4px 12px rgba(0, 0, 0, 0.1);
  }

  .input-group {
    margin-bottom: 1rem;
  }

  .input-group label {
    font-size: 0.875rem;
    font-weight: 500;
    display: block;
    margin-bottom: 0.5rem;
  }

  .input-group input {
    width: 100%;
    padding: 0.5rem;
    border: 1px solid #e2e8f0;
    border-radius: 4px;
    background-color: #f0f4f8;
    transition: border-color 0.2s ease;
  }

  .input-group input:focus {
    outline: none;
    border-color: #3182ce;
  }

  .submit-btn {
    width: 100%;
    padding: 0.75rem;
    background-color: #0f52ba;
    border-radius: 5px;
    color: #ffffff;
    font-weight: 500;
    font-size: larger;
    cursor: pointer;
    border: none;
    transition: background-color 0.2s ease;
  }

  .submit-btn:hover {
    background-color: #2b6cb0;
  }
</style>


