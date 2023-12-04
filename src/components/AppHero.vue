<script>

export default {

}

</script>

<template>
    <div class="hero-wrap">

        <div class="arrow left">
            &leftarrow;
        </div>
        <div class="internal-hero">
            <div>
                <h1 class="title">Our Team<span>.</span></h1>
                <p class="subtitle">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse pariatur quidem, cupiditate omnis.
                </p>
                <button class="btn-white">READ MORE <span>| &RightArrow;</span></button>
                <button class="btn-orange">PURCHASE <span>| &RightArrow;</span></button>
            </div>
        </div>
        <div class="arrow right">
            &rightarrow;
        </div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;

.hero-wrap {
    background-image: url("../assets/img/img/rev-slider-main-home-img-03.jpg");
    background-size: cover;
    height: 650px;
    .internal-hero {
        position: relative;
        top: 60%;
        transform: translateY(-50%);
        width: 70%;
        margin: 0 auto;
        div {
            width: 40%;
            .title {
                font-size: 4rem;
            }

            button {
                padding: .5rem;
                border-radius: 0;
                border: 0;
                margin-top: 2rem;
                margin-right: .5rem;
                font-size: .7rem;
                font-weight: bold;
                span {
                    font-size: 1.2rem;
                    font-weight: 100;
                }
                

                &.btn-orange{
                    background-color: $main_color;
                    color: white;
                }

                &.btn-white{
                    background-color: white;
                }
            }
        }


    }
    
    .arrow{
        font-size: 1.8rem;
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        &.left{
            left: 2.5%;
        }
        &.right{
            right: 2.5%;
        }
    }

}
</style>