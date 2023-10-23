<script setup>
import { defineEmits } from 'vue'

const emits = defineEmits(['selectOption'])

const selectOption = (red) => {
  emits('selectOption', red)
}
</script>



<template>
          <VNavigationDrawer
          expand-on-hover
            rail
          >
          <VList>
          <VListItem
            prepend-avatar="https://avatars.githubusercontent.com/u/107437940?v=4"
            title="Mustafa mohammed"
            subtitle="musmoh73@gmail.com"
          ></VListItem>
        </VList>
        <VDivider></VDivider>
        <VList density="compact" nav>
          <VListItem 
  prepend-icon="mdi-image" 
  title="Color Gallery" 
  value="color"
  @click="selectOption(true)"
></VListItem>
       </VList>
       <VList density="compact" nav>
        <VListItem 
  prepend-icon="mdi-dialpad" 
  title="Grayspace Gallery" 
  value="grayscale"
  @click="selectOption(false)"
></VListItem>
       </VList>
          </VNavigationDrawer>

</template>