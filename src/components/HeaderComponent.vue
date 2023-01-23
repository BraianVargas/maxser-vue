<template lang="">
    <nav class="navbar navbar-expand-lg bg-black text-white">
        <div class="container-fluid">
            <a class="navbar-brand" href="/">
                <img src="../assets/images/logo.webp" style="width:80px">
            </a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup"
                aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="d-flex justify-content-end scollapse navbar-collapse" id="navbarNavAltMarkup">
                <div class="navbar-nav">
                    <RouterLink class="nav-link p-2 text-white" to="/">
                        <i class="bi bi-house"></i> Inicio
                    </RouterLink>
                    
                    <RouterLink class="nav-link p-2 text-white" to="/about">
                        <i class="bi bi-info-circle"></i> ¿Quienes Somos?
                    </RouterLink>
                    
                    <div class="dropdown p-d">
                        <a class="dropdown-toggle nav-link text-white" type="button" data-bs-toggle="dropdown" aria-expanded="false">
                            <i class="bi bi-whatsapp"></i> Whatsapp
                        </a>
                        <ul class="dropdown-menu">
                            <li><a class="dropdown-item" href="#">Ventas Online</a></li>
                            <li><a class="dropdown-item" href="#">Servicio Técnico</a></li>
                            <li><a class="dropdown-item" href="#">Empresas</a></li>
                        </ul>
                    </div>
                    
                    <RouterLink class="nav-link p-2 text-white" to="/about">
                        <i class="bi bi-calendar-event"></i> Eventos
                    </RouterLink>

                    <a href="http://www.maxserstore.com.ar" class="nav-link btn-tienda p-2 text-white" target="_blank"> <i class="bi bi-shop-window"></i> Maxser Store </a>
                    
                </div>
            </div>
        </div>
    </nav>
</template>

<script>
    export default {

    }
</script>

<style lang="css">
    @import '../assets/base.css';

    a{
        text-decoration: none;
    }

    .btn-tienda{
        border-radius: 150px;
        border: solid 2px #fe9000;
        box-shadow: 0px 0px 30px #FE9000d3;
        background-color: #e9650e;
    }

</style>