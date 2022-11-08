<script lang="ts">
  type Data = {
    name: string;
    email: string;
    email2: string;
    telephone: string;
    message: string;
  };
  let name = '';
  let email = '';
  let email2 = '';
  let telephone = '';
  let message = '';

  let errors = {
    name: false,
    email: false,
    email2: false,
    telephone: false,
    message: false,
  };

  const handleSubmit = () => {
    if (!email) {
      errors.email = true;
    }
    if (!email2) {
      errors.email2 = true;
    }
    if (!message) {
      errors.message = true;
    }
    if (!name) {
      errors.name = true;
    }
    if (!telephone) {
      errors.telephone = true;
    }

    if (email !== email2) {
      errors.email2 = true;
      return;
    }

    if (email && message && name && telephone && email2) {
      alert(`${name}, Gracias por contactarte, te responderemos a la brevedad`);
      name = '';
      email = '';
      email2 = '';
      telephone = '';
      message = '';
    }
  };
</script>

<form class="form" id="form" on:submit|preventDefault={handleSubmit}>
  <h3>Contactanos llenando todos los campos</h3>
  <section class="form__first-section">
    <label>
      <span>Nombre</span>
      <div>
        <input type="text" placeholder="Nombre" name="name" bind:value={name} />
        <p id="error_name">
          {#if errors.name}
            <span>Por favor ingrese su nombre</span>
          {/if}
        </p>
      </div>
    </label>

    <label for=""
      ><span>Telefono</span>

      <div>
        <input
          type="text"
          placeholder="Telefono"
          name="telephone"
          bind:value={telephone}
        />
        <p id="error_telefono">
          {#if errors.telephone}
            El telefono es requerido
          {/if}
        </p>
      </div>
    </label>
  </section>

  <section class="form__second-section">
    <label for=""
      ><span>Correo</span>
      <div>
        <input
          type="email"
          name="email"
          placeholder="Correo"
          bind:value={email}
        />
        <p id="error_email">
          {#if errors.email}
            El email es requerido
          {/if}
        </p>
      </div>
    </label>

    <label for=""
      ><span>Correo</span>
      <div>
        <input
          type="email"
          name="email2"
          placeholder="Repite el correo"
          bind:value={email2}
        />
        <p id="error_email2">
          {#if errors.email2}
            Los emails no coinciden
          {/if}
        </p>
      </div>
    </label>

    <label for=""
      ><span>Mensaje</span>
      <div>
        <textarea name="message" placeholder="Mensaje" bind:value={message} />
        <p id="error_mensaje">
          {#if errors.message}
            El mensaje es requerido
          {/if}
        </p>
      </div>
    </label>
  </section>
  <section class="section-button">
    <button type="submit" class="form__button">Enviar</button>
  </section>
</form>

<style>
  .form h3 {
    color: #f7bd45;
    font-size: 1.5rem;
    font-weight: 600;
    margin: 1rem 0;
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
    color: black;
  }

  .form__first-section label {
    display: flex;
    justify-content: center;
    /* align-items: center; */
    width: 100%;
    color: white;
  }

  .form__first-section label span {
    padding-top: 20px;
  }
  .form__first-section label div {
    display: flex;
    flex-direction: column;
    width: 100%;
  }

  .form__first-section label div p {
    width: 100%;
    margin: 0;
    color: #b71540;
  }

  .form__second-section {
    display: flex;
    flex-direction: column;
    width: 50%;
  }

  .form__second-section label {
    display: flex;
    justify-content: center;
    /* align-items: center; */
    gap: 10px;
    width: 100%;
    color: white;
  }
  .form__second-section label span {
    padding-top: 20px;
  }

  .form__second-section label div {
    display: flex;
    width: 100%;
    flex-direction: column;
  }

  .form__second-section label div input {
    flex: 1;
    color: black;
  }
  textarea {
    color: black;
  }

  .form__second-section label div p {
    width: 100%;
    margin: 0;
    color: #b71540;
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

  .form__button:hover {
    background-color: #347e8a;
  }

  .form .section-button {
    padding: 10px;
    width: 50%;
    display: flex;
    justify-content: flex-end;
  }
</style>
