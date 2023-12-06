<script>
    export default{

    }

</script>

<template>
    <div class="container">
        <i class="fa-solid fa-play"></i>
        <img src="../assets/img/svg/svg-7.svg" class="cart" alt="cart">
        <img src="../assets/img/svg/svg-8.svg" class="circle" alt="circle">
    </div>
</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;
    .container {
        width: 99%;
        height: 100vh;
        background-image: url("../assets/img/img/h1-img-04.jpg");
        background-size: cover;
        position: relative;

        i{
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 2rem;
            color: white;
        }

        img{
            width: 28px;
            position: absolute;
            right: -1%;
            &.cart{
                background-color: white;
                padding: .5rem;
                top: 20px;
            }

            &.circle{
                background-color: #EE2852;
                padding: .27rem;
                top: -15px;
            }
        }

    }


</style>