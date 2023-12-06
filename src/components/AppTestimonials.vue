<script>
export default {
    data() {
        return {
            testimonials: [
                {
                    name: "Cynthia Clark",
                    photo: "04",
                    phrase: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum dolor esse, rem labore exercitationem."
                },
                {
                    name: "Samai Thongkham",
                    photo: "07",
                    phrase: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum dolor esse, rem labore exercitationem."
                },
                {
                    name: "Breana Walsh",
                    photo: "08",
                    phrase: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum dolor esse, rem labore exercitationem."
                }
            ],
            index: 0
        }
    },
    methods: {
        getImagePath(img) {
            return new URL(`../assets/img/img/h3-img-${img}.png`, import.meta.url).href;
        },
        next(){
            if(this.index < this.testimonials.length - 1) {
                this.index++;
            }else{
                this.index = 0;
            }
        },
        prev(){
            if(this.index == 0){
                this.index = this.testimonials.length-1;
            }else{
                this.index--;
            }
        }
    }
}
</script>

<template>
    <div class="wrap">
        <div class="container">
            <div class="title giant">
                Testimonials.
            </div>

            <div class="testimonial">
                <img :src="getImagePath(testimonials[index].photo)" :alt="testimonials[index].name">
                <h3 class="name">{{ testimonials[index].name }}</h3>
                <p class="phrase">
                    "{{ testimonials[index].phrase }}"
                </p>

                <div class="slider-page">
                    <span>01</span>
                    <hr :class="index == 0 ? 'active' : ''" class="one">
                    <hr :class="index == 1 ? 'active' : ''" class="two">
                    <hr :class="index == 2 ? 'active' : ''" class="three">
                    <span>03</span>
                </div>

                <button @click="prev()" class="square-arrow left">
                    &xlarr;
                </button>

                <button @click="next()" class="square-arrow right">
                    &xrarr;
                </button>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;

.wrap {
    padding-bottom: 13rem;
    background-color: $bg_testimonials;

    .container {
        text-align: center;
        width: 70%;
        margin: 0 auto;
        position: relative;

        .giant {
            line-height: 9rem;
            font-size: 11rem;
            color: $testimonials_title;
            font-weight: bold;
        }
    }

    .testimonial {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%);

        img {
            border-radius: 50%;
            scale: .65;
            border: 4px solid white;
            margin: 0;
        }

        .name {
            font-family: serif;
            font-size: .9rem;
            color: white;
            margin-bottom: 1.3rem;
            line-height: 0rem;
        }

        p {
            font-family: serif;
            margin: 0 auto;
            color: white;
            font-size: 1rem;
        }

        .slider-page {
            display: flex;
            justify-content: center;
            margin-top: 1rem;

            span {
                color: white;
                font-size: .6rem;
                line-height: 2rem;
            }

            hr {
                width: 7%;
                height: 0;
                border: 1px solid #555555;

                &.active {
                    border: 1px solid white;
                }

                &.one {
                    margin-left: .3rem;
                }

                &.three {
                    margin-right: .3rem;
                }
            }

            
        }

        .square-arrow{
            background-color: $bg_testimonials;
            color: white;
            font-size: 1.5rem;
            position: absolute;
            top: 50%
        }

        .left{
            left: -80%;
        }

        .right{
            right: -80%;
        }
    }


}
</style>