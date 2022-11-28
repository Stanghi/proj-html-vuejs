<script>
import headerLinks from '../data/header-links.js';
import headerSocials from '../data/header-socials.js';
export default {
    name: 'HeaderTopComponent',
    data() {
        return {
            headerLinks,
            headerSocials,
        };
    },
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
                        <li v-for="(link, index) in headerLinks" :key="index">
                            <a :href="link.url">{{ link.name }}</a>
                        </li>
                    </ul>
                </div>
                <div class="socials">
                    <ul>
                        <li v-for="(social, index) in headerSocials" :key="index">
                            <a :href="social.url"><i class="fa-brands" :class="social.name"></i></a>
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
