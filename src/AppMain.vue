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

        <div class="limitless">
            <div class="text">
                <h2>Limitless learning, more possibilities</h2>
                <p>
                    Online courses open the opportunity for learning to almost anyone, regardless of
                    their scheduling commitments.
                </p>
                <button class="ms-btn">
                    <a href="#"> Read more </a>
                </button>
            </div>
        </div>

        <div class="recent-courses ms-container">
            <h2>Recent courses</h2>
            <div class="nav-categories">
                <span class="active">
                    <a href="#"> All categories </a>
                </span>
                <span :class="active && 'active'">
                    <a href="#"> Business </a>
                </span>
                <span :class="active && 'active'">
                    <a href="#"> Design </a>
                </span>
                <span :class="active && 'active'">
                    <a href="#"> Development </a>
                </span>
                <span :class="active && 'active'">
                    <a href="#"> IT & Software </a>
                </span>
                <span :class="active && 'active'">
                    <a href="#"> Lifestyle </a>
                </span>
                <span :class="active && 'active'">
                    <a href="#"> Marketing </a>
                </span>
                <span :class="active && 'active'">
                    <a href="#"> Office Productivity </a>
                </span>
            </div>

            <div class="cards">
                <MainCardComponent />
                <MainCardComponent />
                <MainCardComponent />
                <MainCardComponent />
                <MainCardComponent />
                <MainCardComponent />
                <MainCardComponent />
                <MainCardComponent />
                <MainCardComponent />
                <MainCardComponent />
                <MainCardComponent />
                <MainCardComponent />
            </div>

            <button class="ms-btn">
                <a href="#"> Show all </a>
            </button>
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
        background-color: $violet;

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
        padding-bottom: 30px;
        h2 {
            margin-bottom: 35px;
            color: $violet;
        }
    }

    .limitless {
        position: relative;
        height: 530px;
        margin-bottom: 105px;
        background-image: url('./assets/images/bg.png');
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;

        .text {
            position: absolute;
            top: 50%;
            right: 50%;
            transform: translate(0, -50%);
            width: 540px;
            color: $violet;

            h2 {
                font-size: 3rem;
                padding-bottom: 30px;
            }

            p {
                font-weight: bold;
                padding-bottom: 50px;
            }
        }
    }

    .recent-courses {
        display: flex;
        align-items: center;
        flex-direction: column;
        padding-bottom: 110px;

        h2 {
            font-size: 3rem;
            margin-bottom: 40px;
            color: $violet;
        }

        .nav-categories {
            margin-bottom: 55px;

            span {
                padding: 10px 15px;
                margin-right: 15px;

                a {
                    text-decoration: none;
                    color: #937992; // VAR
                }

                &:last-child {
                    margin-right: 0px;
                }
            }

            .active {
                background-color: #f0f4fa;
                border-radius: 30px;
            }
        }

        .cards {
            margin-bottom: 30px;
        }
    }
}
</style>
