<header class="main-header">Juan perez - Desarrollador web</header>
<nav class="nav">
  <ul class="mainMenu">
    <li class="mainMenu__item">
      <a href="/" class="mainMenu__link">Inicio</a>
    </li>
    <li class="mainMenu__item">
      <a href="/nosotros" class="mainMenu__link">Nosotros</a>
    </li>
    <li class="mainMenu__item">
      <a href="/clientes" class="mainMenu__link">Clientes</a>
    </li>
    <li class="mainMenu__item">
      <a href="/contactos" class="mainMenu__link">Contactos</a>
    </li>
  </ul>
</nav>
<slot />

<footer>
  <p>Todos los derechos reservados Juan Perez - Desarrollo web</p>
</footer>

<style>
  :global(body) {
    margin: 0;
    font-family: 'Roboto', sans-serif;
  }
  :global(.mainMenu) {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #3f99a6;
    list-style: none;
    padding: 10px;
    margin: 0;
  }

  :global(.mainMenu__item) {
    padding: 0 10px;
  }

  :global(.mainMenu__link) {
    color: white;
    padding: 10px;
    text-decoration: none;
  }
  :global(footer) {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 10px;
    font-size: 20px;
    background-color: #c3d6f1;
  }
</style>
