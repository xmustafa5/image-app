<script setup>
import { defineProps, ref } from "vue";
const alertVisible = ref(false)
const p = defineProps({
    iswithColor:Boolean
})

const copyUrl =  (url) => {
    const textArea = document.createElement("textarea");
  textArea.value = url;
 
  showAlert();
};
const showAlert = () => {
  alertVisible.value = true;
  setTimeout(() => {
    alertVisible.value = false;

  }, 1000);
};

</script>

<template>
    <vCard class="mx-5 my-2 pa-3">
    
    <VRow >
        <VCol v-for="n in 12" :key="n"
         cols="6"
         sm="4"
         md="3"
         lg="1"
        
         >
         <VHover
         v-slots="{isHovering, props}"
         >
         
            <VCard
            @click="copyUrl(`https://picsum.photos/500/300?image=${n * 5 + 10}${p.iswithColor ? '' : '&grayscale'}`)"
            :elevation="isHovering ? 12:2"
            v-bind:="props"
            >
                <VImg 
                :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${p.iswithColor ? '' : '&grayscale'}`"
                 aspect-ratio="1" cover>
                    <template v-slot:placeholder>
                        <VRow 
                        class="fill-height " 
                        align="center" 
                        justify="center">
                        <VProgressCircular
                            indeterminate
                            color="purple"
                            >
                            </VProgressCircular>
                        </VRow>
                    </template>
                </VImg>
            </VCard>
        </VHover>
        </VCol>
    </VRow>
</vCard>
<div class="secuuss  ">
    <v-alert  v-if="alertVisible" title="copy seccuss"  type="success" ></v-alert>

</div>
</template>

<style>
.secuuss{
    width: 15%;
    position: absolute;
    top: 8px;
    left: 8pc
}
@media screen and (min-width: 100px) and (max-width: 999px) {
    .secuuss{
    width: 60%;
    position: absolute;
    top: 8px;
    left:1pc;
   
}
.alert {
    font-size: 10pc !important;
    background: red !important;
}
}
</style>