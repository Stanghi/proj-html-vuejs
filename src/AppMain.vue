<script>
import MainCardComponent from './components/MainCardComponent.vue';
export default {
    name: 'AppMain',
    components: {
        MainCardComponent,
    },
};
</script>

<template>
    <main>
        <div class="band-nav">
            <div>
                <a href="#">
                    <i class="fa-solid fa-chart-line"></i>
                    Business
                </a>
            </div>
            <div>
                <a href="#">
                    <i class="fa-solid fa-palette"></i>
                    Design
                </a>
            </div>
            <div>
                <a href="#">
                    <i class="fa-solid fa-gear"></i>
                    Development
                </a>
            </div>
            <div>
                <a href="#">
                    <i class="fa-regular fa-face-smile"></i>
                    Lifestyle
                </a>
            </div>
            <div>
                <a href="#">
                    <i class="fa-solid fa-wallet"></i>
                    Office Productivity
                </a>
            </div>
        </div>

        <div class="jumbotron">
            <div class="jumbotron-left">
                <div>
                    <h1>Udemy Affiliate Sales</h1>
                    <p>Monetize your audience and attract new customers with Udemy!</p>
                </div>
            </div>
            <div class="jumbotron-right"></div>
        </div>

        <div class="popular-courses">
            <div class="ms-container">
                <h2>Popular Development Courses</h2>
                <div class="cards">
                    <MainCardComponent />
                    <MainCardComponent />
                    <MainCardComponent />
                    <MainCardComponent />
                    <MainCardComponent />
                    <MainCardComponent />
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use './style/partials/variables' as *;

main {
    padding-top: 155px;

    .band-nav {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 80px;
        margin-bottom: 30px;
        background-color: #273044; // VAR

        div {
            display: flex;
            align-items: center;
            padding-right: 60px;

            a {
                text-decoration: none;
                color: $white;

                i {
                    padding-right: 10px;
                    font-size: 1.3rem;
                }
            }

            &:last-child {
                padding-right: 0px;
            }
        }
    }

    .jumbotron {
        display: flex;
        height: 400px;
        margin-bottom: 90px;

        .jumbotron-left {
            display: flex;
            justify-content: flex-end;
            align-items: center;
            width: 50%;
            color: $white;
            background-color: $red;

            div {
                width: 630px;
                h1 {
                    font-size: 3.3rem;
                    font-weight: bold;
                }
                p {
                    font-size: 1.5rem;
                }
            }
        }

        .jumbotron-right {
            width: 50%;
            background-image: url('./assets/images/slide-1.jpg');
            background-repeat: no-repeat;
            background-size: cover;
            background-position: center;

            &::before {
                content: '';
                position: absolute;
                border-left: 180px solid $red;
                border-top: 400px solid transparent;
            }
        }
    }

    .popular-courses {
        padding-bottom: 85px;
        h2 {
            margin-bottom: 35px;
        }

        .cards {
            display: flex;
            justify-content: space-between;
        }
    }
}
</style>
