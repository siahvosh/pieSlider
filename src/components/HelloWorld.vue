<template>

  <div id="container" class="container">
    <div class="txt-slider">
      <div class="txt-item">
          <span class="title">nami nectar</span>
          <span class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aliquid consequuntur dolor dolorem ex quos, voluptatem.</span>
      </div>

    </div>
    <div id="slider" class="pic-sliders" >
      <div class="item">
        <img class="img-1" src="file:///C:/Users/PC/Desktop/img-1/Luffy.png" alt="">
        <img class="img-2" src="file:///C:/Users/PC/Desktop/img-1/luffy-can.png" alt="">
      </div>
      <div class="item1">
        <img class="img-3" src="file:///C:/Users/PC/Desktop/img-1/Zoro.png" alt="">
        <img class="img-4" src="file:///C:/Users/PC/Desktop/img-1/Zoro-can.png" alt="">
      </div>
      <div class="item1">
        <img class="img-3" src="file:///C:/Users/PC/Desktop/img-1/Sanji.png" alt="">
        <img class="img-4" src="file:///C:/Users/PC/Desktop/img-1/Sanji-can.png" alt="">
      </div>
      <div class="item1">
        <img class="img-3" src="file:///C:/Users/PC/Desktop/img-1/Nami.png" alt="">
        <img class="img-4" src="file:///C:/Users/PC/Desktop/img-1/Nami-can.png" alt="">
      </div>
    </div>
    <div class="avatars">
      <img @click="showCard(0)" class="avatar" src="file:///C:/Users/PC/Desktop/img-1/luffy-profile.png" alt="">
      <img @click="showCard(1)" class="avatar" src="file:///C:/Users/PC/Desktop/img-1/zoro-profile.png" alt="">
      <img @click="showCard(2)" class="avatar" src="file:///C:/Users/PC/Desktop/img-1/sanji-profile.png" alt="">
      <img @click="showCard(3)" class="avatar" src="file:///C:/Users/PC/Desktop/img-1/nami-profile.png" alt="">
    </div>
  </div>

</template>

<script setup>

  let sliderNumber = -1
  let cardNumber = 0

  function showCard(val){
    cardNumber = val
    let slider  = document.getElementById("slider")
    let container  = document.getElementById("container")
    let slideChilds  = slider.children

    // console.log({slider: sliderNumber})



    console.log({val : cardNumber})
    for (let i = 0; i <= slideChilds.length; i++){
      slideChilds[0].style.transform= "translate(-550px, 0)"
      slideChilds[0].style.scale= "1.1"
    }
      slideChilds[cardNumber].style.transform= "translate(0, 0)"
      slideChilds[cardNumber].style.scale= "1.2"
      container.style.background = "#3f6235"
      slideChilds[0].style.opacity= "0"


  }



</script>

<style>
@import url('https://fonts.cdnfonts.com/css/fantasy');

/**{*/
/*  font-family: 'Fantasy', sans-serif ;*/
/*}*/

.container{
  position: relative;
  width: 1300px;
  height: 650px;
  background: #b21616;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.pic-sliders{
  position: absolute;
  width: 50%;
  height: 90%;
  top: 50%;
  left: 60%;
  transform: translate(-50%, -50%);
  overflow: hidden;

}

.item{
  position: relative;
  transition: all 0.5s ease;
  scale: 1.2;
}

.img-1{
  width: 230px;
  position: absolute;
  left: 50px;
}
.img-2{
  width: 250px;
  scale: 1.2;
  position: absolute;
  right: 0;
  margin: 55px 90px 0 0;
}

.item1{
  position: relative;
  transform: translate(590px, 0);
  transition: all 0.5s ease;
}
.img-3{
  width: 300px;
  position: absolute;
  left: 40px;
  z-index: 1;

}
.img-4{
  width: 250px;
  scale: 1.2;
  position: absolute;
  right: 0;
  margin: 55px 90px 0 0;
}

.txt-slider{
  position: absolute;
  width: 35%;
  height: 30%;
  top: 210px;
  left: 30px;
  overflow: hidden;
}

.title{
  color: white;
  font-weight: 800;
  letter-spacing: 2px;
  font-size: 50px;
  margin: 20px 0 0 10px;
  display: flex;
  text-transform: uppercase;

}

.description{
  color: white;
  display: flex !important;
  margin: 10px 0 0 10px;
}

.avatars{
  position: absolute;
  width: 10%;
  height: 70%;
  top: 100px;
  right: 50px;
  /*background: red;*/
  overflow: hidden;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;


}

.avatar{
  border-radius: 180%;
  width: 100px;
  object-fit: cover;
  align-self: center;
  border: 1px solid grey;
  cursor: pointer;
}


</style>
