<template>
    <div class='team'>
        <h1>{{$t("Team.Title")}}</h1>
        <div class='team-list'>
            <div class='team-member'>
                <div class='pic'>
                    <img src="../assets/Chloe.jpg" alt="">
                    <h5>Chloe</h5>
                    <p>Director</p>
                </div>                
            </div>
            <div class='team-member'>
                <div class='pic'>
                    <img src="../assets/Angela.jpg" alt="">
                    <h5>Angela</h5>
                    <p>Marketing Manager</p>
                </div>
            </div>
            <div class='team-member'>
                <div class='pic'>
                    <img src="../assets/Cissy.jpg" alt="">
                    <h5>Cissy</h5>
                    <p>Office Coordinator</p>
                </div>
            </div>
            <div class='team-member'>
                <div class='pic'>
                    <img src="../assets/Tom.jpg" alt="">
                    <h5>Tom</h5>
                    <p>Event Coordinator</p>
                </div>
            </div>
            <div class='team-member'>
                <div class='pic'>
                    <img src="../assets/Marshell.jpg" alt="">
                    <h5>Marshell</h5>
                    <p>Property Manager</p>
                </div>
            </div>
            <div class='team-member'>
                <div class='pic'>
                    <img src="../assets/Sheep.jpg" alt="">
                    <h5>Peach&Pumpkin</h5>
                    <p>Friends</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>

.team-list{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;    
}
.team-member{
    width: 150px;
    margin-top: 20px;
    margin-left:20px;
    margin-right:20px;
}

.team-member img{
    width: 100%;
    display: block;
    border-radius: 5%;
}
.pic{
    position: relative;
    
}
.pic::before{
    content: "";
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.6);
    position: absolute;
    top: 0;
    left: 0;
    opacity: 0;
    transition: all 0.6s ease 0s;
    border-radius: 5%;
}
.team-member:hover .pic::before{
    opacity: 1;
}
h5{
    font-size: 18px;
    position: absolute;
    left: 5px;
    top: 100px;
    opacity: 0;
    color: #ffffff;
}
p{
    position: absolute;
    left: 5px;
    top: 125px;
    opacity: 0;
    color: #ffffff;
    font-size: 12px;
}
.team-member:hover p{
    opacity: 1;
    transition: 1s;
}
.team-member:hover h5{
    opacity: 1;
    transition: 1s;
}
</style>