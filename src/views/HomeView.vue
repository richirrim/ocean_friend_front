<template>
  <!--Menu-->
  <div class="home">
    <header class="main-header l-section">
      <div class="wrapper l-container">
        <img
          class="main-logo"
          :src="require(`@/assets/images/oseanfriend.png`)"
        />
        <nav class="main-nav">
          <ul class="menu">
            <router-link class="menu__link" to="/">Home</router-link>
            <router-link class="menu__link" to="/dashboard"
              >Dashboard</router-link
            >
            <router-link
              class="menu__link"
              to="#aboutUs"
              @click.prevent="scrollInto('aboutUs')"
              >Nosotros</router-link
            >
            <router-link
              class="menu__link"
              to="#aboutSystem"
              @click.prevent="scrollInto('aboutSystem')"
              >Sobre el sistema</router-link
            >
          </ul>
        </nav>
      </div>
    </header>
    <!--Banner -->
    <div class="main-banner l-section">
      <img
        class="main-banner__hero-image"
        :src="require(`@/assets/images/banner-image.jpg`)"
        alt="Imagen del banner"
      />
      <div class="main-banner__content">
        <h1 class="main-banner__title">Ocean Friend</h1>
        <h2>Organización para la preservación de las especies marinas</h2>
        <p>Hacer el cambio está al alcance de tus manos</p>
      </div>
    </div>
    <main class="main l-section">
      <!-- Nosotros -->
      <section id="#aboutUs" class="about l-section center-content">
        <div class="about__container l-container">
          <h2 class="about__title">About us</h2>
          <p class="about__text">
            Somos un grupo de biólogos que nos unimos con la comunidad para
            hacer el cambio hoy. Gracias a los reportes de la comunidad y a las
            alertas en tiempo real de nuestro Osean Friend estamos salvando
            vidas marinas todos los días.
          </p>
          <p class="about__text icon-notification">
            A una notificación de hacer el cambio.
          </p>
        </div>
      </section>
      <!---- Acerca del sistema -->
      <section id="#aboutSystem" class="about-system l-section">
        <h2 class="about-system__title">¿Cómo funciona nuestro sistema?</h2>
        <div class="about-system__wrapper l-container">
          <article class="card-info">
            <figure class="card card-info__container-image">
              <img
                class="card-info__image"
                :src="require(`@/assets/images/robot.jpg`)"
              />
            </figure>
            <div class="card-info__content">
              <h3 class="card-info__subtitle">Conoce a nuestro Osean Friend</h3>
              <p class="card-info__description">
                Osean Friend es un robot que navega por el mar buscando espacies
                que se encuentran en alguna situación de peligro.
              </p>
            </div>
          </article>
          <article class="card-info">
            <figure class="card card-info__container-image">
              <img
                class="card-info__image"
                :src="require(`@/assets/images/biologos.jpg`)"
              />
            </figure>
            <div class="card-info__content">
              <h3 class="card-info__subtitle">Equipo de biólogos</h3>
              <p class="card-info__description">
                Cuando Osean Friend encuentra un espécimen en situación de
                peligro un grupo especializado de biólogos recibe la alerta y
                así el equipo evalúa la situación para poder accionar de la
                manera más efectiva para salvar la vida del animal.
              </p>
            </div>
          </article>
          <article class="card-info">
            <figure class="card card-info__container-image">
              <img
                class="card-info__image"
                :src="require(`@/assets/images/tortuga_bolsa.jpg`)"
              />
            </figure>
            <div class="card-info__content">
              <h3 class="card-info__subtitle">Tú</h3>
              <p class="card-info__description">
                Tú como contribuyente nos puedes ayudar de dos formas:
              </p>
              <p>
                Si encuentras un animal marino en situación de peligro podrás
                ayudar haciendo un reporte describiendo la situación en la que
                se encuentra dicho espécimen, adjuntando una imagen lo mas clara
                posible y la ubicación de donde se encuentra.
              </p>
            </div>
          </article>
          <article class="card-info">
            <figure class="card card-info__container-image">
              <img
                class="card-info__image"
                :src="require(`@/assets/images/tortugas_contenido2.jpg`)"
              />
            </figure>
            <div class="card-info__content">
              <h3 class="card-info__subtitle">Ensúciate las manos</h3>
              <p class="card-info__description">
                Si eastas subscrito a nuestro sitio y estás cerca de un lugar
                donde haya un reporte, nosotros te mandamos la alerta a ti con
                instrucciones de que hacer, no te preocupes nosotros
                anticipadamente evaluamos si una persona común puede hacer la
                tarea.
              </p>
            </div>
          </article>
        </div>
      </section>
      <!--Formulario para alerta-->
      <section class="form-alert l-section l-container">
        <h2 class="form-alert__title">¿Quiere hacer un reporte?</h2>
        <div class="form-alert__content">
          <p class="form-alert__description">
            Agradecemos tus ganas de contribuir y ayudar a hacer el cambio.
            Confiamos en ti la veracidad de tu información compartida
          </p>
          <p class="form-alert__description">
            Recuerda leer aquí como funciona nuestro sistema para hacer tu
            reporte correctamente
          </p>
          <form class="form form-card card" method="post">
            <input
              v-model="name"
              class="form-card__input"
              type="text"
              name="name"
              placeholder="Nombre de la especie del animal: Tortuga"
              required
            />
            <textarea
              v-model="description"
              class="form-card__input-textarea"
              description="description"
              placeholder="Describe la situación: La tortuga tiene una bolsa de basura al redor de su cuello y no se puede mover con facilidad"
              required
            ></textarea>
            <input
              v-model="location"
              class="form-card__input"
              type="text"
              placeholder="Compartir mi ubicación"
              required
            />
            <!-- -->
            <input
              class="form-card__input-image"
              accept="image/*"
              type="file"
              multiple
            />
            <input
              class="form-card__input-submit button"
              type="submit"
              value="Enviar alerta"
              @click.prevent="createAlert"
            />
            <span>Juntos hacemos un cambio by 💙 Ocean Friend .</span>
          </form>
        </div>
      </section>
    </main>
    <!--footer-->
    <footer>
      <p>Osean Friend 2022</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
  data () {
    return {
      name: '',
      description: '',
      photo: 'tortugita.png',
      location: ''
    }
  },
  methods: {
    scrollInto (id) {
      const section = document.querySelector(`#${id}`)
      section.scrollIntoView({ behavior: 'smooth' })
    },
    async createAlert () {
      const newAlert = {
        description: this.description,
        photo: this.photo,
        location: this.location
      }

      await fetch('http://localhost:3052/alarms/create', {
        method: 'POST', // *GET, POST, PUT, DELETE, etc.
        mode: 'cors', // no-cors, *cors, same-origin
        cache: 'no-cache', // *default, no-cache, reload, force-cache, only-if-cached
        credentials: 'same-origin', // include, *same-origin, omit
        headers: {
          'Content-Type': 'application/json'
          // 'Content-Type': 'application/x-www-form-urlencoded',
        },
        redirect: 'follow', // manual, *follow, error
        referrerPolicy: 'no-referrer', // no-referrer, *no-referrer-when-downgrade, origin, origin-when-cross-origin, same-origin, strict-origin, strict-origin-when-cross-origin, unsafe-url
        body: JSON.stringify(newAlert) // body data type must match "Content-Type" header
      })

      this.description = ''
      this.photo = ''
      this.location = ''
      this.name = ''
    }
  }
}
</script>

<style scoped lang="scss">
.main-header {
  position: fixed;
  top: 0;
  background-color: var(--color-first);
  height: var(--header-height);
  width: 100%;
  opacity: 0.9;
  z-index: 100;

  .main-logo {
    width: calc(var(--header-height) / 2);
    height: calc(var(--header-height) / 2);
  }
  .main-nav {
    padding: 0;
  }
  .wrapper {
    justify-content: space-between;
    align-items: center;
  }
}
.main-banner {
  position: relative;
  border-radius: 0.5rem;
  padding: calc(var(--header-height) * 4) 1em calc(var(--header-height) * 4);
  color: #fff;
  background-color: var(--color-second);
  overflow: hidden;

  &__content {
    position: relative;
  }
  &__hero-image {
    position: absolute;
    top: 0;
    left: 0;
    opacity: 0.2;
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
    filter: blur(0.25rem);
  }
  &__title {
    font-size: calc(var(--h1-font-size) * 3);
    margin-bottom: 0.2em;
  }
}
.menu {
  margin: 0;
  padding: 0;
  list-style: none;
  display: flex;
  justify-content: space-evenly;

  &__link {
    color: #fff;
    transition: all 0.3s;
    &:hover {
      color: var(--color-accent);
    }
  }
  &__link:not(:last-child) {
    margin-right: var(--gutter);
  }
}

.about {
  &__title {
    color: var(--color-first);
  }
  &__container {
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  &__text {
    width: 60%;
  }
  &__text:last-child {
    font-weight: bold;
  }
}

.about-system {
  &__title {
    color: var(--color-first);
  }
}

.card-info {
  margin-bottom: var(--gutter);
  display: flex;
  justify-content: space-between;

  &__container-image {
    --width: 14rem;
    position: relative;
    margin: 0;
    padding: 0;
    background-color: var(--color-first);
    width: calc(var(--width) * 2);
    height: var(--width);
    overflow: hidden;
  }
  &__image {
    position: absolute;
    top: 0;
    left: 0;
    opacity: 0.3;
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
  }
  &__content {
    text-align: left;
    width: 50%;
    display: flex;
    justify-content: center;
    flex-direction: column;
  }
  &__subtitle {
    width: 100%;
  }
  &__description {
    margin: 0;
  }
}

.form-alert {
  justify-content: center;
  &__title {
    color: var(--color-first);
  }
}

.form-card {
  display: flex;
  flex-direction: column;
  & > * {
    border-radius: 0.5rem;
    padding: 1em;
    margin-bottom: 1em;
  }
  &__input,
  &__input-textarea {
    border: none;
    color: var(--color-second);
    background-color: var(--color-bg);
    &::placeholder {
      color: var(--color-accent);
    }
    &:focus {
      outline: 2px solid var(--color-accent);
    }
  }
  &__input-textarea {
    resize: none;
    width: 100%;
    height: 8rem;
  }

  &__input-submit {
    background-color: var(--color-accent);
    justify-content: center;
  }
}

footer {
  background-color: var(--color-second);
  padding: 50px 10vw;
  width: 100%;
}
</style>
