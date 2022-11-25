<script>
export default {
    name: 'HeaderBottomComponent',
};
</script>

<template>
    <div class="header-bottom">
        <div class="ms-container bottom">
            <div class="logo">
                <a href="#">
                    <img src="../assets/images/MasterStudy.svg" alt="MasterStudy.svg" />
                </a>
            </div>

            <div class="search-bar">
                <div class="select-category">
                    <a href="#">
                        <i class="fa-solid fa-bars"></i>
                        category
                    </a>
                </div>

                <input type="text" placeholder="Search courses" />
                <button class="lens">
                    <i class="fa-sharp fa-solid fa-magnifying-glass"></i>
                </button>
            </div>

            <div class="bullhorn">
                <a href="#">
                    <i class="fa-solid fa-bullhorn"></i>
                    Become an instructor
                </a>
            </div>

            <div class="enterprise">
                <a href="#">
                    <i class="fa-solid fa-briefcase"></i>
                    For enterprise
                </a>
            </div>

            <div class="log-in">
                <a href="#">
                    <i class="fa-regular fa-user"></i>
                    Log in
                </a>
            </div>

            <button class="ms-btn">
                <a href="#"> Sign up </a>
            </button>

            <div>
                <a href="#"><i class="fa-regular fa-bookmark"></i></a>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;

.header-bottom {
    display: flex;
    align-items: center;
    height: calc(100% - 50px);

    .ms-container.bottom {
        display: flex;
        align-items: center;
        justify-content: space-between;

        .select-category a,
        .bullhorn a,
        .enterprise a,
        .log-in a {
            text-decoration: none;
            color: $text-gray;
        }

        div i {
            margin-right: 10px;
        }

        .logo {
            margin-right: 40px;
        }

        .search-bar {
            display: flex;
            align-items: center;
            margin-right: 60px;

            .select-category {
                font-size: 0.78rem;
                text-transform: uppercase;
                font-weight: bold;
                margin-right: 10px;

                i {
                    margin-right: 0px;
                }
            }

            input {
                width: 510px;
                height: 45px;
                border: none;
                outline: none;
                padding-left: 15px;
                background-color: $input-background;
            }

            .lens {
                cursor: pointer;
                display: flex;
                justify-content: center;
                align-items: center;
                border: none;
                width: 60px;
                height: 45px;
                color: $white;
                background-color: $light-violet;

                i {
                    margin-right: 0px;
                }
            }
        }

        .bullhorn {
            margin-right: 25px;
        }

        .log-in {
            margin-left: 75px;
        }

        .fa-bookmark {
            color: $text-gray;
            margin-right: 0px;
            font-size: 1.5rem;
        }
    }
}
</style>
