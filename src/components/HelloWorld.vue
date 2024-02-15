<template>
  <div id="container" class="container">
    <div id="txt-slider" class="txt-slider">
      <div class="txt-item">
          <span class="title">luffy fizz</span>
          <span class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium debitis dignissimos dolorum eos et eum harum ipsam, omnis, quaerat soluta tempora tempore! Molestias, officiis vitae! Alias deleniti eaque possimus tenetur?</span>
      </div>
      <div class="txt-item-1">
        <span class="title">zero zest</span>
        <span class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium debitis dignissimos dolorum eos et eum harum ipsam, omnis, quaerat soluta tempora tempore! Molestias, officiis vitae! Alias deleniti eaque possimus tenetur?</span>
      </div>
      <div class="txt-item-1">
        <span class="title">sanji spark</span>
        <span class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium debitis dignissimos dolorum eos et eum harum ipsam, omnis, quaerat soluta tempora tempore! Molestias, officiis vitae! Alias deleniti eaque possimus tenetur?</span>
      </div>
      <div class="txt-item-1">
        <span class="title">nami nectar</span>
        <span class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium debitis dignissimos dolorum eos et eum harum ipsam, omnis, quaerat soluta tempora tempore! Molestias, officiis vitae! Alias deleniti eaque possimus tenetur?</span>
      </div>
    </div>
    <div id="slider" class="pic-sliders">
      <div class="item">
        <img class="img-1" src="file:///C:/Users/PC/Desktop/img-1/Luffy.png" alt="">
        <img class="img-2" src="file:///C:/Users/PC/Desktop/img-1/luffy-can.png" alt="">
      </div>
      <div class="item-1">
        <img class="img-3" src="file:///C:/Users/PC/Desktop/img-1/Zoro.png" alt="">
        <img class="img-4" src="file:///C:/Users/PC/Desktop/img-1/Zoro-can.png" alt="">
      </div>
      <div class="item-1">
        <img class="img-3" src="file:///C:/Users/PC/Desktop/img-1/Sanji.png" alt="">
        <img class="img-4" src="file:///C:/Users/PC/Desktop/img-1/Sanji-can.png" alt="">
      </div>
      <div class="item-1">
        <img class="img-3" src="file:///C:/Users/PC/Desktop/img-1/Nami.png" alt="">
        <img class="img-4" src="file:///C:/Users/PC/Desktop/img-1/Nami-can.png" alt="">
      </div>
    </div>
    <div style="position: absolute; bottom: 160px; left: 28px">
      <button style="width: 400px; height: 50px; border-radius: 5px; background: #eae4e4;">
        <span  style="font-weight: 700; font-size: 18px"> buy now </span>
        <svg style="transform: translate(5px, 4px)" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M7 18c-1.1 0-1.99.9-1.99 2S5.9 22 7 22s2-.9 2-2s-.9-2-2-2M1 4h2l3.6 7.59L3.62 17H19v-2H7l1.1-2h8.64l4.97-9H5.21l-.94-2H1zm16 14c-1.1 0-1.99.9-1.99 2s.89 2 1.99 2s2-.9 2-2s-.9-2-2-2"/></svg>
      </button>
    </div>
    <div class="label" style="position: absolute; top: 50px; left: 100px">
      <span style="font-family: Garamond, serif;font-weight: 700; font-size: 24px; color: white; text-transform: uppercase; letter-spacing: 5px">mirzad</span>
      <img width="50" height="70"  src="file:///C:/Users/PC/Desktop/1x/7797864.png" alt="">
      <span style="font-family: Garamond, serif;font-weight: 700; font-size: 24px; color: #f8f8f8; text-transform: uppercase; letter-spacing: 5px">siavash</span>
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

    const transformElements = (index, yTranslate, xTranslate = 0, scale = 1, opacity = 0, tOpacity = 1) => {
      textChild[index].style.transform = `translate(0, ${yTranslate}px)`;
      textChild[index].style.opacity = tOpacity;
      slideChild[index].style.transform = `translate(${xTranslate}px, 0)`;
      slideChild[index].style.scale = scale;
      slideChild[index].style.opacity = opacity;
    };

    if (lastCard > currentCard) {
      for (let i = currentCard + 1; i < textChild.length; i++)
        transformElements(i, 200, 700);
      transformElements(lastCard, 200, 700);
    }
    else {
      for(let i = 0; i < currentCard; i++)
        transformElements(i, -200, -700);
      transformElements(lastCard, -200, -700);
    }
    transformElements(currentCard, 0, 0, 1.1, 1, 1);

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
  /*overflow: hidden;*/
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

.item, .item-1{
  position: relative;
  transition: all 0.3s ease;
  scale: 1.1;
}

.item-1 {
  transform: translate(700px, 0);
}

.img-1, .img-3{
  width: 230px;
  position: absolute;
  left: 50px;
}
.img-3{
  width: 300px;
}

.img-2, .img-4{
  width: 250px;
  scale: 1.2;
  position: absolute;
  right: 0;
  margin: 55px 110px 0 0;
}



/*text slider--------------------------------------------------------------------*/
.txt-slider{
  position: relative;
  width: 35%;
  height: 35%;
  top: 210px;
  left: 30px;
  overflow: hidden;
  /*border: 2px solid red;*/
}

.txt-item, .txt-item-1{
  position: relative;
  top: 85px;
  transition: all 0.3s ease;
  display: flex;
}

.txt-item-1{
  transform: translate(0, 200px);
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
  margin: 10px 0 0 0;
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

button:hover{
  background: #ded9d9 !important;
}

.label::after{
  content: '';
  position: absolute;
  height: 5px;
  background-image: linear-gradient(to left, red, white);
  width:  99%;
  left: 0px;
  top: 80px;


}


</style>
