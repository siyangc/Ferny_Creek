<template>
    <div class=service>
        <h1>{{$t("Service.Title")}}</h1>
        <div class='service-list'>
            <div class='service-item'>
                <img src="../assets/wedding.jpg" alt="">
                <h4 class='title'>{{$t("Service.Wedding")}}</h4>
                <p>{{$t("Service.WeddingContent")}}</p>
            </div>
            <div class='service-item'>
                <img src="../assets/event.jpg" alt="">
                <h4 class='title'>{{$t("Service.Event")}}</h4>
                <p>{{$t("Service.EventContent")}}</p>
            </div>
            <div class='service-item'>
                <img src="../assets/conference.jpg" alt="">
                <h4 class='title'>{{$t("Service.Conference")}}</h4>
                <p>{{$t("Service.ConferenceContent")}}</p>
            </div>
        </div>
        <br><br><br>
        <hr>
        <br><br><br>
        <div class='service-detail'>
            <div class='service-detail-item'>
                <img src="../assets/Accommodation.png" alt="">
                <h5>{{$t("Service.Accommodation")}}</h5>
            </div>
            <div class='service-detail-item'>
                <img src="../assets/Catering.png" alt="">
                <h5>{{$t("Service.Catering")}}</h5>
            </div>
            <div class='service-detail-item'>
                <img src="../assets/Photography.png" alt="">
                <h5>{{$t("Service.Photography")}}</h5>
            </div>
            <div class='service-detail-item'>
                <img src="../assets/LiveMusic.png" alt="">
                <h5>{{$t("Service.Live Music")}}</h5>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>


.service-list{
    padding-top: 50px;
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    justify-content: space-between;
}
.service-item{
    flex:1;
    text-align: center;
    
}
.service-item img{
    width: inherit;
    border-radius: 10%;
}
.title{
    padding-top:10px;
    color: #B37C57;
    text-align: center;
}
.title::before{
    content: '';
    width: 30px;
    height: 1px;
    display: inline-block;
    margin: 0 1em;
    background: #B37C57;
    vertical-align: super;
}
.title::after{
    content: '';
    width: 30px;
    height: 1px;
    display: inline-block;
    margin: 0 1em;
    background: #B37C57;
    vertical-align: super;
}
.service-item p {
    padding-left:20%;
    padding-right: 20%;
    padding-top: 10px;
    padding-bottom: 20px;
}

.service-detail{
    width: 100%;
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
    grid-row-gap: 50px;
    justify-content: space-between;
}
.service-detail-item{
    text-align: center;
}
.service-detail-item img{
    border-radius: 5%;
}
.service-detail h5 {
    padding-top: 30px;
    color:rgb(243, 156, 6);
    font-weight: bold;
}
</style>