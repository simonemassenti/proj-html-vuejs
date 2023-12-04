<script>
export default {

}
</script>

<template>
    <div class="container">
        <img src="../assets/img/img/h1-blog-img-04.jpg" alt="">
        <div class="founder-card">
            <h2 class="title">Jason Bickford</h2>
            <p class="subtitle">
                <small>Founder and Executive Director</small>
            </p>
            <hr>

            <p class="description">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Deserunt possimus deleniti natus, perferendis aliquam tenetur sunt...
            </p>

            <div class="signature">
                <img src="../assets/img/img/signature.png" alt="">
            </div>
        </div>

        <div class="square-arrow left">
            &LeftArrow;
        </div>

        <div class="square-arrow right">
            &RightArrow;
        </div>

        <img class="decoration" src="../assets/img/svg/svg-4.svg" alt="">
    </div>
    <div class="debug"></div>
</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;

.container {
    width: 70%;
    display: flex;
    margin: 5rem 0;
    position: relative;
    left: 50%;
    transform: translateX(-50%);

    img {
        width: 50%;
    }

    .founder-card {
        font-size: 1.5rem;
        width: 50%;
        padding: 3rem;
        position: absolute;
        right: 8%;
        top: 50%;
        transform: translateY(-50%);
        background-color: white;

        p.subtitle {
            margin: 0;
        }

        hr {
            width: 30%;
            margin-top: .5rem;
        }

        p.description {
            font-size: .8rem;
            margin: .5rem 0;
            line-height: 1.3rem;
            color: $gray_text;
        }

        .signature {
            text-align: right;
            margin-top: .5rem;

            img {
                width: 30%;
            }
        }
    }

    .decoration {
        position: absolute;
        scale: .70;
        right: -15%;
        top: -45%;
        z-index: -1;
    }

    .square-arrow {
        display: inline;
        width: 3rem;
        height: 3rem;
        background-color: $main_color;
        text-align: center;
        line-height: 3rem;
        position: absolute;
        bottom: 0;
        color: white;
        &.left{
            left: 0;
        }

        &.right{
            left: 3rem;
        }
    }
}</style>