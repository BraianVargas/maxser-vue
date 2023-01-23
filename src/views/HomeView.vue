<script> 
  export default{
    data(){
      const productsArray = [
      {
        id:1,
        img_src:"src/assets/images/productos/celulares.png",
        title:"Celulares",
        content:"Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sint ab vel, voluptatum ullam, consequatur rem beatae delectus nam officia harum repellendus. At harum fugiat qui eaque dolorum illo totam corrupti."
      },
      {
        id:2,
        img_src:"src/assets/images/productos/notebooks.png",
        title:"Notebooks",
        content:"Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sint ab vel, voluptatum ullam, consequatur rem beatae delectus nam officia harum repellendus. At harum fugiat qui eaque dolorum illo totam corrupti."
      },
      {
        id:3,
        img_src:"src/assets/images/productos/accesorios.png",
        title:"Accesorios Gamer",
        content:"Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sint ab vel, voluptatum ullam, consequatur rem beatae delectus nam officia harum repellendus. At harum fugiat qui eaque dolorum illo totam corrupti."
      },
      {
        id:4,
        img_src:"src/assets/images/productos/seguridad.png",
        title:"Seguridad",
        content:"Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sint ab vel, voluptatum ullam, consequatur rem beatae delectus nam officia harum repellendus. At harum fugiat qui eaque dolorum illo totam corrupti."
      }
    ]
    return { productsArray }
    }
  }

</script>

<template>
  <div class="container-fluid ">
    <ul v-for="producto in productsArray" :key="producto.id">
      <li id="product_item" v-if="(producto.id % 2) ==0">
        <div class="d-flex justify-content-center">
          <div class="row" style="max-width:800px;">
            <p class="col-12" style="max-width: 550px;">
              <b class="fs-2"> {{ producto.title }} </b>
              <br>
              {{ producto.content}}
            </p>
          </div>
          <div class="row">
            <img v-bind:src="producto.img_src" id="img_prod" alt="" srcset="">
          </div>
        </div>
      </li>
      <li id="product_item" v-else>
        <div class="d-flex justify-content-center">
          <div class="row">
            <img v-bind:src="producto.img_src" id="img_prod" alt="" srcset="">
          </div>
          <div class="row" style="max-width:800px;">
            <p class="col-12" style="max-width: 550px;">
              <b class="fs-2"> {{ producto.title }} </b>
              <br>
              {{ producto.content}}
            </p>
          </div>
        </div>
      </li>
    </ul>
  </div>

</template>

<style>
  ul{
    list-style: none;
    width: auto;
    margin: 1em;
    justify-content: center;
  }
  #product_item{
    padding-top: 1cm;
  }
  #img_prod{
    max-width: 550px;
    padding: 0;
    filter: drop-shadow(0 8px 10px  rgba(0, 0, 0, 0.815));
  }
</style>