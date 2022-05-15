<template>
  <!--Menu-->
  <div class="home">
    <header class="main-header  l-section">
      <div class="wrapper  l-container">
        <img class="logo" :src="require(`@/assets/images/oseanfriend.png`)">
        <nav class="header__nav">
          <ul class="header__menu">
            <li><a href="#">Home</a></li>
            <li><a href="#">Dashboard</a></li>
            <li><a href="#">About us</a></li>
            <li><a href="#">¿Cómo funciona nuestro sistema?</a></li>
          </ul>
        </nav>
      </div>
    </header>
    <article>
      <!--Priemra parte-->
      <section class="banner">
        <h1>Osean Friend</h1>
        <h2>Organización para la preservación de las especies marinas </h2>
        <p>Hacer el cambio está al alcance de tus manos</p>
      </section>
      <!--About Us-->
      <section>
        <h2>About us</h2>
        <p>Somos un grupo de biólogos que nos unimos con la comunidad para hacer el cambio hoy.</p>
        <p>Gracias a los reportes de la comunidad y a las alertas en tiempo real de nuestro Osean Friend estamos
          salvando vidas marinas todos los días.</p>
        <p>A una notificación de hacer el cambio </p>
      </section>
      <!--Como funcionamos-->
      <section>
        <h2>¿Cómo funciona nuestro sistema?</h2>
        <div class="contairner">
          <div class="card">
            <figure><img :src="require(`@/assets/images/robot.jpg`)"></figure>
            <div class="card__contenido">
              <h3>Conoce a nuestro Osean Friend </h3>
              <p>Osean Friend es un robot que navega por el mar buscando espacies que se encuentran en alguna situación
                de
                peligro. </p>
            </div>
            <br>
            <div>
              <figure><img :src="require(`@/assets/images/biologos.jpg`)"></figure>
              <div class="card__contenido">
                <h3>Equipo de biólogos </h3>
                <p>Cuando Osean Friend encuentra un espécimen en situación de peligro un grupo especializado de biólogos
                  recibe
                  la alerta y así el equipo evalúa la situación para poder accionar de la manera más efectiva para
                  salvar
                  la
                  vida del animal.</p>
              </div>
            </div>
            <h3>Tú </h3>
            <p>Tú como contribuyente nos puedes ayudar de dos formas:</p>
            <div>
              <figure><img :src="require(`@/assets/images/tortuga_bolsa.jpg`)"></figure>
              <div class="card__contenido">
                <h3>Haz un reporte</h3>
                <p>Si encuentras un animal marino en situación de peligro podrás ayudar haciendo un reporte describiendo
                  la
                  situación en la que se encuentra dicho espécimen, adjuntando una imagen lo mas clara posible y la
                  ubicación de
                  donde se encuentra.</p>
              </div>
            </div>
            <div>
              <figure><img :src="require(`@/assets/images/tortugas_contenido2.jpg`)"></figure>
              <div class="card__contenido">
                <h3>Ensúciate las manos</h3>
                <p>Si eastas subscrito a nuestro sitio y estás cerca de un lugar donde
                  haya un reporte, nosotros te mandamos la alerta a ti con instrucciones de que hacer, no te preocupes
                  nosotros
                  anticipadamente evaluamos si una persona común puede hacer la tarea.</p>
              </div>
            </div>
          </div>
        </div>
      </section>
      <!--Formulario para alerta-->
      <section>
        <h2>¿Quiere hacer un reporte?</h2>
        <p>Agradecemos tus ganas de contribuir y ayudar a hacer el cambio. Confiamos en ti la veracidad de tu
          información compartida</p>
        <p>Recuerda leer aquí como funciona nuestro sistema para hacer tu reporte correctamente</p>
        <form action="/signup" method="post">
          <p>
            <label>Title</label><br>
          </p>
          <p>
            <label>Nombre de la especie del animan el peligro</label><br>
            <input type="text" name="name" placeholder="Tortuga">
          </p>
          <p>
            <label>Describe la situación </label><br>
            <textarea description="description"
              placeholder="La tortuga tiene una bolsa de basura alredor de su cuello y no se puede mover con facilidad"></textarea>
          </p>
          <p>
            <button class="button">Subir una foto</button>
            <button class="button">Agregar ubicación</button>
          </p>
        </form>
        <p>juntos hacemos en cambio</p>
      </section>
    </article>
    <!--footer-->
    <footer>
      <p>Osean Friend 2022</p>
    </footer>
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  name: 'HomeView'
}
</script>

<style scopde lang="scss">
header {
  padding: 0px 10vw;
  height: 100px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 100;
  position: fixed;
  top: 0;
  width: 100%;
  background-color: rgba(206, 224, 224, 0.9);
  ;
}

.header__nav {
  width: 67%;
}

.header__menu {
  display: flex;
  margin: 0;
  padding: 0;
  list-style: none;
  justify-content: space-evenly;
}

.logo {
  width: 100px;
}
.contairner{
  width: 100%;
  display: flex;
  max-width: 500px;
}

.card {
  width: 100%;
  margin: 20px;
  border-radius: 6px;
  overflow: hidden;
  background-color: #fff;
  box-shadow: 0px 1px 10px rgba(0, 0, 0, 0.2);
  flex-direction: row;
}
.card figure {
  width: 400px;
}

footer {
  background-color: var(--color-second);
  padding: 50px 10vw;
  width: 100%;
}
</style>
