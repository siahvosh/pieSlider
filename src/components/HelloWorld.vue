<template>



    <div class="card">

      <div class="text-center"
           style="
                justify-content: center;
                position: relative;
                z-index: 11111;
                display: flex;
                margin: 10% 0 0 0;
                color: white;

              "
      >
        <span style="transition: all 1s ease; opacity: 0; position: absolute; font-weight: 500; letter-spacing: 15px; font-size: 50px;"> strawberry pie </span>
        <span style="transition: all 1s ease; opacity: 1; position: absolute;  font-weight: 500; letter-spacing: 10px; font-size: 50px;"> lemone pie </span>

      </div>

      <div class="text-center"
           style="
                position: relative;
                z-index: 11111;
                margin: 13% ;
                display: flex;
                color: white;
                justify-content: center;

              "
      >
        <span style="transition: all 1s ease; position: absolute ;opacity: 0;text-shadow: 0 0 8px black; font-weight: 0; letter-spacing: 3px; "> Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cum doloribus dolorum eligendi error et id impedit laborum natus nobis numquam perferendis quaerat quasi ratione recusandae, reiciendis ullam vero voluptate voluptatem?</span>
        <span style="transition: all 1s ease; position: absolute ;opacity: 1;text-shadow: 0 0 8px black; font-weight: 0; letter-spacing: 3px; "> is numquam perferendis quaerat quasi ratione recusandae, reiciendis ullam vero voluptate voluptatem?</span>
      </div>
      <div class="main">
        <div class="strawberry" style="background: #d75935">
          <img class="img-1" src="file:///C:/Users/PC/Desktop/sia3016_Arrange_halved_strawberries_in_a_circle_on_top_of_a_thi_75fb7036-1481-4ec5-98a3-d01aa42d9641%20-%20Copy.png" alt="">
        </div>
        <div class="strawberry" style="background: #e5d36d">
          <img class="img-2" src="file:///C:/Users/PC/Desktop/lemon1.png" alt="">
        </div>
        <div @click="next(1)"
          style="
           position: absolute;
           width: 30px !important;
           height: 30px;
           border-radius: 50px;
           cursor: pointer;
           top: 50%;
           left: 2%;
           background: transparent linear-gradient(to left, #fafafa, #c3b2b2);
          "
        >
          <v-icon style="margin: 0 2px 0 2px ">mdi-chevron-left</v-icon>
        </div>
      </div>

    </div>



</template>

<script setup>



  let main = document.getElementsByClassName('main')
  let text = document.getElementsByClassName('text-center')
  let num = 1




  function next(e){

    console.log({text: text})

    num += e


    if(num >= main[0].children.length - 1)
      num = 0

    for (let i = 0; i < main[0].children.length - 1; i++) {
      main[0].children[i].style.opacity = "0";
      main[0].children[i].children[0].style.transform = "rotate(-5deg)";
      text[0].children[i].style.opacity = "0";
      text[1].children[i].style.opacity = "0";
    }
    main[0].children[num].style.opacity = "1";
    main[0].children[num].children[0].style.transform = "rotate(15deg)";
    text[0].children[num].style.opacity = "1";
    text[1].children[num].style.opacity = "1";





  }

</script>

<style>
@import url('https://fonts.cdnfonts.com/css/fantasy');

*{
  font-family: 'Fantasy', sans-serif ;
}


.main{
  height: 100%;
  width: 100%;
  position: absolute;
  overflow: hidden
}

.card{
  position: relative;
  width: 1200px;
  height: 700px;
  display: flex;
  flex-direction: column;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}


.strawberry{
  transition: all 1s ease;
  height: 100%;
  width: 100%;
  opacity: 1;
  position: absolute;

}


.img-1, .img-2{
  position: absolute;
  transition: all 0.4s ease;
  /*transform:  rotate(100deg);*/

}

.img-1{
  width: 65%;
  top: 50%;
  left: 17%;
}
.img-2{
  width: 60%;
  top: 50%;
  left: 20%;
}
/*img:hover{*/
/*  transform:  rotate(100deg);*/
/*  animation: rotate 1s ease;*/


/*}*/

@keyframes rotate{
  0%{
    transform: rotate(0deg);
  }

  100%{
    transform: rotate(15deg);
  }
}

/*;DataCenterHint =>*/
/*;    default (ping based)*/
/*;    playfab/australiaeast*/
/*;    playfab/brazilsouth*/
/*;    playfab/centralus*/
/*;    playfab/eastasia*/
/*;    playfab/eastus*/
/*;    playfab/japaneast*/
/*;    playfab/northeurope*/
/*;    playfab/southafricanorth*/
/*;    playfab/southcentralus*/
/*;    playfab/southeastasia*/
/*;    playfab/uaenorth*/
/*;    playfab/westeurope*/
/*;    playfab/westus*/


</style>
