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

export default {
    data() {
        return {
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
</template>
<style lang="css">
    #hour_title{
        font-family: 'Courier New', Courier, monospace;
    }
</style>