<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view/>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Righteous&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Varela+Round&display=swap');

#app {
  // font-family: Avenir, Helvetica, Arial, sans-serif;
  // -webkit-font-smoothing: antialiased;
  // -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

/*-----------------------*\
    $Variables
\*-----------------------*/
:root {
  /* Paleta de colores */
  --color-first: #03a9f4;
  --color-second: #0277BD;
  --color-accent: #80d8ff;
  --color-bg: #E1F5FE;
  --color-white: #e0e0e0;
  --color-text: #263238;
  /* Tipografia */
  --font-title: 'Righteous', cursive;
  --font-content: 'Varela Round', sans-serif;
  --h1-font-size: 1.95rem;
  --h2-font-size: 1.56rem;
  --h3-font-size: 1.25rem;
  --body-font-size: 1rem;
  --smaller-font-size: .8rem;
  --small-font-size: .64rem;
  /* Layout */
  --header-height: 60px;
  --max-width: 1200px;
  --gutter: 1em;
}

/*-----------------------*\
  $Base
\*-----------------------*/
*,
*::after,
*::before { box-sizing: border-box; }
body {
  font-size: var(--body-font-size);
  font-family: var(--font-content);
  color: var(--color-text);
  background-color: var(--color-bg);
}
img {
  display: block;
  width: 100%;
  max-width: 100%;
  height: auto;
}
a {
  color: var(--color-accent);
  text-decoration: none;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  margin-top: 0;
  font-family: var(--font-title);
  text-transform: uppercase;
}
h1 { font-size: var(--h1-font-size); }
h2 { font-size: var(--h2-font-size); }
h3 { font-size: var(--h3-font-size); }

/*-----------------------*\
  $Layout
\*-----------------------*/
.l-container {
  margin-left: auto;
  margin-right: auto;
  padding-left: 1rem;
  padding-right: 1rem;
  max-width: var(--max-width);
  height: 100%;
  display: flex;
  flex-wrap: wrap;
}
.l-section {
  margin-bottom: 6rem;
}
.center-block {
  margin-left: auto;
  margin-right: auto;
}
.center-content { text-align: center; }

/*-----------------------*\
  $icons
\*-----------------------*/
[class*=icon-]::before {
  --width: 1.5em;
  content: "";
  display: inline-block;
  margin-right: .4em;
  width: var(--width);
  height: var(--width);
  &:hover::before,
  &:focus::before {
    filter: invert(16%) sepia(17%) saturate(743%) hue-rotate(155deg) brightness(92%) contrast(89%);
  }
}
.icon-arrow::before {
  content: "";
  background-image: url("./assets/icons/icon-arrow.svg");
  background-repeat: no-repeat;
  filter: invert(16%) sepia(17%) saturate(743%) hue-rotate(155deg) brightness(92%) contrast(89%);
}
.icon-description::before {
  content: "";
  background-image: url("./assets/icons/icon-description.svg");
  background-repeat: no-repeat;
  filter: invert(16%) sepia(17%) saturate(743%) hue-rotate(155deg) brightness(92%) contrast(89%);
}
.icon-done::before {
  content: "";
  background-image: url("./assets/icons/icon-done.svg");
  background-repeat: no-repeat;
  filter: invert(16%) sepia(17%) saturate(743%) hue-rotate(155deg) brightness(92%) contrast(89%);
}
.icon-slope::before {
  content: "";
  background-image: url("./assets/icons/icon-slope.svg");
  background-repeat: no-repeat;
  filter: invert(16%) sepia(17%) saturate(743%) hue-rotate(155deg) brightness(92%) contrast(89%);
}
.icon-location::before {
  content: "";
  background-image: url("./assets/icons/icon-location.svg");
  background-repeat: no-repeat;
  filter: invert(16%) sepia(17%) saturate(743%) hue-rotate(155deg) brightness(92%) contrast(89%);
}
.icon-notification::before {
  content: "";
  background-image: url("./assets/icons/icon-notification.svg");
  background-repeat: no-repeat;
  filter: invert(16%) sepia(17%) saturate(743%) hue-rotate(155deg) brightness(92%) contrast(89%);
}
// .icon-example::before {
//   content: "";
//   background-image: url("./assets/icons/icon-example.svg");
//   background-repeat: no-repeat;
//   filter: invert(16%) sepia(17%) saturate(743%) hue-rotate(155deg) brightness(92%) contrast(89%);
// }
</style>
