<template>
    <div class='about'>
        <h1>{{$t("About.Title")}}</h1>
        <p>{{$t("About.Content")}}</p>
    </div>

</template>

<script>
export default {
    
}
</script>

<style scoped>
.about{
    background-color: rgb(231, 199, 91);

}
h1{
    text-align: center;
    font-size: 50px;
    color: #ffffff;
    padding-top: 30px;
    padding-bottom: 10px;
}

@media (max-width: 500px) {
    p{
        font-size: 15px;
        font-family: 'Sriracha', cursive;    
        padding-bottom: 30px;
    }
}
@media (min-width: 501px) {
    p{
        padding-left: 20%;
        padding-right: 20%;
        font-size: 25px;
        font-family: 'Sriracha', cursive;    
        padding-bottom: 50px;
        line-height: 80px;
    }
}
</style>