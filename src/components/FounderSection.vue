<script>
export default {
    data() {
        return{
            team: [
                {
                    name: "Jason Bickford",
                    profession: "Founder and Executive Director",
                    photo: "h1-img-01.jpg",
                    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Deserunt possimus deleniti natus, perferendis...",
                    signature: "signature_JBickford.png"
                },
                {
                    name: "Yù Wang",
                    profession: "Project Manager",
                    photo: "h1-img-02.jpg",
                    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Deserunt possimus deleniti natus, perferendis...",
                    signature: "signature_YWang.png"
                },
                {
                    name: "Aaron Loeb",
                    profession: "Director of Solutions",
                    photo: "h1-img-03.jpg",
                    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Deserunt possimus deleniti natus, perferendis...",
                    signature: "signature_ALoeb.png"
                }
            ],
            index: 0
        }
    },
    methods: {
        getImagePath(img) {
            return new URL(`../assets/img/img/${img}`, import.meta.url).href;
        },
        next(){
            if(this.index < this.team.length - 1) {
                this.index++;
            }else{
                this.index = 0;
            }
        },
        prev(){
            if(this.index == 0){
                this.index = this.team.length-1;
            }else{
                this.index--;
            }
        }
    }

}
</script>

<template>
    <div class="container">
        <img :src="getImagePath(team[index].photo)" alt="">
        <div class="founder-card">
            <h2 class="title">{{ team[index].name }}</h2>
            <p class="subtitle">
                <small>{{ team[index].profession }}</small>
            </p>
            <hr>

            <p class="description">
                {{ team[index].description }}
            </p>
            
            <div class="social">
                <i class="fa-brands fa-linkedin-in"></i>
                <i class="fa-brands fa-facebook-f"></i>
                <i class="fa-brands fa-twitter"></i>
            </div>

            <div class="signature">
                <img :src="getImagePath(team[index].signature)" alt="">
            </div>
        </div>

        <button @click="prev()" class="square-arrow left">
            &LeftArrow;
        </button>

        <button @click="next()" class="square-arrow right">
            &RightArrow;
        </button>

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

        .social{
            .fa-brands{
                margin-right: .5rem;
                font-size: .6rem;
                width: 1.4rem;
                text-align: center;
                padding: .4rem;
                background-color: $main_color;
                border-radius: 50%;
                color: white;
            }
        }

        .signature {
            text-align: right;
            position: relative;
            top: -1rem;
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
        border: 0;
        &.left{
            left: 0;
        }

        &.right{
            left: 3rem;
        }
    }
}</style>