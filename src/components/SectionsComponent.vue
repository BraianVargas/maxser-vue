<script>
     export default {

     }
</script>
<template lang="">
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
<style lang="css">
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