<template>
  <div id="container" class="container">
    <div id="txt-slider" class="txt-slider">
      <div class="txt-item">
          <span class="title">luffy fizz</span>
          <span class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit.consectetur adipisicing elit. Aliquid consequuntur dolor dolorem ex quos, voluptatem.</span>
      </div>
      <div class="txt-item1">
        <span class="title">zero zest</span>
        <span class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit.consectetur adipisicing elit. Aliquid consequuntur dolor dolorem ex quos, voluptatem.</span>
      </div>
      <div class="txt-item1">
        <span class="title">sanji spark</span>
        <span class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit.consectetur adipisicing elit. Aliquid consequuntur dolor dolorem ex quos, voluptatem.</span>
      </div>
      <div class="txt-item1">
        <span class="title">nami nectar</span>
        <span class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit.consectetur adipisicing elit. Aliquid consequuntur dolor dolorem ex quos, voluptatem.</span>
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
  let currentCard = 0
  let lastCard = 0

  function showCard(val){
    currentCard = val

    let slideChild  = document.getElementById("slider").children
    let textChild  = document.getElementById("txt-slider").children
    let container  = document.getElementById("container")

    console.log({lastCard: lastCard})
    console.log({currentCard: currentCard})
    console.log({len: textChild.length})

    const transformElements = (index, yTranslate, xTranslate = 0, scale = 0.8, opacity = 0) => {
      textChild[index].style.transform = `translate(0, ${yTranslate}px)`;
      slideChild[index].style.transform = `translate(${xTranslate}px, 0)`;
      slideChild[index].style.scale = scale;
      slideChild[index].style.opacity = opacity;
    };

    if (lastCard > currentCard) {
      for (let i = currentCard + 1; i < textChild.length; i++) {
        slideChild[i].style.transform = "translateX(700px)"
        // textChild[i].style.transform = "translateY(-100px)";
      }
      transformElements(lastCard, 100, 700);
      transformElements(currentCard, -100, 0, 1.1, 1);
    }
    else {
      for(let i = 0; i < currentCard; i++) {
        slideChild[i].style.transform = "translateX(-700px)"
        // textChild[i].style.transform = "translateY(100px)";
      }
      transformElements(lastCard, -100, -700);
      transformElements(currentCard, 100, 0, 1.1, 1);
    }

    lastCard = currentCard

    const setBackground = (colors) => {
      container.style.background = colors[currentCard];
    };
    switch (currentCard) {
      case 0:
        setBackground(["radial-gradient(circle, rgb(199, 100, 100) 5%, rgba(178,22,22,100) 90%)", null, null, null]);
        break;
      case 1:
        setBackground([null, "radial-gradient(circle, rgba(150, 190, 138, 100) 5%, rgba(63,98,53,100) 90%)", null, null]);
        break;
      case 2:
        setBackground([null, null, "radial-gradient(circle, rgba(185, 185, 131, 100) 5%, rgba(144,144,92,100) 90%)", null]);
        break;
      case 3:
        setBackground([null, null, null, "radial-gradient(circle, rgba(220, 117, 63, 100) 5%, rgba(188,70,7,100) 90%)"]);
        break;
      default:
        setBackground(["default background"]);
    }
  }
</script>

<style>
@import url('https://fonts.cdnfonts.com/css/fantasy');

.container{
  position: relative;
  width: 1300px;
  height: 650px;
  background: radial-gradient(circle, rgb(199, 100, 100) 5%, rgba(178,22,22,100) 90%);
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  overflow: hidden;
}

/*image slider--------------------------------------------------------------------*/
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
  transition: all 0.4s ease;
  scale: 1.1;
}
.item1 {
  position: relative;
  transform: translate(700px, 0);
  transition: all 0.3s ease;
  scale: 0.8;
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
  margin: 55px 110px 0 0;
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
  margin: 55px 110px 0 0;
}

/*text slider--------------------------------------------------------------------*/
.txt-slider{
  position: absolute;
  width: 35%;
  height: 35%;
  /*border: 1px solid white;*/
  top: 210px;
  left: 30px;
  overflow: hidden;
}
.txt-item{
  position: relative;
  transition: all 0.5s ease;
  display: flex;
  transform: translate(0, 100px);


}
.txt-item1{
  position: relative;
  transition: all 0.5s ease;
  transform: translate(0, 300px);
  display: flex;
  text-justify: initial;
}
.title{
  color: white;
  font-weight: 800;
  letter-spacing: 2px;
  font-size: 50px;
  align-self: end;
  /*margin: 20px 0 0 25px;*/
  position: absolute;
  text-transform: uppercase;

}
.description{
  position: absolute;
  color: white;
  align-self: start;
  /*margin: 10px 0 0 10px;*/
}


/*avatar box--------------------------------------------------------------------*/
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
