<template>
    <nav>
        <img src="../assets/logo.svg" alt="Trafalgar" />
        <ul>
            <li>Home</li>
            <li>Find a doctor</li>
            <li>Apps</li>
            <li>Testimonials</li>
            <li>About us</li>
        </ul>
    </nav>
</template>
<script setup lang="ts"></script>
<style scoped lang="scss">
nav {
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    justify-content: space-between;
    padding: 56px 10vw;

    ul {
        display: flex;
        flex-flow: row nowrap;
        list-style: none;
        gap: 40px;
        font-size: 18px;
        font-weight: 400;

        li {
            cursor: pointer;
            opacity: 0.5;
            transition: opacity 300ms;

            &:hover {
                opacity: 1;
            }
        }
    }
}
</style>
