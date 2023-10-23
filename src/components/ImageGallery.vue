<template>
    <VRow class="ma-0">
        <VCol v-for="n in 200" :key="n"
         cols="6"
         sm="4"
         md="3"
         lg="1"
         >
            <VCard>
                <VImg 
                :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
                 aspect-ratio="1" cover>
                    <template v-slot:placeholder>
                        <VRow 
                        class="fill-height ma-0" 
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
</template>