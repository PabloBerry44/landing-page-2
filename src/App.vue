<template>
    <NavigationDesktop v-if="screenWidth > 950" />
    <NavigationMobile v-else />

    <section class="two-columns-template hero">
        <div class="text-content">
            <h1>Virtual healthcare for you</h1>
            <p>
                Trafalgar provides progressive, and affordable healthcare, accessible on mobile and online for everyone
            </p>
            <button class="blue">Consult today</button>
        </div>
        <img src="./assets/images/trafalgar-header-illustration-1.webp" alt="" />
    </section>

    <section class="services">
        <h2>Our services</h2>
        <p class="description">
            We provide to you the best choiches for you. Adjust it to your health needs and make sure your undergo
            treatment with our highly qualified doctors you can consult with us which type of service is suitable for
            your health
        </p>
        <div class="services-grid">
            <div class="service">
                <img src="./assets/images/service_005.webp" alt="" />
                <h3>Search doctor</h3>
                <p>Choose your doctor from thousands of specialist, general, and trusted hospitals</p>
            </div>
            <div class="service">
                <img src="./assets/images/service_001.webp" alt="" />
                <h3>Online pharmacy</h3>
                <p>Buy your medicines with our mobile application with a simple delivery system</p>
            </div>
            <div class="service">
                <img src="./assets/images/service_002.webp" alt="" />
                <h3>Consultation</h3>
                <p>Free consultation with our trusted doctors and get the best recomendations</p>
            </div>
            <div class="service">
                <img src="./assets/images/service_003.webp" alt="" />
                <h3>Details info</h3>
                <p>Free consultation with our trusted doctors and get the best recomendations</p>
            </div>
            <div class="service">
                <img src="./assets/images/service_004.webp" alt="" />
                <h3>Emergency care</h3>
                <p>You can get 24/7 urgent care for yourself or your children and your lovely family</p>
            </div>
            <div class="service">
                <img src="./assets/images/service_006.webp" alt="" />
                <h3>Tracking</h3>
                <p>Track and save your medical history and health data</p>
            </div>
        </div>
        <button class="white">Learn more</button>
    </section>

    <section class="two-columns-template reverse">
        <div class="text-content">
            <h2>Leading healthcare providers</h2>
            <p>
                Trafalgar provides progressive, and affordable healthcare, accessible on mobile and online for everyone.
                To us, it’s not just work. We take pride in the solutions we deliver
            </p>
            <button class="white">Learn more</button>
        </div>
        <img src="./assets/images/trafalgar-illustration-sec02-1.webp" alt="" />
    </section>
    <section class="two-columns-template">
        <div class="text-content">
            <h2>Download our mobile apps</h2>
            <p>
                Our dedicated patient engagement app and web portal allow you to access information instantaneously (no
                tedeous form, long calls, or administrative hassle) and securely
            </p>
            <button class="white">
                Download
                <svg width="11" height="16" viewBox="0 0 11 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M4.81951 1.05554L4.81951 12.6308L2.27646 10.0877C1.92569 9.73698 1.39954 9.73698 1.04878 10.0877C0.698014 10.4385 0.698014 10.9647 1.04878 11.3154L5.08258 15.3492C5.43335 15.7 5.95949 15.7 6.31026 15.3492L10.3441 11.3154C10.6948 10.9647 10.6948 10.4385 10.3441 10.0877C9.9933 9.73698 9.46715 9.73698 9.11638 10.0877L6.57333 12.6308L6.57333 1.05554C6.57333 0.617083 6.22257 0.178627 5.69642 0.178627C5.17027 0.178627 4.81951 0.617083 4.81951 1.05554Z"
                        fill="#458FF6"
                    />
                </svg>
            </button>
        </div>
        <img src="./assets/images/trafalgar-illustration-sec03-1.webp" alt="" />
    </section>

    <Testimonials />

    <Footer />
</template>
<script setup lang="ts">
import { onMounted, ref } from 'vue'
import NavigationDesktop from './components/NavigationDesktop.vue'
import NavigationMobile from './components/NavigationMobile.vue'
import Testimonials from './components/Testimonials.vue'
import Footer from './components/Footer.vue'

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
<style scoped lang="scss">
.hero p {
    font-size: 21px;
}
.two-columns-template {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
    gap: 110px;
    padding: 0 5vw;
    margin-top: 122px;

    &.reverse {
        flex-flow: row-reverse wrap;
    }

    .text-content {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 25px;
        width: 100%;
        max-width: 445px;

        button {
            margin-top: 20px;
        }
    }

    img {
        width: 100%;
        max-width: 600px;
        min-width: 300px;
    }
}

.services {
    margin-top: 96px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    .description {
        max-width: 952px;
        text-align: center;
        margin-top: 60px;
    }

    .services-grid {
        margin-top: 80px;
        display: grid;
        gap: 34px;

        @media (min-width: 800px) {
            grid-template-columns: repeat(2, 1fr);
        }
        @media (min-width: 1200px) {
            grid-template-columns: repeat(3, 1fr);
        }

        .service {
            width: 100%;
            max-width: 350px;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            gap: 22px;
            -webkit-box-shadow: 8px 8px 24px 0px rgba(66, 68, 90, 0.09);
            -moz-box-shadow: 8px 8px 24px 0px rgba(66, 68, 90, 0.09);
            box-shadow: 8px 8px 24px 0px rgba(66, 68, 90, 0.09);
            padding: 40px;
            border-radius: 20px;

            h3 {
                font-size: 24px;
                font-weight: 700;
            }
            p {
                font-size: 16px;
                font-weight: 300;
            }
        }
    }
    button {
        margin-top: 72px;
    }
}
</style>
