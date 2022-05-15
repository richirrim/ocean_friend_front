<template>
  <div>
    <header class="main-header l-section">
      <div class="wrapper l-container">
        <h1 class="main-header__title">Dashboard</h1>
        <div class="user-logout">
          <div class="button user-logout__button">
            <img
              class="user-logout__image"
              :src="require(`@/assets/images/user-image.jpg`)"
              alt="Imagen de usaurio logueado."
            />
            <i class="icon-arrow"></i>
          </div>
          <div class="card menu-toggle">
            <div class="menu-toggle__profile">
              <img
                class="menu-toggle__image"
                :src="require(`@/assets/images/user-image.jpg`)"
                alt="Imagen de usaurio logueado."
              />
              <span class="menu-toggle__name">Woopa master</span>
            </div>
            <button class="menu-toggle__button button">Cerrar Sesión</button>
          </div>
        </div>
      </div>
    </header>
    <main class="main l-section">
      <div class="main__container l-container">
        <h2 class="title">Animales marinos en peligro</h2>
        <SeaAnimalCard
          v-for="animal in seaAnimals"
          :key="animal"
          :animalInfo="animal"
        />
      </div>
    </main>
  </div>
</template>

<script>
import SeaAnimalCard from '@/components/SeaAnimalCard.vue'
import axios from 'axios'

export default {
  name: 'DashboardView',
  components: {
    SeaAnimalCard
  },
  data () {
    return {
      seaAnimals: [
        {
          name: 'Tortuga',
          location: 'sdasd adsdasd asda',
          description: 'Tortuga a la orilla del mar, patita atorada.',
          attended: true
        },
        {
          name: 'Tortuga2',
          location: 'sdasd adsdasd asda',
          description: 'Tortuga a la orilla del mar, patita atorada.',
          attended: false
        },
        {
          name: 'Tortuga3',
          location: 'sdasd adsdasd asda',
          description: 'Tortuga a la orilla del mar, patita atorada.',
          attended: false
        }
      ]
    }
  },
  mounted () {
    axios
      .get('http://localhost:3052/alarms/')
      .then((response) => {
        console.log('data', response.data)
        this.seaAnimals = response.data
      })
      .catch((error) => {
        this.errored = true
      })
      .finally(() => (this.loading = false))
  }
}
</script>

<style scopde lang="scss">
.main-header {
  & > .wrapper {
    position: relative;
    justify-content: space-between;
    align-items: center;
  }
  &__title {
    color: var(--color-first);
  }
}

.user-logout {
  &__button {
    padding: 0.3em 1em;
    width: 100%;
    margin-bottom: var(--gutter);
  }
  &__image {
    --width: 32px;
    border-radius: 50%;
    width: var(--width);
    height: var(--width);
    margin-right: var(--gutter);
    background-color: var(--color-accent);
  }
}

.menu-toggle {
  position: absolute;
  top: 4.5em;
  right: 1rem;
  width: 32rem;
  display: flex;
  display: none;
  justify-content: start;
  flex-direction: column;

  &__image {
    --width: 32px;
    border-radius: 50%;
    margin-right: 0.5em;
    width: var(--width);
    height: var(--width);
  }
  &__button {
    background-color: var(--color-accent);
    padding: 0.8em 0.5em;
    display: block;
  }
  &__profile {
    margin-bottom: var(--gutter);
    display: flex;
    align-items: center;
  }
}

[class*="icon-arrow"]::before {
  --width: 1.5em;
  content: "";
  margin-right: 0;
  padding: 0;
  transform: rotate(180deg);
}

.main {
  .title {
    text-align: left;
  }
  &__container {
    flex-direction: column;
  }
}
</style>
