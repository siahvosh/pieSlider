<template>

  <div class="container">
    <div class="txt-slider">
      <div class="txt-item">
          <span class="title">nami nectar</span>
          <span class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aliquid consequuntur dolor dolorem ex quos, voluptatem.</span>
      </div>

    </div>
    <div id="slider" class="pic-sliders">
      <div class="item">
        <img class="img-1" src="file:///C:/Users/PC/Desktop/img-1/Luffy.png" alt="">
        <img class="img-2" src="file:///C:/Users/PC/Desktop/img-1/luffy-can.png" alt="">
      </div>
      <div class="item1">
        <img class="img-3" src="file:///C:/Users/PC/Desktop/img-1/Zoro.png" alt="">
        <img class="img-4" src="file:///C:/Users/PC/Desktop/img-1/Zoro-can.png" alt="">
      </div>
    </div>
    <div class="avatar">
      <div ></div>


    </div>


    <div @click="next(1)" style="cursor: pointer; position: absolute; width: 300px"> click </div>
  </div>

</template>

<script setup>

  let sliderNumber = -1


  function next(e){
    sliderNumber += e
    if (sliderNumber > 1)
      sliderNumber = 0


      console.log({sliderNumber: sliderNumber})
    let slider  = document.getElementById("slider")
    let slideChilds  = slider.children



    console.log({slider: slider})
    console.log({slider: slideChilds})
    // slider.style.overflow = "hidden"



  }

</script>

<style>
@import url('https://fonts.cdnfonts.com/css/fantasy');

/**{*/
/*  font-family: 'Fantasy', sans-serif ;*/
/*}*/

.container{
  position: relative;
  width: 1200px;
  height: 650px;
  background: orange;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.pic-sliders{
  position: absolute;
  width: 50%;
  height: 80%;
  background: red;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  overflow: hidden;
}

.item{
  position: relative;
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
  margin: 55px 60px 0 0;
}

.item1{
  position: relative;
  transform: translate(550px, 0);
}
.img-3{
  width: 300px;
  position: absolute;
  left: 40px;

}
.img-4{
  width: 250px;
  scale: 1.2;
  position: absolute;
  right: 0;
  margin: 55px 60px 0 0;
}

.txt-slider{
  position: absolute;
  width: 20%;
  height: 30%;
  top: 200px;
  left: 30px;
  background: red;
  overflow: hidden;
}

.title{
  color: white;
  font-weight: 800;
  letter-spacing: 2px;
  font-size: 30px;
  margin: 20px 0 0px 10px;
  display: flex;
  text-transform: uppercase;

}

.description{
  color: white;
  display: flex !important;
  margin: 10px 0 0px 20px;
}

.avatar{
  position: absolute;
  width: 10%;
  height: 70%;
  top: 100px;
  right: 50px;
  background: red;
  overflow: hidden;
}



</style>
