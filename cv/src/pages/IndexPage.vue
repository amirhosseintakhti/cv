<template>
  <q-page>
    <div class="row q-col-gutter-xs-0q">
       <div :class="['col-lg-7 col-md-6 col-xs-12 text-header', $q.screen.gt.md?'text-center':'text-']">
        <div class="q-ml-xl text-center">
        <p>fullstack developer</p>
        <h1 class="text-h2">Hi, I'm <span>amirhossein</span><br>from iran</h1>
        </div>

       </div>
       <div class="col-lg-5 col-md-6 col-xs-12 "><img class="image-bg" src="public/amirhossein1.png" alt=""></div>
    </div>
    <div class="row q-col-gutter-xs-0">
      <div class="col-lg-4 col-md-5 col-xs-12 ">
        <img class="q-ml-xl" src="public/amirabout.svg" alt="" style=" border-radius: 10px;">
      </div>
      <div class="col-lg-7 col-md-6 col-xs-12 text-xs-center" >
        <p class="text-h2 " style="font-family: 'kalameh-Regular';">about</p>
      </div>
    </div>

  </q-page>
</template>

<script setup>
defineOptions({
  name: 'IndexPage'
});
</script>

