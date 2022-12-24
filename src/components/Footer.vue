<template>
    <footer>
        <div class="column">
            <img src="../assets/logo.svg" alt="Trafalgar" />
            <p class="text">
                Trafalgar provides progressive, and affordable healthcare, accessible on mobile and online for everyone
            </p>
            <span>©Trafalgar PTY LTD 2020. All rights reserved</span>
        </div>
        <div class="columns-container">
            <div class="column">
                <span class="title">Company</span>
                <ul>
                    <li>About</li>
                    <li>Testimonials</li>
                    <li>Find a doctor</li>
                    <li>Apps</li>
                </ul>
            </div>
            <div class="column">
                <span class="title">Region</span>
                <ul>
                    <li>Indonesia</li>
                    <li>Singapore</li>
                    <li>Hongkong</li>
                    <li>Canada</li>
                </ul>
            </div>
            <div class="column">
                <span class="title">Help</span>
                <ul>
                    <li>Help center</li>
                    <li>Contact support</li>
                    <li>Instructions</li>
                    <li>How it works</li>
                </ul>
            </div>
        </div>
    </footer>
</template>
<style scoped lang="scss">
footer {
    display: flex;
    flex-flow: row wrap;
    background: linear-gradient(183.41deg, #67c3f3 -8.57%, #5a98f2 82.96%);
    padding: 100px 5vw;
    justify-content: space-evenly;
    gap: 80px;
    margin-top: 200px;

    .columns-container {
        display: flex;
        flex-flow: row wrap;
        gap: 80px;
    }

    .column {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 22px;
        width: max-content;
        max-width: 390px;

        p,
        ul,
        span,
        li {
            font-size: 18px;
            font-weight: 300;
            line-height: 28px;
            color: white;
            line-height: 1.4;
        }

        .title {
            font-weight: 700;
        }

        img {
            height: 41px;
        }

        ul {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
    }
}
</style>
