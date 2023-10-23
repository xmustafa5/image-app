<script setup>
import { defineProps } from "vue";
const p = defineProps({
    iswithColor:Boolean
})


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
            <VCard>
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
        </VCol>
    </VRow>
</vCard>
</template>