<template>
    <nav>
        <div class="nav-container">
            <img src="../assets/logo.svg" alt="Trafalgar" />

            <button @click="menuIsVisible = !menuIsVisible">
                <div class="wrapper" :class="{ trans: menuIsVisible }">
                    <div class="menu-line" :class="{ line1: menuIsVisible }"></div>
                    <div class="menu-line" :class="{ line2: menuIsVisible }"></div>
                    <div class="menu-line" :class="{ line3: menuIsVisible }"></div>
                </div>
            </button>
        </div>
        <transition name="height">
            <div class="dropdown" v-if="menuIsVisible">
                <menu>
                    <li>Home</li>
                    <li>Find a doctor</li>
                    <li>Apps</li>
                    <li>Testimonials</li>
                    <li>About us</li>
                </menu>
            </div>
        </transition>
    </nav>
    <div class="overlay" v-if="menuIsVisible" @click="menuIsVisible = false"></div>
</template>
<script setup lang="ts">
import { ref } from 'vue'

const menuIsVisible = ref(false)
</script>
<style scoped lang="scss">
nav {
    display: flex;
    flex-direction: column;
    font-size: 18px;
    position: relative;

    .nav-container {
        width: 100%;
        display: flex;
        flex-flow: row nowrap;
        align-items: center;
        justify-content: space-between;
        padding: 30px 7vw;
        position: relative;
        z-index: 10;
        background: #ffffff;

        img {
            height: 41px;
        }

        button {
            padding: unset;

            .wrapper {
                display: flex;
                flex-direction: column;
                gap: 8px;
                transition: 500ms transform;

                &.trans {
                    transform: translateX(50%);
                }

                .menu-line {
                    width: 30px;
                    height: 2px;
                    background: black;
                    transition: transform 500ms;

                    &.line1 {
                        transform: rotateZ(-45deg) translateX(-50%);
                    }
                    &.line2 {
                        transform: rotateZ(-45deg) translate(-8px, -7px);
                        height: 2px;
                    }
                    &.line3 {
                        transform: rotateZ(45deg) translateX(-47%);
                    }
                }
            }
        }
    }

    .dropdown {
        background: #ffffff;
        padding: 30px 7vw;
        z-index: 9;
        position: absolute;
        top: 101px;
        width: 100%;

        menu {
            display: flex;
            flex-flow: column;
            list-style: none;
            gap: 20px;
        }
    }
}
.overlay {
    width: 100%;
    height: 100vh;
    z-index: 8;
    position: absolute;
    top: 0;
    left: 0;
}
.height-enter-active,
.height-leave-active {
    transition: transform 0.5s ease;
}

.height-enter-from,
.height-leave-to {
    transform: translateY(-100%);
}
</style>
