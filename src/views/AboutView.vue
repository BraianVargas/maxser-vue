<script>
  export default {
    data() {
      const teamArray = [
        {
          name: "Mauro",
          rol: "Administración",
          img_src: "src/assets/images/team/MAURO.png"
        },
        {
          name: "José",
          rol: "Asesor PyMES",
          img_src: "src/assets/images/team/JOSE.png"
        },
        {
          name: "Iván",
          rol: "Ventas - Marketing",
          img_src: "src/assets/images/team/IVAN.png"
        },
        {
          name: "Ignacio",
          rol: " Ventas - Marketing",
          img_src: "src/assets/images/team/IGNACIO.png"
        },
        {
          name: "Luis",
          rol: "Ventas - Servicio Técnico",
          img_src: "src/assets/images/team/LUIS.png"
        }
      ]

      const premiosArray = [
        {
          title:"Premio Mercurio de Oro 2018-2019",
          slogan:"Hace 50 años atrás se creó este prestigioso premio, que año a año distingue a las mejores y más prestigiosas empresas y comercios de San Juan.",
          subtitle:"Reconocimiento a la mejor asesoría y comercialización de equipos tecnológicos.",
          picture1:"src/assets/images/eventos/mercurio_1.png",
          picture2:"src/assets/images/eventos/mercurio_2.png"
        },
        // {
        //   title:"Premio Mercurio de Oro 2020-2023",
        //   slogan:"Hace 50 años atrás se creó este prestigioso premio, que año a año distingue a las mejores y más prestigiosas empresas y comercios de San Juan.",
        //   subtitle:"Reconocimiento a la mejor asesoría y comercialización de equipos tecnológicos.",
        //   picture1:"src/assets/images/eventos/mercurio_1.png",
        //   picture2:"src/assets/images/eventos/mercurio_2.png"
        // },
        {
          title:"Premio Mercedario",
          slogan:"El premio de mayor trayectoria a nivel nacional, entregado en forma ininterrumpida desde 1968 a las empresas más populares para los sanjuaninos.",
          subtitle:"Reconocimiento a la mejor asistencia técnica profesional de San Juan.",
          picture1:"src/assets/images/eventos/mercedario_1.png",
          picture2:"src/assets/images/eventos/mercedario_2.png"
        },
      ]

      const imageNames = Array.from({length: 20}, (value, index) => `${index+1}`)

      const groupsOfThree = [];
      for (let i = 0; i < teamArray.length; i += 3) {
        groupsOfThree.push(teamArray.slice(i, i + 3));
      }
      return {
        teamArray,
        imageNames,
        premiosArray
      }
    },
    mounted() {
      for (let i = 0; i < 20; i++) {
        this.range.push({ id: i, name: `Item ${i+1}` })
      }
      const carousel = $(this.$refs.carousel);
      carousel.on('slid.bs.carousel', () => {
        this.carouselReady = true;
      });
      carousel.carousel();
    },
    methods: {
      showTime() {
        return horaActual
      },
      getScreenRes() {
        return window.screen.width >= 800 ? true : false
      }
    }
  }
</script>

<template>
  <section id="about_us">
    <h2 class="m-auto text-center p-3 bolder fs-1">Sobre Nosotros</h2>
    <div class="container m-auto p-5">
      <div class="row">
        <div class="col-12 col-md-6 p-2 m-auto text-left">
          <p class="w-80">
            Somos una empresa Sanjuanina especializada en el área tecnológica con mas de 15 años en el mercado.
            Conformada por técnicos y asesores especializados en diferentes sectores de servicio, capacitados para
            proveer soluciones eficientes y de primer nivel.
            <br>
            Nos dedicamos principalmente a ofrecer un excelente servicio al cliente, institución u organización,
            brindando calidad en los resultados de nuestros trabajos y equipamientos tecnológicos. Estamos comprometidos
            con los clientes, las normas legales y el medio ambiente, garantizando un oportuno cumplimiento.
          </p>
        </div>
        <div id="card" class="col-12 col-md-6 text-center bg-white">
          <i id="quote" class="bi bi-quote"></i>
          <h3 class="text-center bolder">
            “Un equipo exitoso late con un solo corazón.”
          </h3>
        </div>
      </div>
    </div>
    <!-- carrousel of Team -->



    

    <!-- <section>
      <div id="team-carousel" class="carousel slide" data-bs-ride="carousel">
        <div class="carousel-inner">
          <div class="carousel-item" v-for="i in 10" :class="{active:i=1}">
            <div class="col-md-4 d-inline-block" v-for="(person,index) in teamArray" >
              <p class="">{{person.name}}</p>
            </div>
          </div>
        </div>
        <button class="carousel-control-prev" type="button" data-bs-target="#team-carousel" data-bs-slide="prev">
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#team-carousel" data-bs-slide="next">
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </section> -->




<!-- ------------------------------------------------------------------------------------------------------ -->


    <!-- <section id="carrousel_people" class="p-4">
      <div id="carouselExampleAutoplaying" class="carousel slide" data-bs-ride="carousel">
        <div class="carousel-inner" v-if="getScreenRes() == true">
          <div class="carousel-item" v-for="(group, index) in groupsOfThree" :key="index" v-bind:class="{active:index=1}">
            <div class=" item-card col-12 col-md-4 d-inline-block" v-for="(person, index) in group" :key="index"> 
              <img class="card-img-top d-flex m-auto" v-bind:src="person.img_src" alt="card image cap" style="width: 200px; height: 200px;">
              <div class="bg-white text-black p-2 text-center">
                <p class="bolder">
                  {{ person.name }}
                  <br>
                  {{ person.rol }}
                </p>
              </div>
            </div>
          </div>
        </div>
        <div class="carousel-inner" v-else>
            <div class="carousel-item" v-for="(person, index) in teamArray" :key="index" v-bind:class="{active:person.id != 1}"> 
              <div class="item-card">
                <img class="card-img-top d-flex m-auto" v-bind:src="person.img_src" alt="card image cap" style="width: 200px; height: 200px;">
                <div class="bg-white text-black p-2 text-center">
                  <p class="bolder">
                    {{ person.name }}
                    <br>
                    {{ person.rol }}
                  </p>
                </div>
              </div>
            </div>
        </div>
        <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleAutoplaying"
          data-bs-slide="prev">
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleAutoplaying"
          data-bs-slide="next">
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </section> -->
    <!-- End carousel of Team -->
  </section>
  
  <section id="portfolio">
    <div class="container pb-5 pt-5 row m-auto">
      <div class="text-container col-12 col-md-4">
        <h2 class="text-white d-flex m-auto bolder" >
          Nuestros Clientes
        </h2>
        <br>
        <p>
          Desde nuestro comienzo hemos trabajado para que la calidad de nuestros servicios este presente en cada detalle. Seguimos ofreciendo el máximo servicio en tecnología proporcionando atención personalizada profesional, horarios flexibles y la confianza que necesitan nuestro clientes. Muchas personas, PyMes, organizaciones e instituciones, siguen eligiendo MAXSER. Comprometidos tecnológicamente para conectar a San Juan con el mundo.
          <br>
          Gracias a todos por confiar en nosotros.
        </p>
      </div>
      <div class="img-container col-12 col-md-7 bg-white">
        <div class="p-3 row m-auto">
          <div class="col-12 d-flex col-md-4 m-auto" v-for="image in imageNames">
            <img class="container p-2" :src="`src/assets/images/empresas/${image}.png`" :alt="imageName">
          </div>
        </div>
      </div>
    </div>
  </section>
  <section id="reconocimientos">
    <div class="bg-black d-block m-auto">
      <h1 class="text-white m-auto text-center p-4">Reconocimientos</h1>
      <div class="row d-flex m-auto mt-4 p-2" style="border:2px solid #FFFF; border-radius: 15px"  v-for="premio in premiosArray">
        <div class="col-12 col-md-4 p-2" >
          <div class="card">
            <img v-bind:src="premio.picture1" alt="" class="card-img-top">
            <div class="card-body">
              <p class="card-title text-black">
                {{premio.title}}
              </p>
              <p class="card-text">
                {{premio.subtitle}}
              </p>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-8 p-2 container">
          <img v-bind:src="premio.picture2" class="w-100" alt="" style="max-width:800px">
        </div>
        <hr/>
      </div>
    </div>
  </section>

</template>

<style>
  .bolder {
    font-weight: bold;
  }
  .item-card{
    border-radius: 0 0 18px 18px ;
  }

  #card {
    overflow: hidden;
    border-radius: 15px;
    color: black;
    
  }

  #quote {
    color: #FE5000;
    font-size: 80px;
  }
  #about_us{
    background-image: linear-gradient(rgba(8, 7, 7, 0.589), rgba(0, 0, 0, 0.801)), url(../assets/images/towers.webp);
    color: white;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
  }
  

  #portfolio{
    background-color: gray;
  }
  .img-container{
    border-radius: 17px;
  }
  .img-container img{
    max-width: 120px;
  }

  @media (min-width: 1024px) {}
</style>