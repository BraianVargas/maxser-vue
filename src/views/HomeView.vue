<script> 
  import HorarioComponent from '../components/HorarioComponent.vue';
  export default{
    data(){
      const productsArray = [
      {
        id:1,
        img_src:"src/assets/images/productos/celulares.png",
        title:"Smartphones",
        slogan:"No dejes de estar conectado",
        content:"Encontrá el Smartphone que necesitas para tu dia a dia y elegi el que se adapte mejor a vos para estar más conectado que nunca!",
        link:"https://maxserstore.com.ar/conectividad/smartphone1/"
        
      },
      {
        id:2,
        img_src:"src/assets/images/productos/notebooks.png",
        title:"Notebooks",
        slogan:"Llevá tu mundo con vos",
        content:"Descubrí en MAXSER la notebook ideal para tus exigencias. Para juegos, trabajo o estudio, la notebook que necesitas está aqui.",
        link:"https://maxserstore.com.ar/notebook/"
      },
      {
        id:3,
        img_src:"src/assets/images/productos/accesorios.png",
        title:"Accesorios Gamer",
        slogan:"",
        content:"Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sint ab vel, voluptatum ullam, consequatur rem beatae delectus nam officia harum repellendus. At harum fugiat qui eaque dolorum illo totam corrupti.",
        link:""
      },
      {
        id:4,
        img_src:"src/assets/images/productos/seguridad.png",
        title:"Seguridad",
        slogan:"",
        content:"Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sint ab vel, voluptatum ullam, consequatur rem beatae delectus nam officia harum repellendus. At harum fugiat qui eaque dolorum illo totam corrupti.",
        link:""
      }
    ]
    return { productsArray }
    },
    methods: {
      getScreenRes(){
        return screen.width>=800?true:false
      }
    }
  }

</script>

<template>
  <HorarioComponent/>
  <div class="container-fluid p-3 mt-2 mb-2">
    <p class="text-decoration-none text-black fw-bolder lead display-5 m-auto text-center">
      <strong>Productos</strong>
    </p>

    <div v-if="getScreenRes()"> <!-- Si es formato pc carga esta sección-->
      <ul v-for="producto in productsArray" :key="producto.id">
        <li id="product_item" v-if="(producto.id % 2) ==0">
          <div class="container" style="max-width:900px;">
            <div class="row">
              <div class="col-12 col-md-7">
                <img v-bind:src="producto.img_src" id="img_prod" alt="" srcset="">
              </div>
              <div class="col-12 col-md-5">
                <b class="fs-2"> {{ producto.title }} </b>
                <br>
                <cite class="fs-6 text-black">"{{producto.slogan}}"</cite>
                <br>
                <br>
                {{ producto.content}}
                <br><br>
                <a v-bind:href="producto.link" class="btn btn-mas p-2 ">Más info...</a>
              </div>
            </div>
          </div>
        </li>
        <li id="product_item" v-else>
          <div class="container" style="max-width:800px;">
            <div class="row">
              <div class="col-12 col-md-5">
                <b class="fs-2"> {{ producto.title }} </b>
                <br>
                <cite class="fs-6 text-black">"{{producto.slogan}}"</cite>
                <br>
                <br>
                {{ producto.content}}
                <br><br>
                <a v-bind:href="producto.link" class="btn btn-mas p-2 ">Más info...</a>
              </div>
              <div class="col-12 col-md-7">
                <img v-bind:src="producto.img_src" id="img_prod" alt="" srcset="">
              </div>
            </div>
          </div>
        </li>
      </ul>
    </div>
    <div v-else> <!-- Si es formato celular o tablet carga esta sección-->
      <ul v-for="producto in productsArray" :key="producto.id">
        <li id="product_item" class="mb-4" style="heigth:200px;">
          <div class="container" style="max-width: 450px; box-shadow: 1px -2px 17px 1px rgba(0,0,0,0.75); border-radius: 15px;">
            <div class="row">
              <b class="fs-2 text-center pt-2 mt-2"> {{ producto.title }} </b>
              <cite class="fs-6 text-black">"{{producto.slogan}}"</cite>
              <br>
              <div class="col-12">
                <br>
                {{ producto.content}}
                <br><br>
                <div class="">
                  <img v-bind:src="producto.img_src" id="img_prod" alt="" style="width:300px; margin:auto;" >
                </div>
                <br>
                <div class="d-flex justify-content-center">
                  <a v-bind:href="producto.link" class="btn btn-mas p-2 mb-4 d-flex justify-content-center">Más info</a>
                </div>
              </div>
            </div>
          </div>
        </li>
      </ul>
    </div>
    <br><br>
    <a href="https://maxserstore.com.ar/productos/" class="m-auto d-flex justify-content-center text-black text-decoration-underline fw-bolder btn-mas btn" target="_blank" rel="noopener noreferrer" style="width: 200px; color:#1783af;">
      Más productos...
    </a>
    <br><br>
  </div>

</template>

<style>
  @font-face {
    font-family: "Rubik";
    src: url("../assets/fonts/rubik.ttf");
  }
  ul{
    list-style: none;
    padding: 1em;
  }
  #product_item{
    height: 500;
  }
  #img_prod{
    min-width: 100px;
    max-width: 450px;
    max-height: 350px;
    padding: 0;
    filter: drop-shadow(0 8px 10px  rgba(0, 0, 0, 0.815));
  }
  #product_content{
    font-family: 'Rubik';
    font-weight: 500;
  }
  .btn-mas{
    background: #fe5000c3;
    box-shadow: none;
    text-shadow: none;
    font-weight: bold;
    border-radius: 100em;
    width: 150px;
  }
  .btn-mas:hover{
    background: #aef1ff;
    box-shadow: 10px 10px 43px 0px rgba(0,0,0,0.75);
  }
  

</style>