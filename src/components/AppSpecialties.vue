<script>
export default {
    data() {
        return {
            specialties: [
                {
                    title: "Knowing",
                    text: "Lorem ipsum dolor sit amet, quis consect.",
                    image: "svg-0.svg"
                },
                {
                    title: "Selling",
                    text: "Lorem ipsum dolor sit amet, quis consect.",
                    image: "svg-1.svg"
                },
                {
                    title: "Learning",
                    text: "Lorem ipsum dolor sit amet, quis consect.",
                    image: "svg-2.svg"
                },
                {
                    title: "Contact",
                    text: "Lorem ipsum dolor sit amet, quis consect.",
                    image: "svg-3.svg"
                },

            ]
        }
    },
    methods: {
        getImagePath(img){
            return new URL(`../assets/img/svg/${img}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <div class="container">
        <h2 class="title">Our specialties<span>.</span></h2>
        <p class="subtitle">Lorem ipsum dolor sit amet, consectetur adipiscing elit</p>
        <hr>

        <div class="row">
            <div v-for="specialty in specialties" class="col">
                <img :src="getImagePath(specialty.image)" :alt="specialty.title">
                <h3>{{ specialty.title }}</h3>
                <p>{{ specialty.text }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;

.container {
    width: 90%;
    background-color: white;
    position: relative;
    left: 50%;
    transform: translate(-50%, -10%);
    padding: 5rem;

    .title {
        font-size: 2.3rem;
        text-align: center;
    }

    p {
        text-align: center;
    }


    hr {
        position: relative;
        left: 50%;
        transform: translateX(-50%);
        width: 5%;
    }

    .row {
        margin-top: 2rem;
        display: flex;
        justify-content: space-around;

        .col {
            width: calc(100% / 4 - 6rem);
            text-align: center;
            
            img{
                width: 50%;
            }

            h3{
                font-family: serif;
                margin: 1rem 0;
            }

            p{
                font-size: .9rem;
                color: $gray_text; 
            }
        }
    }

}
</style>