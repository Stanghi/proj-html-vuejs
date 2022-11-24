<script>
export default {
    name: 'HeaderTopComponent',
};
</script>

<template>
    <div class="header-top">
        <div class="ms-container top">
            <div class="select-language">
                <select name="language" id="language">
                    <option value="en" selected>English</option>
                    <option value="it">Italiano</option>
                    <option value="es">Español</option>
                    <option value="fr">Français</option>
                </select>
            </div>
            <div class="ms-nav">
                <div class="links">
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#">Page</a></li>
                        <li><a href="#">Course Formats</a></li>
                        <li><a href="#">Courses</a></li>
                        <li><a href="#">Demos</a></li>
                    </ul>
                </div>
                <div class="socials">
                    <ul>
                        <li>
                            <a href="#"><i class="fa-brands fa-facebook"></i></a>
                        </li>
                        <li>
                            <a href="#"><i class="fa-brands fa-twitter"></i></a>
                        </li>
                        <li>
                            <a href="#"><i class="fa-brands fa-instagram"></i></a>
                        </li>
                        <li>
                            <a href="#"><i class="fa-brands fa-linkedin"></i></a>
                        </li>
                        <li>
                            <a href="#"><i class="fa-brands fa-google-plus"></i></a>
                        </li>
                        <li>
                            <a href="#"><i class="fa-brands fa-youtube"></i></a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;
.header-top {
    display: flex;
    align-items: center;
    height: 50px;
    border-bottom: 1px solid #e2e2e2;
    font-size: 0.9rem;

    .ms-container.top {
        display: flex;
        align-items: center;
        justify-content: space-between;

        .select-language select {
            border: none;
            outline: none;
            color: $text-light-gray;
        }

        .ms-nav {
            display: flex;

            .links ul,
            .socials ul {
                display: flex;
                list-style: none;
                padding: 0;
                margin: 0;

                a {
                    text-decoration: none;
                    color: $text-light-gray;
                }
            }

            .links ul li {
                padding-right: 30px;
            }

            .socials ul li {
                padding-right: 15px;

                &:last-child {
                    padding-right: 0px;
                }
            }
        }
    }
}
</style>
