<template>
    <article class="testimonials">
        <h2>What our customers are saying</h2>
        <hr />
        <div class="carousel">
            <transition :name="carousel.transitionName">
                <div class="testimonial" v-if="carousel.currentItem == 0">
                    <div class="person-info">
                        <img src="../assets/images/dude.webp" alt="Edward Newgate profile picture" />
                        <div class="info-wrapper">
                            <span class="name">Edward Newgate</span>
                            <span class="title">Founder Circle</span>
                        </div>
                    </div>
                    <div class="quote">
                        <p>
                            “Our dedicated patient engagement app and web portal allow you to access information
                            instantaneously (no tedeous form, long calls, or administrative hassle) and securely”
                        </p>
                    </div>
                </div>
                <div class="testimonial" v-else-if="carousel.currentItem == 1">
                    <div class="person-info">
                        <img src="../assets/images/dude.webp" alt="Edward Newgate profile picture" />
                        <div class="info-wrapper">
                            <span class="name">Edward Newgate</span>
                            <span class="title">Founder Circle</span>
                        </div>
                    </div>
                    <div class="quote">
                        <p>
                            “Our dedicated patient engagement app and web portal allow you to access information
                            instantaneously (no tedeous form, long calls, or administrative hassle) and securely”
                        </p>
                    </div>
                </div>
                <div class="testimonial" v-else-if="carousel.currentItem == 2">
                    <div class="person-info">
                        <img src="../assets/images/dude.webp" alt="Edward Newgate profile picture" />
                        <div class="info-wrapper">
                            <span class="name">Edward Newgate</span>
                            <span class="title">Founder Circle</span>
                        </div>
                    </div>
                    <div class="quote">
                        <p>
                            “Our dedicated patient engagement app and web portal allow you to access information
                            instantaneously (no tedeous form, long calls, or administrative hassle) and securely”
                        </p>
                    </div>
                </div>
                <div class="testimonial" v-else-if="carousel.currentItem == 3">
                    <div class="person-info">
                        <img src="../assets/images/dude.webp" alt="Edward Newgate profile picture" />
                        <div class="info-wrapper">
                            <span class="name">Edward Newgate</span>
                            <span class="title">Founder Circle</span>
                        </div>
                    </div>
                    <div class="quote">
                        <p>
                            “Our dedicated patient engagement app and web portal allow you to access information
                            instantaneously (no tedeous form, long calls, or administrative hassle) and securely”
                        </p>
                    </div>
                </div>
            </transition>
        </div>
    </article>

    <div class="arrows">
        <button @click="handleCarousel(false)" class="left arrow" :class="{ disabled: carousel.currentItem == 0 }">
            <img src="../assets/images/arrow.svg" alt="previous testimonial" />
        </button>
        <button class="dot" @click="handleDot(0)" :class="{ disabled: carousel.currentItem != 0 }"></button>
        <button class="dot" @click="handleDot(1)" :class="{ disabled: carousel.currentItem != 1 }"></button>
        <button class="dot" @click="handleDot(2)" :class="{ disabled: carousel.currentItem != 2 }"></button>
        <button class="dot" @click="handleDot(3)" :class="{ disabled: carousel.currentItem != 3 }"></button>
        <button class="arrow" @click="handleCarousel(true)" :class="{ disabled: carousel.currentItem == 3 }">
            <img src="../assets/images/arrow.svg" alt="next testimonial" />
        </button>
    </div>
</template>
<script setup lang="ts">
import { reactive } from 'vue'

const carousel = reactive({
    currentItem: 0,
    transitionName: 'slide-right',
})

function handleCarousel(nextItem: boolean) {
    if (nextItem && carousel.currentItem < 3) {
        carousel.transitionName = 'slide-right'
        carousel.currentItem++
    } else if (!nextItem && carousel.currentItem > 0) {
        carousel.transitionName = 'slide-left'
        carousel.currentItem--
    }
}

function handleDot(dotIndex: number) {
    carousel.transitionName = 'slide-up'
    carousel.currentItem = dotIndex
}
</script>
<style scoped lang="scss">
.testimonials {
    margin-top: 150px;
    background: linear-gradient(208.18deg, #67c3f3 9.05%, #5a98f2 76.74%);
    border-radius: 24px;
    color: white;
    width: 95%;
    max-width: 1120px;
    margin-inline: auto;
    flex-direction: column;
    text-align: center;
    padding: 30px;
    min-height: 425px;

    @media (min-width: 500px) {
        padding: 64px;
        margin-top: 266px;

        .testimonial-wrapper {
            gap: 110px;
        }
    }

    hr {
        width: 56px;
        height: 2px;
        background: white;
        margin-inline: auto;
        margin-top: 25px;
    }

    .carousel {
        display: grid;
        width: 100%;
        height: 100%;
        overflow: hidden;

        .testimonial {
            margin-top: 60px;
            display: flex;
            flex-flow: row wrap;
            gap: 50px;
            justify-content: space-evenly;
            grid-area: 1 / 1;

            .person-info {
                display: flex;
                flex-flow: row nowrap;
                align-items: center;
                gap: 20px;

                img {
                    border-radius: 50%;
                    border: 4px solid white;
                    width: 80px;
                }

                .info-wrapper {
                    display: flex;
                    flex-direction: column;
                    align-items: flex-start;
                    gap: 0.6em;

                    .name {
                        width: max-content;
                        font-weight: 700;
                        font-size: 18px;
                    }
                    .title {
                        width: max-content;
                        font-weight: 400;
                        font-size: 16px;
                    }
                }
                @media (min-width: 500px) {
                    img {
                        width: 133px;
                    }

                    .info-wrapper {
                        .name {
                            font-weight: 700;
                            font-size: 22px;
                        }
                        .title {
                            font-weight: 400;
                            font-size: 18px;
                        }
                    }
                }
            }
            .quote {
                max-width: 420px;
                width: 100%;

                p {
                    color: white;
                    font-weight: 400;
                    font-size: 19px;
                    text-align: left;
                }
            }
        }
    }
}

.arrows {
    display: flex;
    flex-flow: row nowrap;
    width: 100%;
    justify-content: center;
    align-items: center;
    gap: 18px;
    margin-top: 40px;

    button {
        transition: opacity 300ms;

        &.left {
            transform: rotateZ(180deg);
        }

        &.arrow {
            &.disabled {
                opacity: 0.5;
                cursor: default;
            }
        }
        &.dot {
            padding: 0;
            width: 10px;
            height: 10px;
            background: #5b9bf3;

            &.disabled {
                opacity: 0.5;
            }
        }
    }
}

.slide-right-enter-active,
.slide-right-leave-active {
    transition: all 0.25s ease-out;
}

.slide-right-enter-from {
    opacity: 0;
    transform: translateX(100%);
}

.slide-right-leave-to {
    opacity: 0;
    transform: translateX(-100%);
}

.slide-left-enter-active,
.slide-left-leave-active {
    transition: all 0.25s ease-out;
}

.slide-left-enter-from {
    opacity: 0;
    transform: translateX(-100%);
}

.slide-left-leave-to {
    opacity: 0;
    transform: translateX(100%);
}

.slide-up-enter-active,
.slide-up-leave-active {
    transition: all 0.25s ease-out;
}

.slide-up-enter-from {
    opacity: 0;
    transform: translateY(-100%);
}

.slide-up-leave-to {
    opacity: 0;
    transform: translateY(100%);
}
</style>
