<script setup>
import SideBar from './components/SideBar.vue'
import ImageGallery from './components/ImageGallery.vue'
import { ref } from 'vue';
const iswithColor = ref(true)
const onSlelectOption = (isColor)=>{
  iswithColor.value = isColor
}
</script>
<template>
  <VApp>
  
    <SideBar @selectOption="onSlelectOption"/>
    <VMain>
      <ImageGallery :iswithColor="iswithColor"/>
    </VMain>
  </VApp>
  
</template>


