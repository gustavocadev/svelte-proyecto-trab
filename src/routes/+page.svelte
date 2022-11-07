<script lang="ts">
  type Data = {
    name: string;
    email: string;
    email2: string;
    telephone: string;
    message: string;
  };

  const goToContact = () => {
    window.scrollTo(0, document.body.scrollHeight);
  };

  const handleSubmit = (e: any) => {
    const formData = new FormData(e.currentTarget as HTMLFormElement);

    const data = Object.fromEntries(formData as any) as Data;

    const { email, message, name, telephone, email2 } = data;
    if (!email || !message || !name || !telephone) {
      alert('Por favor, complete todos los campos');
      return;
    }

    if (email2 !== email) {
      alert('El email no coincide');
      return;
    }

    alert(
      `${data.name}, Gracias por contactarte, te responderemos a la brevedad`
    );
    e.currentTarget.reset();
  };
</script>

<svelte:head>
  <title>Home</title>
</svelte:head>
<section class="section-bg">
  <header class="section-bg__header-bg">
    <h1 class="text-5xl">Diseño y desarrollo de aplicaciones web</h1>
    <div class="section-bg__header-bg-location">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="icon icon-tabler icon-tabler-map-pin"
        width="74"
        height="74"
        viewBox="0 0 24 24"
        stroke-width="1.5"
        stroke="#C4A53A"
        fill="none"
        stroke-linecap="round"
        stroke-linejoin="round"
      >
        <path stroke="none" d="M0 0h24v24H0z" fill="none" />
        <circle cx="12" cy="11" r="3" />
        <path
          d="M17.657 16.657l-4.243 4.243a2 2 0 0 1 -2.827 0l-4.244 -4.243a8 8 0 1 1 11.314 0z"
        />
      </svg>
      <p>Ilo, Moquegua</p>
    </div>
    <button class="section-bg__header-bg-button" on:click={goToContact}
      >Contactar</button
    >
  </header>
  <div class="layer-black">
    <div class="img-background" />
  </div>
</section>

<main class="main">
  <header class="main__header">
    <h2>Mis servicios</h2>
  </header>
  <section class="section-services">
    <article>
      <header>Diseño Web</header>
      <div class="article__bg-icon">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="icon icon-tabler icon-tabler-palette"
          width="44"
          height="44"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="#2c3e50"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path stroke="none" d="M0 0h24v24H0z" fill="none" />
          <path
            d="M12 21a9 9 0 1 1 0 -18a9 8 0 0 1 9 8a4.5 4 0 0 1 -4.5 4h-2.5a2 2 0 0 0 -1 3.75a1.3 1.3 0 0 1 -1 2.25"
          />
          <circle cx="7.5" cy="10.5" r=".5" fill="currentColor" />
          <circle cx="12" cy="7.5" r=".5" fill="currentColor" />
          <circle cx="16.5" cy="10.5" r=".5" fill="currentColor" />
        </svg>
      </div>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Blanditiis
        sint rerum vitae nobis quod ea pariatur voluptatem quidem nam! Et
        deserunt molestias dolorum autem ex magni animi non ipsa eos.
      </p>
    </article>
    <article>
      <header>Aplicaciones moviles</header>
      <div class="article__bg-icon">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="icon icon-tabler icon-tabler-brand-android"
          width="44"
          height="44"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="#2c3e50"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path stroke="none" d="M0 0h24v24H0z" fill="none" />
          <line x1="4" y1="10" x2="4" y2="16" />
          <line x1="20" y1="10" x2="20" y2="16" />
          <path
            d="M7 9h10v8a1 1 0 0 1 -1 1h-8a1 1 0 0 1 -1 -1v-8a5 5 0 0 1 10 0"
          />
          <line x1="8" y1="3" x2="9" y2="5" />
          <line x1="16" y1="3" x2="15" y2="5" />
          <line x1="9" y1="18" x2="9" y2="21" />
          <line x1="15" y1="18" x2="15" y2="21" />
        </svg>

        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="icon icon-tabler icon-tabler-brand-apple"
          width="44"
          height="44"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="#2c3e50"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path stroke="none" d="M0 0h24v24H0z" fill="none" />
          <path
            d="M9 7c-3 0 -4 3 -4 5.5c0 3 2 7.5 4 7.5c1.088 -.046 1.679 -.5 3 -.5c1.312 0 1.5 .5 3 .5s4 -3 4 -5c-.028 -.01 -2.472 -.403 -2.5 -3c-.019 -2.17 2.416 -2.954 2.5 -3c-1.023 -1.492 -2.951 -1.963 -3.5 -2c-1.433 -.111 -2.83 1 -3.5 1c-.68 0 -1.9 -1 -3 -1z"
          />
          <path d="M12 4a2 2 0 0 0 2 -2a2 2 0 0 0 -2 2" />
        </svg>
      </div>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ipsam facilis
        error repellat, a aspernatur modi enim repudiandae. Repellat recusandae
        officia, sequi et tempore quo iure, autem qui, dolorum amet placeat?
      </p>
    </article>
    <article>
      <header>E-commerce</header>
      <div class="article__bg-icon">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="icon icon-tabler icon-tabler-shopping-cart"
          width="44"
          height="44"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="#2c3e50"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path stroke="none" d="M0 0h24v24H0z" fill="none" />
          <circle cx="6" cy="19" r="2" />
          <circle cx="17" cy="19" r="2" />
          <path d="M17 17h-11v-14h-2" />
          <path d="M6 5l14 1l-1 7h-13" />
        </svg>
      </div>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Nam veritatis
        soluta nisi fugit! Autem minima qui eveniet quod at, distinctio quo
        corporis quibusdam nihil rerum commodi veritatis. Quisquam, ad nesciunt.
      </p>
    </article>
  </section>
  <h2 class="contact font-bold">Contacto</h2>
  <form class="form" id="form" on:submit|preventDefault={handleSubmit}>
    <h3 class="text-2xl py-2">Contactanos llenando todos los campos</h3>
    <section class="form__first-section">
      <label for=""
        ><span>Nombre</span>
        <input
          type="text"
          placeholder="Nombre"
          name="name"
          class="text-black"
        />
      </label>

      <label for=""
        ><span>Telefono</span>
        <input
          type="text"
          placeholder="Telefo"
          name="telephone"
          class="text-black"
        />
      </label>
    </section>

    <section class="form__second-section">
      <label for=""
        ><span>Correo</span>
        <input type="email" name="email" class="text-black" />
      </label>

      <label for=""
        ><span>Correo</span>
        <input type="email" name="email2" class="text-black" />
      </label>

      <label for=""
        ><span>Mensaje</span>
        <textarea name="message" class="text-black" />
      </label>
    </section>
    <section class="section-button">
      <button type="submit">Enviar</button>
    </section>
  </form>
</main>

<style>
  :global(.main-header) {
    padding: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  :global(.section-bg__header-bg) {
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100%;
    position: absolute;
    font-size: 30px;
    z-index: 150;
    width: 100%;
  }

  .section-bg__header-bg-location {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .section-bg__header-bg-button {
    cursor: pointer;
    background-color: #3f99a6;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
    border-radius: 4px;
    outline: none;
    border: 0;
    padding: 8px;
    font-size: 25px;
  }
  .section-bg__header-bg-button:hover {
    background-color: #347e8a;
  }

  .header-bg h1 {
    margin: 10px;
  }

  .img-background {
    background-image: url('/mac.jpg');
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    height: inherit;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    z-index: 10;
    opacity: 0.5;
  }

  .layer-black {
    position: absolute;
    z-index: 100;
    width: 100%;
    background-color: rgba(0, 0, 0, 0.9);
    height: inherit;
  }

  .section-bg {
    position: absolute;
    width: 100%;
    z-index: 10;
    height: calc(100vh - 300px);
  }

  .section-bg p {
    font-size: 20px;
  }

  .main {
    margin-top: 500px;
  }

  .section-services {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
  }

  .section-services header {
    text-align: center;
    font-size: 25px;
    padding: 10px;
  }

  .section-services article {
    padding: 10px;
    text-align: center;
  }

  .section-services article p {
    line-height: 2;
  }

  .main__header {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 25px;
  }

  .article__bg-icon {
    background-color: #f7bd45;
    border-radius: 100%;
    width: 100px;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 auto;
  }

  .contact {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 10px;
    font-size: 40px;
  }
  .form h3 {
    color: #f7bd45;
  }

  .form {
    display: flex;
    width: 100%;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    background-color: #757575;
  }

  .form input,
  textarea {
    padding: 10px;
    margin: 10px;
    border: none;
    border-radius: 5px;
    flex-grow: 1;
  }

  .form__second-section textarea {
    height: 100px;
  }

  .form__first-section {
    width: 50%;
    display: flex;
  }

  .form__first-section label input {
    flex-grow: 1;
  }

  .form__first-section label {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    color: white;
  }

  .form__second-section {
    display: flex;
    flex-direction: column;
    width: 50%;
  }

  .form__second-section label {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    width: 100%;
    color: white;
  }
  textarea {
    margin-left: 0;
    /* margin-right: 0; */
  }

  .form button {
    margin: 10px;
    padding: 10px 45px;
    border: none;
    border-radius: 5px;
    background-color: #3c96af;
    color: white;
    font-size: 20px;
    cursor: pointer;
  }

  .form button:hover {
    background-color: #347e8a;
  }

  .form .section-button {
    padding: 10px;
    width: 50%;
    display: flex;
    justify-content: flex-end;
  }
</style>
