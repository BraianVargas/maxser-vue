<script> 
  var myDate = new Date()
    var hours = myDate.getHours()
    var minutes = myDate.getMinutes()
    var seconds = myDate.getSeconds()
    var day = myDate.getDay()
    
    if (hours < 10) hours = 0 + hours;
    if (minutes < 10) minutes = "0" + minutes;
    if (seconds < 10) seconds = "0" + seconds;
    
    var open = false
    
    var horaActual = hours + ':' + minutes 
    var horaActualWithSecs = hours + ':' + minutes + ':' + seconds

    if (day != 0){
        if(day == 6){
            if ((hour < 10) || (hour > 14)){
                open = false
            }else{
                open = true
            }
        }else{
            if((hours > 9) || (hours < 21)){
                open = true
            }else{
                open = false
            }
        }
    }else{
        open = false
    }
  console.log(open)



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
      return { 
        productsArray,
        open, 
        horaActualWithSecs 
      }
    },
    methods: {
      showTime(){
        return horaActual
      },
      getScreenRes(){
          return window.screen.width>=800?true:false
      },
      getScreenRes(){
        return screen.width>=700?true:false
      }
    }
  }
</script>

<template>
  <div class="container-fluid bg-black p-5">
      <div class="container pt-4 pb-4">
          <div class="row">
              <div class="col-12 col-md-3">
                  <p id="hour_title" class="fs-4 text-white text-center">Hora Actual</p>
                  <p id="actual_hour" class="fs-4 text-white text-center"> {{showTime()}} hs</p>
              </div>
              <div class="col-12 col-md-3">
                  <p id="hour_title" class="fs-4 text-white text-center">Hora de apertura</p>
                  <p id="hour_content" class="fs-4 text-white text-center">09:00 hs</p>
              </div>
              <div class="col-12 col-md-3">
                  <p id="hour_title" class="fs-4 text-white text-center">Hora de cierre</p>
                  <p id="hour_content" class="fs-4 text-white text-center">21:00 hs</p>
              </div>
              <div class="col-12 col-md-3">
                  <div>
                      <img v-if="open==true" src="src/assets/images/open.svg" class="m-auto d-flex" type="svg" alt="" srcset="" style="width:150px;">
                      <img v-if="open==false" src="src/assets/images/close.svg" class="m-auto d-flex" type="svg" alt="" srcset="" style="width:150px;">
                  </div>
              </div>
          </div>
      </div>
  </div>







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
                <a target="_blank" v-bind:href="producto.link" class="btn btn-mas p-2 ">Más info...</a>
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
                <a target="_blank" v-bind:href="producto.link" class="btn btn-mas p-2 ">Más info...</a>
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





  <div class="banner-grid">
    <div class="banner-item large" id="maxsoft">
         <img src="../assets/images/maxsoft/logo.webp" alt="" srcset="" class="large" style="width: 80%;">
    </div>
    <div class="banner-item small" id="ubication">
         <a target="_blank" href="https://www.google.com.ar/maps/place/MAXSER/@-31.5710231,-68.5314988,17z/data=!3m1!4b1!4m5!3m4!1s0x96813ff95ca35993:0x178904cc7e8269fd!8m2!3d-31.5710277!4d-68.5293101">
              <img src="../assets/images/pin-ubication.webp" alt="" srcset="" class="large" style="width: 20%;">
              <h3 class="text-white fw-bolder text-center">¿Donde Estamos?</h3>
         </a>
    </div>
    <div class="banner-item small" id="about-us">
         <router-link to="/about">
              <img src="../assets/images/info.webp" alt="" srcset="" class="large" style="width: 30%;">
              <h3 class="text-white fw-bolder text-center">¿Quienes Somos?</h3>
         </router-link>
    </div>
    <div class="banner-item large" id="contact">
         <img src="../assets/images/maxsoft/logo.webp" alt="" srcset="" class="large" style="width: 80%;">
    </div>
    <div class="banner-item large" id="maxsoft">
         <img src="../assets/images/maxsoft/logo.webp" alt="" srcset="" class="large" style="width: 80%;">
    </div>
</div>


</template>

<style>
  #hour_title{
    font-family: 'Courier New', Courier, monospace;
  }




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
  








  .banner-grid {
    display: flex;
    flex-wrap: wrap;
}

.banner-item {
    box-shadow: 10px 10px 16px -11px rgba(0,0,0,0.75);
    border-radius: 15px;
    flex: 1 0 calc(33.33% - 20px);
    margin: 10px;
    background-color: lightgray;
    text-align: center;
    padding: 20px;
}

.large {
    flex: 1 0 calc(66.66% - 20px);
}

.small {
    flex: 1 0 calc(33.33% - 20px);
}

@media (max-width: 768px) {
    .banner-item {
         flex: 1 0 calc(50% - 20px);
    }

    .large {
         flex: 1 0 calc(100% - 20px);
    }

    .small {
         flex: 1 0 calc(50% - 20px);
    }
}


#maxsoft{
    background-image: url(../assets/images/maxsoft/fondo-maxsoft.webp);
    background-size: cover;
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
}
#ubication{
    background-image: linear-gradient(rgba(8, 7, 7, 0.589), rgba(0, 0, 0, 0.801)),url(../assets/images/fondo-maps.webp);
    background-size: cover;
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
}
#about-us{
    background-image: linear-gradient(rgba(0, 0, 0, 0.589), rgba(0, 0, 0, 0.527)), url(../assets/images/about.webp);
    background-size: cover;
    background-attachment: fixed ;
    background-position: center;
    background-repeat: no-repeat;
}
#contact{
    background-image: linear-gradient(rgba(0, 0, 0, 0.589), rgba(0, 0, 0, 0.527)), url(../assets/images/contact.webp);
    background-size: cover;
    background-attachment: fixed ;
    background-position: center;
    background-repeat: no-repeat;
    background-clip: calc(100%-20%);
}


</style>