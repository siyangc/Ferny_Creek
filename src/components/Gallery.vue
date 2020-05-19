<template>
    <div class='gallery'>
        <owl 
        :autoplay='true' 
        :responsive='responsive'
        :dots='false'>
            <template v-slot:prev><img class='left-arrow' src="../assets/arrow.png" alt=""></template>
                <img src="../assets/slide-01.jpg">
                <img src="../assets/slide-02.jpg">
                <img src="../assets/slide-03.jpg">
                <img src="../assets/slide-04.jpg">
                <img src="../assets/slide-05.jpg">
                <img src="../assets/slide-06.jpg">
                <img src="../assets/slide-07.jpg">
                <img src="../assets/slide-08.jpg">
            
            <template v-slot:next><img class='right-arrow' src="../assets/arrow.png" alt=""></template>
        </owl>     
        

    </div>
</template>

<script>
import owl from 'vue-owl-carousel'
export default {
    components: {
        owl
    },
    data() {
        return {
            responsive:{0:{items:1,nav:false},500:{items:2,nav:false}}
        }
    },
    methods: {
        turnLeft(){

        }
    }
    
}
</script>

<style scoped>
.gallery {
    width: 100%;
    position: relative;
}
.left-arrow{
    width: 30px;
    position: absolute;
    top: 50%;
    left: 10px;
    z-index: 30;
    transform:rotate(90deg);
}
.right-arrow{
    width: 30px;
    position: absolute;
    top: 50%;
    right: 10px;
    z-index: 30;
    transform:rotate(-90deg);
}
</style>