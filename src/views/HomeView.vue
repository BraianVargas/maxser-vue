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
    <a target="_blank" href="https://maxser.com.ar/enterprise.html">
        <img src="../assets/images/maxsoft/logo.webp" alt="" srcset="" class="large" style="width: 80%;">
      </a>
  </div>
  <div class="banner-item small" id="ubication">
        <a target="_blank" href="https://www.google.com.ar/maps/place/MAXSER/@-31.5710231,-68.5314988,17z/data=!3m1!4b1!4m5!3m4!1s0x96813ff95ca35993:0x178904cc7e8269fd!8m2!3d-31.5710277!4d-68.5293101">
            <img src="../assets/images/pin-ubication.webp" alt="" srcset="" class="large" style="width: 20%;">
            <h3 class="text-white fw-bolder text-center">¿Donde Estamos?</h3>
        </a>
  </div>
  <div class="banner-item small" id="about-us">
    <a target="_blank" href="https://maxser.com.ar/about-us.html">
      <img src="../assets/images/info.webp" alt="" srcset="" class="large" style="width: 30%;">
      <h3 class="text-white fw-bolder text-center">Sobre Nosotros</h3>
    </a>
  </div>
  <div class="banner-item large" id="maxserstore">
    <a target="_blank" href="https://www.maxserstore.com.ar">
      <img src="../assets/images/maxserstore-logo.webp" alt="" srcset="" class="large" style="width:70%; align-item:center;">
  </a>
  </div>
  <div class="banner-item large" id="events">
    <a href="https://maxser.com.ar/about-us.html#premios" target="_blank">
      <h1 class="text-white fw-bolder text-center p-5">Premios, eventos y reconocimientos</h1>
    </a>
  </div>
</div>

<div class="banner-grid mt-5 pt-5 mb-5 pb-5" style="max-width:800px; margin:auto;">
  <div class="banner-item small">
    <svg xmlns="http://www.w3.org/2000/svg" width="60" height="60" fill="currentColor" class="bi bi-whatsapp" viewBox="0 0 16 16">
      <path d="M13.601 2.326A7.854 7.854 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.057 3.965L0 16l4.204-1.102a7.933 7.933 0 0 0 3.79.965h.004c4.368 0 7.926-3.558 7.93-7.93A7.898 7.898 0 0 0 13.6 2.326zM7.994 14.521a6.573 6.573 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.557 6.557 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592zm3.615-4.934c-.197-.099-1.17-.578-1.353-.646-.182-.065-.315-.099-.445.099-.133.197-.513.646-.627.775-.114.133-.232.148-.43.05-.197-.1-.836-.308-1.592-.985-.59-.525-.985-1.175-1.103-1.372-.114-.198-.011-.304.088-.403.087-.088.197-.232.296-.346.1-.114.133-.198.198-.33.065-.134.034-.248-.015-.347-.05-.099-.445-1.076-.612-1.47-.16-.389-.323-.335-.445-.34-.114-.007-.247-.007-.38-.007a.729.729 0 0 0-.529.247c-.182.198-.691.677-.691 1.654 0 .977.71 1.916.81 2.049.098.133 1.394 2.132 3.383 2.992.47.205.84.326 1.129.418.475.152.904.129 1.246.08.38-.058 1.171-.48 1.338-.943.164-.464.164-.86.114-.943-.049-.084-.182-.133-.38-.232z"/>
    </svg>
    <br>
    <a href="" class="btn btn-whatsapp">Contactar</a>
  </div>
  <div class="banner-item small">
    <svg xmlns="http://www.w3.org/2000/svg" width="60" height="60" fill="currentColor" class="bi bi-building" viewBox="0 0 16 16">
      <path d="M4 2.5a.5.5 0 0 1 .5-.5h1a.5.5 0 0 1 .5.5v1a.5.5 0 0 1-.5.5h-1a.5.5 0 0 1-.5-.5v-1Zm3 0a.5.5 0 0 1 .5-.5h1a.5.5 0 0 1 .5.5v1a.5.5 0 0 1-.5.5h-1a.5.5 0 0 1-.5-.5v-1Zm3.5-.5a.5.5 0 0 0-.5.5v1a.5.5 0 0 0 .5.5h1a.5.5 0 0 0 .5-.5v-1a.5.5 0 0 0-.5-.5h-1ZM4 5.5a.5.5 0 0 1 .5-.5h1a.5.5 0 0 1 .5.5v1a.5.5 0 0 1-.5.5h-1a.5.5 0 0 1-.5-.5v-1ZM7.5 5a.5.5 0 0 0-.5.5v1a.5.5 0 0 0 .5.5h1a.5.5 0 0 0 .5-.5v-1a.5.5 0 0 0-.5-.5h-1Zm2.5.5a.5.5 0 0 1 .5-.5h1a.5.5 0 0 1 .5.5v1a.5.5 0 0 1-.5.5h-1a.5.5 0 0 1-.5-.5v-1ZM4.5 8a.5.5 0 0 0-.5.5v1a.5.5 0 0 0 .5.5h1a.5.5 0 0 0 .5-.5v-1a.5.5 0 0 0-.5-.5h-1Zm2.5.5a.5.5 0 0 1 .5-.5h1a.5.5 0 0 1 .5.5v1a.5.5 0 0 1-.5.5h-1a.5.5 0 0 1-.5-.5v-1Zm3.5-.5a.5.5 0 0 0-.5.5v1a.5.5 0 0 0 .5.5h1a.5.5 0 0 0 .5-.5v-1a.5.5 0 0 0-.5-.5h-1Z"/>
      <path d="M2 1a1 1 0 0 1 1-1h10a1 1 0 0 1 1 1v14a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V1Zm11 0H3v14h3v-2.5a.5.5 0 0 1 .5-.5h3a.5.5 0 0 1 .5.5V15h3V1Z"/>
    </svg>
    <br>
    <a href="" class="btn btn-whatsapp">Contactar</a>
  </div>
  <div class="banner-item small">
    <svg xmlns="http://www.w3.org/2000/svg" width="60" height="60" fill="currentColor" class="bi bi-tools" viewBox="0 0 16 16">
      <path d="M1 0 0 1l2.2 3.081a1 1 0 0 0 .815.419h.07a1 1 0 0 1 .708.293l2.675 2.675-2.617 2.654A3.003 3.003 0 0 0 0 13a3 3 0 1 0 5.878-.851l2.654-2.617.968.968-.305.914a1 1 0 0 0 .242 1.023l3.27 3.27a.997.997 0 0 0 1.414 0l1.586-1.586a.997.997 0 0 0 0-1.414l-3.27-3.27a1 1 0 0 0-1.023-.242L10.5 9.5l-.96-.96 2.68-2.643A3.005 3.005 0 0 0 16 3c0-.269-.035-.53-.102-.777l-2.14 2.141L12 4l-.364-1.757L13.777.102a3 3 0 0 0-3.675 3.68L7.462 6.46 4.793 3.793a1 1 0 0 1-.293-.707v-.071a1 1 0 0 0-.419-.814L1 0Zm9.646 10.646a.5.5 0 0 1 .708 0l2.914 2.915a.5.5 0 0 1-.707.707l-2.915-2.914a.5.5 0 0 1 0-.708ZM3 11l.471.242.529.026.287.445.445.287.026.529L5 13l-.242.471-.026.529-.445.287-.287.445-.529.026L3 15l-.471-.242L2 14.732l-.287-.445L1.268 14l-.026-.529L1 13l.242-.471.026-.529.445-.287.287-.445.529-.026L3 11Z"/>
    </svg>
    <br>
    <a href="" class="btn btn-whatsapp">Contactar</a>
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
  box-shadow: 1px -2px 17px 1px rgba(0,0,0,0.75);
    border-radius: 15px;
    flex: 1 0 calc(33.33% - 20px);
    margin: 10px;
    background-color: rgb(255, 255, 255);
    text-align: center;
    padding: 20px;
}

.large {
    flex: 1 0 calc(66.66% - 20px);
}

.small {
    flex: 1 0 calc(33% - 20px);
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
#maxserstore{
    background-image: linear-gradient(rgba(8, 7, 7, 0.589), rgba(0, 0, 0, 0.801)),url(../assets/images/Store.webp);
    background-size: cover;
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
}
#events{
    background-image: linear-gradient(rgba(8, 7, 7, 0.589), rgba(0, 0, 0, 0.801)),url(../assets/images/events.webp);
    background-size: cover;
    background-attachment: fixed;
    background-position: bottom;
    background-repeat: no-repeat;
}

.btn-whatsapp{
  background-color: #07ce50;
  scrollbar-shadow-color: #075e54;
  border-radius: 15px;
  margin-top: 2em;
  color: white;
  box-shadow: inset 0 0 7px 2px #075e54;
  border: 5px white solid;
  outline: 1px black solid;
}
.btn-whatsapp:hover{
  background-color: white;
  border-radius: 15px;
  margin-top: 2em;
  color: black;
  box-shadow: 0 0 0 0;
  border: 5px #07ce50 solid;
  outline: 1px 075e54 solid;
}


</style>