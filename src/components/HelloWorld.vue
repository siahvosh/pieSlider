<template>

        <div class="main">


          <v-row cols="12" style="height: 40%" justify="center" align-content="center">
            <v-col cols="4" style="border: 1px solid white; height: 100%">

                <img class="stra-img-1" src="file:///C:/Users/PC/Desktop/%E2%80%94Pngtree%E2%80%94a%20strawberry_4435823.png" alt="">


            </v-col>
            <v-col cols="4" style="border: 1px solid white; align-self: center">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Explicabo, iure?</v-col>
            <v-col cols="4" style="border: 1px solid white"></v-col>

          </v-row>
          <v-row cols="12"> </v-row>

        </div>



</template>

<script setup>
  //
</script>

<style>
body{

}


.main{
  width: 100%;
  height: 100%;
  background: #FF7B54 !important;
}

.stra-img-1{
  width: 200px;
  position: absolute;
  display: flex;
  filter: drop-shadow(5px 0 5px black);
  transform: translate(-20px, -20px);
  animation: rotate 1s ease 0.2s 1;
  transform-style: preserve-3d;
}
@keyframes rotate {
  from{
    rotate: 0;
  }
  to{
    rotate: 360deg;
  }

}



</style>
