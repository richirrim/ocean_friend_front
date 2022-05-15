<template>
  <div>
    <header class="main-header  l-section">
      <div class="wrapper  l-container">
        <h1 class="main-header__title">Dashboard</h1>
        <div class="user-logout">
          <div class="button  user-logout__button">
            <img class="user-logout__image" :src="require(`@/assets/images/user-image.jpg`)" alt="Imagen de usaurio logueado.">
            <i class="icon-arrow"></i>
          </div>
          <div class="card  menu-toggle">
            <div class="menu-toggle__profile">
              <img class="menu-toggle__image" :src="require(`@/assets/images/user-image.jpg`)" alt="Imagen de usaurio logueado.">
              <span class="menu-toggle__name">Woopa master</span>
            </div>
            <button class="menu-toggle__button  button">Cerrar Sesión</button>
          </div>
        </div>

      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: 'DashboardView'
}
</script>

<style scopde lang="scss">
.main-header > .wrapper {
  position: relative;
  justify-content: space-between;
  align-items: center;
}

.user-logout {
  &__button {
    padding: .3em 1em;
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
    margin-right: .5em;
    width: var(--width);
    height: var(--width);
  }
  &__button {
    background-color: var(--color-accent);
    padding: .8em .5em;
    display: block;
  }
  &__profile {
    margin-bottom: var(--gutter);
    display: flex;
    align-items: center;
  }
}

[class*=icon-]::before {
  --width: 1.5em;
  content: "";
  margin-right: 0;
  padding: 0;
  transform: rotate(180deg);
}
</style>
