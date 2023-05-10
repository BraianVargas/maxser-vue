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
            <div class="d-flex justify-content-end scollapse navbar-collapse" >
                <div class="navbar-nav navbar-sm-collapse  " id="navbarNavAltMarkup">
                    <a class="nav-link p-2 text-white" href="/">
                        <i class="bi bi-house"></i> Inicio
                    </a>
                    
                    <RouterLink class="nav-link p-2 text-white" to="/about">
                        <i class="bi bi-info-circle"></i> ¿Quienes Somos?
                    </RouterLink>
                    
                    <div class="dropdown p-d">
                        <a class="dropdown-toggle nav-link text-white" type="button" data-bs-toggle="dropdown" aria-expanded="false">
                            <i class="bi bi-whatsapp"></i> Whatsapp
                        </a>
                        <ul class="dropdown-menu">
                            <li><a class="dropdown-item" target="_blank" href="https://api.whatsapp.com/send?phone=542644682062">Ventas Online</a></li>
                            <li><a class="dropdown-item" target="_blank" href="https://api.whatsapp.com/send?phone=542645320318">Servicio Técnico</a></li>
                            <li><a class="dropdown-item" target="_blank" href="https://wa.me/message/SXEDLC4LIH26I1">Empresas</a></li>
                        </ul>
                    </div>
                    
                    <a href="http://www.maxserstore.com.ar" class="nav-link btn-tienda p-2 text-white" target="_blank"> <i class="bi bi-shop-window"></i> Maxser Store </a>
                    
                </div>
            </div>
        </div>
    </nav>
</template>

<script>
    export default{}

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