<script>
import MainCardComponent from './components/MainCardComponent.vue';
import MainNewsletterComponent from './components/MainNewsletterComponent.vue';
import coursesDataBase from './data/courses.js';
import categories from './data/categories.js';

export default {
    name: 'AppMain',
    components: {
        MainCardComponent,
        MainNewsletterComponent,
    },
    data() {
        return {
            coursesDataBase,
            categories,
            showAll: false,
            page: 1,
            NumberOfPages: Math.ceil(coursesDataBase.length / 6),
            coursesDataBase2: [...coursesDataBase],
        };
    },
    methods: {
        showHideCourses() {
            this.showAll = !this.showAll;
        },

        toggleCategory(i) {
            for (let cat of categories) {
                cat.active = false;
            }
            this.categories[i].active = true;

            if (this.categories[i].name === 'All categories') {
                this.coursesDataBase2 = this.coursesDataBase;
            } else {
                this.coursesDataBase2 = this.coursesDataBase.filter(
                    (item) => item.category === this.categories[i].name
                );
            }
        },

        nextPrev(value) {
            if (value === 'prev') {
                if (this.page > 1) {
                    this.page--;
                } else {
                    this.page = 1;
                }
            } else {
                if (this.page < this.NumberOfPages) {
                    this.page++;
                }
            }
            console.log(this.page);
        },
    },
};
</script>

<template>
    <main>
        <div class="fixed-menu">
            <i class="fa-solid fa-desktop"></i>
            <i class="fa-solid fa-life-ring"></i>
            <i class="fa-solid fa-wrench"></i>
            <i class="fa-solid fa-cart-shopping"></i>
            <i class="fa-solid fa-mobile-screen-button"></i>
        </div>

        <section class="band-nav">
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
        </section>

        <section class="jumbotron">
            <div class="jumbotron-left">
                <div>
                    <h1>Udemy Affiliate Sales</h1>
                    <p>Monetize your audience and attract new customers with Udemy!</p>
                </div>
            </div>
            <div class="jumbotron-right"></div>
        </section>

        <section class="popular-dev-courses ms-container">
            <h2>Popular Development Courses</h2>
            <div class="cards">
                <MainCardComponent
                    v-for="course in coursesDataBase"
                    v-show="course.category === 'Development'"
                    :key="course.id"
                    :course="course"
                />
            </div>
        </section>

        <section class="limitless">
            <div class="content">
                <h2>Limitless learning, more possibilities</h2>
                <p>
                    Online courses open the opportunity for learning to almost anyone, regardless of
                    their scheduling commitments.
                </p>
                <button class="ms-btn">
                    <a href="#"> Read more </a>
                </button>
            </div>
        </section>

        <section class="recent-courses ms-container">
            <h2>Recent courses</h2>
            <div class="nav-categories">
                <span
                    v-for="(category, index) in categories"
                    :key="index"
                    :class="category.active && 'active'"
                    @click="toggleCategory(index)"
                >
                    <p>{{ category.name }}</p>
                </span>
            </div>

            <div class="cards">
                <template v-for="(course, index) in coursesDataBase2" :key="course.id">
                    <MainCardComponent v-show="showAll ? true : index < 12" :course="course" />
                </template>
            </div>

            <button @click="showHideCourses()" v-if="coursesDataBase2.length > 12" class="ms-btn">
                <p v-if="!showAll">Show all</p>
                <p v-else>Hide</p>
            </button>
            <h3 v-else-if="coursesDataBase2.length === 0">Nothing found</h3>
        </section>

        <MainNewsletterComponent />

        <section class="popular-courses">
            <div class="ms-container">
                <h2>Popular courses</h2>
                <p>Discover our most popular courses for self learning</p>

                <div class="cards">
                    <MainCardComponent
                        v-for="course in coursesDataBase"
                        :key="course.id"
                        v-show="course.id / 6 <= page && Math.ceil(course.id / 6) >= page"
                        :course="course"
                    />
                </div>

                <div>
                    <button @click="nextPrev('prev')">
                        <i class="fa-solid fa-chevron-left"></i>
                    </button>
                    <button @click="nextPrev('next')">
                        <i class="fa-solid fa-chevron-right"></i>
                    </button>
                </div>
            </div>
        </section>

        <section class="become-access ms-container">
            <div class="box">
                <img src="./assets/images/instructor.png" alt="instructor" />
                <div>
                    <h2>Become an instructor</h2>
                    <p>Teach what you love. Masterstudy gives you the tools to create a course.</p>
                    <button class="ms-btn">
                        <a href="#"> Start teaching </a>
                    </button>
                </div>
            </div>
            <div class="box">
                <img src="./assets/images/business.png" alt="business" />
                <div>
                    <h2>Access For Business</h2>
                    <p>Get unlimited access to 2,500 of top courses for yout team.</p>
                    <button class="ms-btn">
                        <a href="#"> doing business </a>
                    </button>
                </div>
            </div>
        </section>

        <section class="testimonial">
            <div>
                <h2>Investing for Your Future</h2>
                <p>
                    It is no exaggeration to say this MasterStudy experience was transformative-both
                    professionally and personally. This workshop will long remain a high point of my
                    life. Thanks again.... I am feeling energized and eager to start teaching my
                    class next week. I can't wait to use all of my new teaching tools. I will
                    absolutely recommend this workshop to other educators!
                </p>
                <span>
                    <h3>Linda Green</h3>
                    <p>Procuct Manager, Apple Inc</p>
                </span>
            </div>
        </section>
    </main>
</template>

<style lang="scss" scoped>
@use './style/partials/variables' as *;

main {
    padding-top: 155px;

    .fixed-menu {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        position: fixed;
        z-index: 999;
        bottom: 0;
        right: 0;
        width: 65px;
        height: 280px;
        padding: 20px 25px;
        box-shadow: 0px 0px 19px -7px rgba(0, 0, 0, 0.8);
        background-color: $white;

        i {
            cursor: pointer;
            font-size: 1.4rem;
            color: $violet;
        }
    }

    .band-nav {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 80px;
        margin-bottom: 30px;
        background-color: $violet;

        div {
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
                    margin-bottom: 30px;
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

    .popular-dev-courses {
        margin-bottom: 30px;

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

        .content {
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
        margin-bottom: 110px;
        color: $violet;

        h2 {
            font-size: 3rem;
            margin-bottom: 40px;
        }

        .nav-categories {
            display: flex;
            margin-bottom: 55px;

            span {
                padding: 10px 15px;
                margin-right: 15px;

                p {
                    cursor: pointer;
                    color: #937992; //? VAR
                }

                &:last-child {
                    margin-right: 0px;
                }
            }

            .active {
                background-color: #f0f4fa; //? var
                border-radius: 30px;
            }
        }

        .cards {
            margin-bottom: 30px;
        }
    }

    .popular-courses {
        padding-top: 105px;
        margin-bottom: 75px;
        background-color: #f0f4fa; //? var

        .ms-container {
            display: flex;
            align-items: center;
            flex-direction: column;

            h2 {
                font-size: 3rem;
                margin-bottom: 15px;
                color: $violet;
            }

            p {
                margin-bottom: 50px;
                color: $violet;
            }
        }

        button {
            cursor: pointer;
            border: 1px solid #e0e0e0; //? var
            background-color: $white;
            width: 45px;
            height: 45px;
            margin-bottom: 75px;
            color: #e0e0e0; //? var

            &:hover {
                background-color: $light-violet;
            }
        }
    }

    .become-access {
        display: flex;
        align-items: center;
        padding-bottom: 70px;

        .box {
            display: flex;
            align-items: center;
            width: 855px;
            height: 375px;
            border: 1px solid #e2e2e2; //? VAR

            img {
                margin: 0 40px;
            }

            div {
                width: 360px;

                h2 {
                    font-size: 2rem;
                    padding-bottom: 30px;
                    color: $violet;
                }

                p {
                    padding-bottom: 30px;
                }

                button:hover {
                    background-color: #46c197; //? VAR
                }
            }

            &:first-child {
                margin-right: 30px;
            }
        }
    }

    .testimonial {
        position: relative;
        height: 670px;
        background-image: url('./assets/images/testimonial.jpg');
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;

        div {
            position: absolute;
            top: 50%;
            left: 370px;
            transform: translate(0, -50%);
            width: 740px;
            height: 530px;
            padding: 100px;
            color: $violet;
            background-color: $white;

            h2 {
                margin-bottom: 30px;
                font-size: 2.2rem;
            }

            p {
                margin-bottom: 50px;
                line-height: 30px;
            }

            &::before {
                content: '';
                position: absolute;
                top: 50%;
                right: -25px;
                transform: translate(0, -50%);
                width: 0;
                height: 0;
                border-style: solid;
                border-width: 17.5px 0 17.5px 25px;
                border-color: transparent transparent transparent $white;
            }
        }
    }
}
</style>
