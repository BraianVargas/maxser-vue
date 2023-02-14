<template lang="">
     <div>
          <div id="pie" class="bg-black p-5">
               <div class="container">
                    <div class="justify-content-center text-center">
                         <img src="../../src/assets/images/LOGO.webp" alt="" style="width: 150px; height: 92px;" srcset="">
                    </div>
               </div>
          </div>
          <section class="bottom-menu">
               <div class="d-flex align-items-center">
                    <ul class="col-12 text-center f-flex bg-black">
                         <li class="links">
                              <a target="_blank"
                                   href="https://drive.google.com/file/d/13YHCCOWZFtM72qM6PSIvw6BZAXiLikZ-/view">
                                   Terminos y Condiciones
                              </a>
                         </li>
                         <li class="links">
                              <a target="_blank"
                                   href="https://drive.google.com/file/d/13YHCCOWZFtM72qM6PSIvw6BZAXiLikZ-/view">
                                   Política de Garantía
                              </a>
                         </li>
                         <li class="links">
                              <a target="_blank"
                                   href="https://drive.google.com/file/d/13YHCCOWZFtM72qM6PSIvw6BZAXiLikZ-/view">
                                   Política de Trabajo
                              </a>
                         </li>
                         <li class="links">
                              <a href="#contacto">
                                   Contacto
                              </a>
                         </li>
                    </ul>
                    <div class="col-12 text-center">
                    </div>
               </div>
               <div class="row d-flex align-items-center">
                    <div class="col-12 text-center text-md-left">
                         <div>
                              <span class="copyright">© 2023 MAXSER - Todos los derechos reservados </span>
                              <br><br>
                         </div>
                    </div>
                    <div class="col-12 text-center text-md-end">
                         <a href="http://qr.afip.gob.ar/?qr=NrhR4fVjecn_U2p8ncSDsg,," target="_F960AFIPInfo"> <img
                                   class="m-auto" style="width: 50px; height: auto;" src="../../src/assets/images/DATAWEB.jpg"> </a>
                    </div>
               </div>

          </section>


          <div class="container-fluid bg-black">
               <div class="row text-end">
                    <a target="_blank" href="https://bricode-sj.web.app/"
                         style="text-decoration: none; color: #FFF; font-size: small;">
                         Desarrollado con ❤ por BriCode | <strong>Contactar</strong>
                    </a>
               </div>
               <br>
          </div>
     </div>
</template>

<script>
     export default {

     }
</script>
<style lang="css">
     .bottom-menu{
          box-sizing: border-box;
          display: block;
          background-color: #000;
          font-family: "Noto Sanz", sans-serif;
          font-size: 16px;
          line-height: 22px;
          padding: 26px;
          text-size-adjust: 100%;
     }
     .bottom-menu .links{
          box-sizing: border-box;
          display: block;
          font-family: sans-serif;
          font-size: 16px;
          list-style: none;
          color: white;
     }
     .links{
          box-sizing: border-box;
          display:  inline-block;
          font-family: sans-serif;
          font-size: 14px;
          line-height: 20px;
          list-style-type: none;
          text-align: center;
          text-size-adjust: 100%;
     }
     .links:last-child::after{
          content: "";
     }
     .links::after{
          content: "|";
          margin: 5px;
          color:white;
     }
     .links a{
          color: rgb(114, 114, 114);
     }
     .links a:hover{
          color:white;
          text-decoration: underline;
     }
     .copyright{
          color:white;
          text-align: center;
          font-size: 12px;
     }
</style>