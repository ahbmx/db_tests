```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Login</title>

  <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/bulma@1.0.4/css/bulma.min.css">

  <style>
    html,
    body {
      min-height: 100%;
    }

    body {
      background: #f5f7fa;
    }

    .login-page {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 2rem 1rem;
    }

    .login-card {
      width: 100%;
      max-width: 420px;
      background: white;
      border-radius: 14px;
      padding: 2.5rem;
      box-shadow: 0 10px 35px rgba(0, 0, 0, 0.08);
    }

    .login-logo {
      display: block;
      max-width: 120px;
      max-height: 90px;
      width: auto;
      height: auto;
      margin: 0 auto 1.5rem;
    }

    .login-title {
      text-align: center;
      margin-bottom: 0.5rem !important;
    }

    .login-subtitle {
      text-align: center;
      color: #7a7a7a;
      margin-bottom: 2rem;
    }

    .login-card .input {
      height: 3rem;
      border-radius: 8px;
    }

    .login-card .button {
      height: 3rem;
      border-radius: 8px;
      font-weight: 600;
    }

    .forgot-password {
      text-align: right;
      margin-top: -0.5rem;
      margin-bottom: 1.5rem;
    }

    .login-footer {
      text-align: center;
      margin-top: 1.5rem;
      color: #7a7a7a;
      font-size: 0.9rem;
    }
  </style>
</head>

<body>

  <main class="login-page">

    <div class="login-card">

      <!-- Your 170x133 logo -->
      <img
        src="images/logo.png"
        alt="Logo"
        class="login-logo"
      >

      <h1 class="title is-3 login-title">
        Welcome back
      </h1>

      <p class="login-subtitle">
        Sign in to your account to continue.
      </p>

      <form action="/login" method="POST">

        <div class="field">
          <label class="label" for="email">
            Email
          </label>

          <div class="control">
            <input
              id="email"
              name="email"
              class="input"
              type="email"
              placeholder="you@example.com"
              autocomplete="email"
              required
            >
          </div>
        </div>

        <div class="field">
          <label class="label" for="password">
            Password
          </label>

          <div class="control">
            <input
              id="password"
              name="password"
              class="input"
              type="password"
              placeholder="Your password"
              autocomplete="current-password"
              required
            >
          </div>
        </div>

        <div class="forgot-password">
          <a href="/forgot-password">
            Forgot your password?
          </a>
        </div>

        <div class="field">
          <div class="control">
            <button
              type="submit"
              class="button is-primary is-fullwidth"
            >
              Sign in
            </button>
          </div>
        </div>

      </form>

      <div class="login-footer">
        Don't have an account?
        <a href="/register">Create one</a>
      </div>

    </div>

  </main>

</body>
</html>


```
