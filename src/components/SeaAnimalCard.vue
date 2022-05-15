<template>
  <div class="row">
    <div class="card  card-animal">
      <figure class="card  card-animal__container">
        <img class="card-animal__image" :src="require(`@/assets/images/tortuga-image.jpg`)" alt="">
      </figure>
      <div class="card-animal__content">
        <span class="card-animal__name">{{ animalInfo.name }}</span>
        <span class="card-animal__location  icon-location">{{ animalInfo.location }}</span>
        <span class="card-animal__description  icon-description">Descripción: <span contenteditable="true">{{ animalInfo.description }}</span></span>
        <span class="card-animal__status" :class="statusClass">Estado: <span>{{ status(animalInfo.isAttended) }}</span></span>
      </div>
      <i class="icon-arrow" @click="isToggleShow ? this.isToggleShow = false : this.isToggleShow = true"></i>
      <div class="card-animal__dropdown-list" :class="toggleDropdown">
          <div class="card">
            <div class="card  card-animal__map"></div>
          </div>
          <div class="card">
            <img class="card  card-animal__image-big" :src="require(`@/assets/images/tortuga-image.jpg`)" alt="">
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SeaAnimalCard',
  props: [
    'animalInfo'
  ],
  data () {
    return {
      isToggleShow: false,
      animalStatus: Boolean
    }
  },
  computed: {
    toggleDropdown () {
      return this.isToggleShow ? 'show-dropdown-list' : 'hidden-dropdown-list'
    },
    statusClass () {
      return this.animalStatus ? 'icon-done' : 'icon-slope'
    }
  },
  methods: {
    status (animalStatus) {
      this.animalStatus = this.animalInfo.attended
      return animalStatus ? 'Rescatado' : 'Pendiente'
    }
  }
}
</script>

<style scopde lang="scss">
.card-animal {
  --width: 88px;
  position: relative;
  width: 100%;
  display: flex;
  flex-direction: row;
  align-items: center;

  .icon-arrow {
    cursor: pointer;
    transition: all .3s;
    &:active {
      transform: scale(.70);
    }
  }

  &__container {
    padding: 0;
    width: calc(var(--width) + 2em);
    height: var(--width);
    overflow: hidden;
    margin: 0;
    margin-right: var(--gutter);
  }
  &__content {
    width: 20%;
    display: flex;
    flex-direction: column;
    text-align: left;
    width: 100%;
  }
  &__image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
  }
  &__name {
    font-weight: bold;
    color: var(--color-first);
  }
  &__dropdown-list {
    position: absolute;
    top: 9em;
    right: 0;
    left: 0;
    display: flex;
    z-index: 100;
    transition: all .3s;
    & > div:first-child {
      margin-right: var(--gutter);
      flex-basis: 70%;
    }
    & > div:last-child {
      flex-basis: 30%;
    }
  }
  &__map {
    background-color: var(--color-first);
    width: 100%;
    height: 100%;
    flex-basis: 60%;
  }
  &__image-big {
    padding: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
    flex-basis: 40%;
  }

  .show-dropdown-list {
    display: flex;
  }
  .hidden-dropdown-list {
   display: none;
  }
}
</style>
