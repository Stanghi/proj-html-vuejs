<script>
export default {
    name: 'AppFooter',
};
</script>

<template>
    <footer>
        <div class="footer-top">
            <div class="container">
                <div class="about">
                    <h3>About</h3>
                    <p>
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Optio incidunt, non
                        magni ut quas aperiam numquam maxime exercitationem at minima. Ullam
                    </p>
                </div>
                <div class="contact">
                    <h3>contact</h3>
                    <p>USA, California 20, First Avenue, California</p>
                    <div>
                        <p>Tel.: +1 212 458 300 32</p>
                        <p>FAX: +1 212 375 24 14</p>
                    </div>
                    <p><a href="#">info@masterstudy.com</a></p>
                </div>
                <div class="social">
                    <h3>social network</h3>
                    <div class="circles">
                        <div class="circle fb">
                            <a href="#">
                                <i class="fa-brands fa-facebook"></i>
                            </a>
                        </div>
                        <div class="circle ins">
                            <a href="#">
                                <i class="fa-brands fa-instagram"></i>
                            </a>
                        </div>
                        <div class="circle li">
                            <a href="#">
                                <i class="fa-brands fa-linkedin"></i>
                            </a>
                        </div>
                        <div class="circle pin">
                            <a href="#">
                                <i class="fa-brands fa-pinterest"></i>
                            </a>
                        </div>
                        <div class="circle twi">
                            <a href="#">
                                <i class="fa-brands fa-twitter"></i>
                            </a>
                        </div>
                        <div class="circle dri">
                            <a href="#">
                                <i class="fa-brands fa-dribbble"></i>
                            </a>
                        </div>
                        <div class="circle gplus">
                            <a href="#">
                                <i class="fa-brands fa-google-plus"></i>
                            </a>
                        </div>
                        <div class="circle sky">
                            <a href="#">
                                <i class="fa-brands fa-skype"></i>
                            </a>
                        </div>
                    </div>
                </div>
                <div class="image">
                    <img src="./assets/images/percent.jpg" alt="percent" />
                </div>
            </div>
        </div>
        <div class="footer-bottom container">
            <div>
                <img src="./assets/images/f-logo.png" alt="logo" />
            </div>
            <p>
                Copyright Ⓒ 2020. <span><a href="#">MasterStudy</a> </span>. Theme by
                <span><a href="">StylemixThemes</a> </span>
            </p>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
@use './style/partials/variables' as *;

footer {
    height: 365px;
    color: $white;
    background-color: $violet;

    .container {
        width: 65%;
        margin: 0 auto;
    }

    .footer-top {
        display: flex;
        align-items: center;
        height: 80%;
        border-bottom: 1px solid #576066;

        .container {
            display: flex;
            justify-content: space-between;
        }

        .about,
        .contact,
        .social,
        .image {
            width: 270px;

            h3 {
                text-transform: uppercase;
                margin-bottom: 25px;
            }

            p {
                line-height: 20px;
                font-size: 0.8rem;
            }

            img {
                width: 100%;
            }
        }

        .contact {
            div {
                margin: 20px 0;
            }
            a {
                text-decoration: none;
                color: $text-gray;
            }
        }

        .social .circles {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            max-width: 215px;

            .circle {
                display: flex;
                justify-content: center;
                align-items: center;
                font-size: 1.3rem;
                width: 45px;
                height: 45px;
                border-radius: 50%;
                margin-bottom: 10px;

                a {
                    text-decoration: none;
                    color: $white;
                }
            }

            .fb {
                background-color: #3b5998;
            }
            .ins {
                background-color: #c32aa3;
            }
            .li {
                background-color: #0077b5;
            }
            .pin {
                background-color: #bd081c;
            }
            .twi {
                background-color: #1da1f2;
            }
            .dri {
                background-color: #ea4c89;
            }
            .gplus {
                background-color: #db4437;
            }
            .sky {
                background-color: #00aff0;
            }
        }
    }

    .footer-bottom {
        display: flex;
        align-items: center;
        height: 20%;
        font-size: 0.9rem;

        div {
            display: flex;
            align-items: center;
            width: 25px;
            margin-right: 20px;

            img {
                width: 100%;
            }
        }

        a {
            font-weight: bold;
            color: $white;
        }
    }
}
</style>
