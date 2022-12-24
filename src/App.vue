<template>
    <NavigationDesktop v-if="screenWidth > 950" />
    <NavigationMobile v-else />
</template>
<script setup lang="ts">
import { onMounted, ref } from 'vue'
import NavigationDesktop from './components/NavigationDesktop.vue'
import NavigationMobile from './components/NavigationMobile.vue'

const screenWidth = ref(0)

onMounted(() => {
    checkWidth()
    window.addEventListener('resize', checkWidth)
})

function checkWidth() {
    screenWidth.value = window.innerWidth
    console.log(screenWidth.value)
}
</script>
