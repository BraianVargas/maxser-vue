<script>
  export default {
    data() {
      const teamArray = [
        [{
            id: 1,
            name: "Mauro",
            rol: "Administración",
            img_src: "src/assets/images/team/MAURO.png"
          },
          {
            id: 2,
            name: "José",
            rol: "Asesor PyMES",
            img_src: "src/assets/images/team/JOSE.png"
          },
          {
            id: 3,
            name: "Iván",
            rol: "Ventas - Marketing",
            img_src: "src/assets/images/team/IVAN.png"
          }
        ],
        [{
            id: 4,
            name: "Ignacio",
            rol: " Ventas - Marketing",
            img_src: "src/assets/images/team/IGNACIO.png"
          },
          {
            id: 5,
            name: "Luis",
            rol: "Ventas - Servicio Técnico",
            img_src: "src/assets/images/team/LUIS.png"
          }
        ]
      ]
      return {
        teamArray
      }
    },
    methods: {
      showTime() {
        return horaActual
      },
      getScreenRes() {
        return window.screen.width >= 800 ? true : false
      },
      getScreenRes() {
        return screen.width >= 700 ? true : false
      }
    }
  }
</script>

<template>
  <section id="about_us" class="">
    <h2 class="m-auto text-center p-3 bolder fs-1">Sobre Nosotros</h2>
    <div class="container m-auto p-3">
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
    <section id="carrousel_people">
      <div id="carouselExampleAutoplaying" class="carousel slide" data-bs-ride="carousel">
        <div class="carousel-inner" v-for="(group, index) in teamArray" :key="index">
          <div class="carousel-item row" v-bind:class="{ active: index = 1}">
            <div class="col-md-4" v-for="(person, index) in group" :key="index">
              <div class="p-2 col-md-4 m-auto ">
                <img class="card-img-top m-auto" v-bind:src="person.img_src" alt="card image cap"
                  style="width: 200px; height: 200px;">
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
    </section>
    <!-- End carousel of Team -->
  </section>

</template>

<style>
  .bolder {
    font-weight: bold;
  }

  #card {
    border-radius: 15px;
    color: black;
  }

  #quote {
    color: #FE5000;
    font-size: 80px;
  }

  #about_us {
    color: white;

    background-image: linear-gradient(rgba(8, 7, 7, 0.589), rgba(0, 0, 0, 0.801)), url(../assets/images/towers.webp);
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
  }

  @media (min-width: 1024px) {}
</style>