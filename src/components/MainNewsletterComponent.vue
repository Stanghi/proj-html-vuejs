<script>
export default {
    name: 'MainNewsletterComponent',
};
</script>

<template>
    <div class="newsletter">
        <div class="text">
            <h3>Subscribe our newsletter</h3>
            <p>
                There are many variations of passages of Lorem Ipsum available, but the majority
                have suffered alteration in some form, by injected humor, or randomised words
            </p>
        </div>
        <div class="input">
            <p>Your e-mail address</p>
            <div>
                <input type="text" placeholder="Enter your E-mail" />
                <button class="btn-subscribe">subscribe</button>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;

.newsletter {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 170px;
    color: $white;
    background-color: $red;

    .text {
        display: flex;
        justify-content: flex-end;
        flex-direction: column;
        width: 670px;

        h3 {
            margin-bottom: 10px;
        }
    }

    .input {
        width: 505px;

        p {
            margin-bottom: 10px;
            text-transform: uppercase;
            font-size: 0.9rem;
        }

        div {
            display: flex;
            input {
                width: 340px;
                height: 45px;
                border: none;
                outline: none;
                padding-left: 15px;
                background-color: $white;
            }

            .btn-subscribe {
                cursor: pointer;
                padding: 0 25px;
                border: none;
                height: 45px;
                text-transform: uppercase;
                color: $white;
                background-color: $light-violet;
            }
        }
    }
}
</style>
