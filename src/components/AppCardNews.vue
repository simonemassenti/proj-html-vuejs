<script>
export default {
    props: {
        article: Object
    },
    methods: {
        getImagePath(img) {
            return new URL(`../assets/img/img/h1-blog-img-${img}.jpg`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <div class="container">
        <img :src="getImagePath(article.image)" :alt="article.title">
        <small class="subtitle">
            <i class="fa-regular fa-clock"></i>
            {{ article.date }}
            <i class="fa-regular fa-user"></i>
            {{ article.author }}
        </small>
        <h2 class="title">{{ article.title }}</h2>
        <p class="subtitle">{{ article.preview }}</p>
        
        <div class="theme">
            <i class="fa-solid fa-tag"></i>
            {{ article.theme }}
        </div>

        <button class="btn-rm">READ MORE</button>


    </div>
</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;
.container{
    position: relative;

    img{
        width: 100%;
    }

    small{
        font-size: .6rem;
    }

    p{
        margin: 0;
        font-size: .8rem;
        line-height: 1.3rem;
    }

    .theme{
        font-size: .6rem;
        background-color: $main_color;
        color: white;
        display: block;
        width: 40%;
        padding: .5rem;
        text-align: center;
        position: absolute;
        top: 55%;
        right: 5%;
        i{
            color: inherit;
        }
    }
}

</style>