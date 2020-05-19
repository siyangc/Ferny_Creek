<template>
    <div class='contact'>
        <h1>{{$t("Contact.Title")}}</h1>
        <div class='container'>
            <div class='container-left'>
                <h3>{{$t("Contact.L-Title")}}</h3>                
                <h4>{{$t("Contact.Address")}}</h4>                
                <h4>{{$t("Contact.Office")}}</h4>                
                <h4>{{$t("Contact.Phone")}}</h4>                
                <h4>{{$t("Contact.Email")}}</h4>
            </div>
            <div class='container-right'>
                <h3>{{$t("Contact.R-Title")}}</h3>                
                <img src="../assets/wechat.jpg" alt="">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
.contact {
    width: 100%;
    background-color: #000;
    position: relative;
    padding-bottom: 30px;
}
h1{
    padding-top: 50px;
    padding-bottom: 50px;
    color: #ffffff;
}
.container{
    margin: 40px 20% 0 20%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 30px;
    justify-content: center;
}
.container-left{
    text-align: left;
    
}
.container-right{
    text-align: right; 
}
h3{
    color: #ffffff;
    margin-bottom: 30px;
}
h4{
    color:dimgray;
    margin-bottom: 20px;
}
img{
    width: 150px;
}
@media (max-width: 500px){
    .container{
        grid-template-columns: 1fr;
        margin:0;
    }
    .container-left{
    text-align: center;
    
}
.container-right{
    text-align: center; 
}

}
</style>