<script>
import AppCardNews from './AppCardNews.vue';

export default {
    components: {
        AppCardNews
    },
    data() {
        return {
            news: [
                {
                    date: "May 5, 2019",
                    author: "Amanda Doe",
                    title: "Next investment",
                    preview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed eius mas tellus dolor ...",
                    theme: "Business, Leading",
                    image: "01"
                },
                {
                    date: "May 5, 2019",
                    author: "Amanda Doe",
                    title: "Team Building",
                    preview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed eius mas tellus dolor ...",
                    theme: "Business, Leading",
                    image: "02"
                },
                {
                    date: "May 5, 2019",
                    author: "Amanda Doe",
                    title: "New Business Day",
                    preview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed eius mas tellus dolor ...",
                    theme: "Business, Leading",
                    image: "03"
                },
                {
                    date: "May 5, 2019",
                    author: "Amanda Doe",
                    title: "Build a Business",
                    preview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed eius mas tellus dolor ...",
                    theme: "Business, Leading",
                    image: "04"
                }
            ],
            indexes: [0, 1, 2]
        }
    },
    methods: {
        next() {
            for (let i = 0; i < this.indexes.length; i++) {
                this.indexes[i]++;
                if (this.indexes[i] > this.news.length - 1) {
                    this.indexes[i] = 0;
                }
            }
        },
        prev() {
            for (let i = 0; i < this.indexes.length; i++) {
                this.indexes[i]--;
                if (this.indexes[i] < 0) {
                    this.indexes[i] = this.news.length - 1;
                }
            }
        }
    }
}
</script>

<template>
    <div class="wrapper">
        <div class="container">
            <div class="top">
                <h2 class="title">Latest news<span>.</span></h2>
                <p class="subtitle">Lorem ipsum dolor sit amet consectetur, adipisicing elit.</p>
                <hr>
            </div>


            <div class="card-container">
                <AppCardNews class="card" :article="news[indexes[0]]" />
                <AppCardNews class="card" :article="news[indexes[1]]" />
                <AppCardNews class="card" :article="news[indexes[2]]" />

                <button class="square-arrow left" @click="prev()">&xlarr;</button>
                <button class="square-arrow right" @click="next()">&xrarr;</button>
            </div>
            
        </div>

        <img class="decoration" src="../assets/img/svg/svg-4.svg" alt="">
    </div>
</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;

.wrapper {
    background-color: $bg_lightgray;
    position: relative;
    .container {
        width: 70%;
        margin: 0 auto;
        padding: 4rem 0;
        z-index: 1;
        .top {
            text-align: center;

            h2 {
                font-size: 2rem;
            }

            hr {
                width: 5%;
                margin: 1rem auto 0;
            }
        }

        .card-container {
            display: flex;
            position: relative;

            .card {
                width: calc(100% / 3 - 1rem);
            }

            .square-arrow {
                position: absolute;
                background-color: $bg_lightgray;
                top: 50%;
                transform: translateY(-50%);
                font-size: 1.5rem;

                &.left {
                    left: -10%;
                }

                &.right {
                    right: -10%;
                }
            }
        }
    }

    .decoration {
        position: absolute;
        scale: .70;
        z-index: 0;
        top: -20%;
    }
}
</style>