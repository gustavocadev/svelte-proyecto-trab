<header class="main-header">Juan perez - Desarrollador web</header>
<nav class="nav">
  <ul class="main-menu">
    <li class="main-menu__item">
      <a href="/" class="main-menu__link">Inicio</a>
    </li>
    <li class="main-menu__item">
      <a href="/nosotros" class="main-menu__link">Nosotros</a>
    </li>
    <li class="main-menu__item">
      <a href="/clientes" class="main-menu__link">Clientes</a>
    </li>
    <li class="main-menu__item">
      <a href="/contactos" class="main-menu__link">Contacto</a>
    </li>
  </ul>
</nav>
<slot />

<footer>
  <p>Todos los derechos reservados Juan Perez - Desarrollo web</p>
</footer>

<style>
  :global(html) {
    scroll-behavior: smooth;
  }
  :global(body) {
    margin: 0;
    font-family: 'Roboto', sans-serif;
  }
  .main-header {
    text-align: center;
    padding: 0.5rem;
  }
  .main-menu {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #3f99a6;
    list-style: none;
    padding: 10px;
    margin: 0;
  }

  .main-menu__item {
    padding: 0 10px;
  }

  .main-menu__link {
    color: white;
    padding: 10px;
    text-decoration: none;
  }
  footer {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 20px;
    font-size: 18px;
    background-color: #3f99a6;
  }
</style>
