<script>
export default {
    name: 'MainCardComponent',
};
</script>

<template>
    <div class="card">
        <img src="../assets/images/ios10.jpg" alt="ios10" />
        <div class="content">
            <div class="content-text">
                <p>Development ></p>
                <p>The complete IOS 10 & Swift 3 Developer Course</p>
            </div>
            <div class="card-bottom">
                <div class="rating-star">
                    <img src="../assets/images/starfull.svg" alt="starfull" />
                    <img src="../assets/images/starfull.svg" alt="starfull" />
                    <img src="../assets/images/starfull.svg" alt="starfull" />
                    <img src="../assets/images/starfull.svg" alt="starfull" />
                    <img src="../assets/images/staremptyl.svg" alt="staremptyl" />
                </div>

                <div class="price">
                    <p>$ 199.99</p>
                    <p>$ 100</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;

.card {
    width: 270px;
    min-height: 360px;
    border: 1px solid #e2e2e2;

    img:first-child {
        width: 100%;
        height: 180px;
    }

    .content {
        padding: 20px;
        height: calc(100% - 180px);

        .content-text {
            padding-bottom: 20px;
            border-bottom: 1px solid #e2e2e2;

            p:first-child {
                margin-bottom: 20px;
                font-size: 0.9rem;
                color: $text-light-gray;
            }

            p:last-child {
                word-wrap: break-word;
            }
        }

        .card-bottom {
            display: flex;
            justify-content: space-between;
            height: 50px;

            .rating-star img {
                height: 100%;
                width: 15px;
            }

            .price {
                display: flex;
                justify-content: center;
                align-items: flex-end;
                flex-direction: column;

                p:first-child {
                    text-decoration: line-through;
                    font-size: 0.8rem;
                    color: $text-light-gray;
                }

                p:last-child {
                    font-weight: bold;
                    font-size: 0.9rem;
                }
            }
        }
    }
}
</style>
