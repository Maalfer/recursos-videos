# HTML utilizado en el vídeo de prueba:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Login Seguro (Simulado)</title>
  <style>
    * {
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(-45deg, #1e3c72, #2a5298, #0f2027, #203a43);
      background-size: 400% 400%;
      animation: gradientBG 15s ease infinite;
      display: flex;
      justify-content: center;
      align-items: center;
      color: #fff;
    }

    @keyframes gradientBG {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .container {
      background: rgba(255, 255, 255, 0.05);
      padding: 40px;
      border-radius: 15px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
      backdrop-filter: blur(12px);
      width: 100%;
      max-width: 400px;
    }

    h1 {
      text-align: center;
      margin-bottom: 30px;
      font-size: 28px;
      color: #f1c40f;
    }

    label {
      display: block;
      margin-top: 10px;
      margin-bottom: 5px;
      font-weight: 600;
    }

    input[type="text"],
    input[type="password"] {
      width: 100%;
      padding: 12px;
      border: none;
      border-radius: 8px;
      background-color: #ffffff15;
      color: #fff;
      font-size: 16px;
      margin-bottom: 15px;
      transition: background-color 0.3s ease;
    }

    input::placeholder {
      color: #ccc;
    }

    input:focus {
      outline: none;
      background-color: #ffffff25;
    }

    button {
      width: 100%;
      padding: 12px;
      background-color: #f1c40f;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      font-weight: bold;
      color: #000;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    button:hover {
      background-color: #e0b90a;
    }

    .message {
      margin-top: 20px;
      padding: 15px;
      border-radius: 10px;
      text-align: center;
      font-weight: bold;
      font-size: 16px;
    }

    .success {
      background-color: #27ae60cc;
      color: #ecf0f1;
    }

    .error {
      background-color: #e74c3ccc;
      color: #fff;
    }

    .note {
      text-align: center;
      margin-top: 30px;
      font-size: 0.85em;
      color: #ccc;
    }

    code {
      background-color: rgba(255,255,255,0.1);
      padding: 2px 6px;
      border-radius: 5px;
      color: #f1c40f;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Acceso al Sistema</h1>
    <form method="GET" action="">
      <label for="user">Usuario:</label>
      <input type="text" id="user" name="user" placeholder="admin" required />

      <label for="pass">Contraseña:</label>
      <input type="password" id="pass" name="pass" placeholder="123123" required />

      <button type="submit">Iniciar sesión</button>
    </form>

    <div id="mensaje"></div>

    <div class="note">
      <p><strong>⚠️ Este ejemplo es educativo.</strong></p>
      <p>Los datos se reflejan en la URL. No es seguro para producción.</p>
      <p>Prueba válida: <code>?user=admin&pass=123123</code></p>
    </div>
  </div>

  <script>
    const params = new URLSearchParams(window.location.search);
    const user = params.get('user');
    const pass = params.get('pass');
    const mensaje = document.getElementById('mensaje');

    if (user && pass) {
      if (user === "admin" && pass === "123123") {
        mensaje.innerHTML = `<div class="message success">✅ Bienvenido, <strong>${user}</strong>. Has iniciado sesión correctamente.</div>`;
      } else {
        mensaje.innerHTML = `<div class="message error">❌ Usuario o contraseña incorrectos.</div>`;
      }
    }
  </script>
</body>

</html>
``` 




# PÁGINA DE ERROR 403 PERSONALIZADA

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Error 403 - Acceso Prohibido</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(145deg, #1f1f1f, #121212);
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      color: #ffffff;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      text-align: center;
    }

    .error-container {
      animation: fadeIn 1.2s ease-in-out;
    }

    h1 {
      font-size: 10rem;
      margin: 0;
      color: #ff4c4c;
      text-shadow: 2px 2px 20px rgba(255, 76, 76, 0.4);
    }

    h2 {
      font-size: 2rem;
      margin: 0.5em 0;
      color: #f0db4f;
    }

    p {
      font-size: 1.2rem;
      max-width: 500px;
      margin: 1em auto;
      color: #cccccc;
    }

    .btn {
      display: inline-block;
      margin-top: 20px;
      padding: 12px 24px;
      background: #f0db4f;
      color: #000;
      text-decoration: none;
      font-weight: bold;
      border-radius: 8px;
      transition: all 0.3s ease;
      box-shadow: 0 4px 15px rgba(240, 219, 79, 0.4);
    }

    .btn:hover {
      background: #ffe84f;
      transform: translateY(-3px);
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(-30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .icon-lock {
      font-size: 5rem;
      margin-bottom: 20px;
      color: #ff4c4c;
    }

  </style>
</head>
<body>
  <div class="error-container">
    <div class="icon-lock">🔒</div>
    <h1>403</h1>
    <h2>Acceso Prohibido</h2>
    <p>No tienes permiso para acceder a este recurso. Si crees que esto es un error, contacta con el administrador del sitio.</p>
    <a href="/" class="btn">Volver al Inicio</a>
  </div>
</body>
</html>
``` 

