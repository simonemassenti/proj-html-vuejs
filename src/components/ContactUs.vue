<script>
export default {
    data() {
        return{
            ny: true,
            mb: false,
            ln: false
        }
    },
    methods: {
        showEvent(city) {
            switch(city){
                case 'ny': 
                    this.ny=true;
                    this.mb=false;
                    this.ln=false;
                    break;
                case 'mb':
                    this.ny=false;
                    this.mb=true;
                    this.ln=false;
                    break;
                case 'ln':
                    this.ny=false;
                    this.mb=false;
                    this.ln=true;
                    break;
            }
        }
    }


}
</script>

<template>
    <div class="container">
        <div class="events">
            <img class="world" src="../assets/img/img/h1-contact-rev-01.png" alt="">
            <img @click="showEvent('ny')" class="event newyork" src="../assets/img/img/h1-contact-rev-02.png" alt="">
            <div v-show="ny" class="info-ny">
                <h4 class="title">New York Coaching</h4>
                <button class="btn-rm">READ MORE</button>
            </div>
            <img @click="showEvent('mb')" class="event melbourne" src="../assets/img/img/h1-contact-rev-02.png" alt="">
            <div v-show="mb" class="info-mb">
                <h4 class="title">Melbourne Coaching</h4>
                <button class="btn-rm">READ MORE</button>
            </div>
            <img @click="showEvent('ln')" class="event london" src="../assets/img/img/h1-contact-rev-02.png" alt="">
            <div v-show="ln" class="info-ln">
                <h4 class="title">London Coaching</h4>
                <button class="btn-rm">READ MORE</button>
            </div>

        </div>

        <div class="contact-from">
            <h2 class="title">Contact us<span>.</span></h2>
            <p class="subtitle">Lorem ipsum dolor sit amet consectetur, adipisicing elit.</p>
            <hr>
            <div class="data">
                <input class="input-style" type="text" id="name" placeholder="Your Name">
                <input class="input-style" type="email" id="email" placeholder="Your Email">
            </div>

            <textarea class="input-style" name="" id="" cols="47" rows="5" placeholder="Write a Message..."></textarea>
            
            <button class="btn-orange">SEND <span>| &RightArrow;</span></button>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;
.container {
    width: 70%;
    margin: 0 auto;
    display: flex;
    padding: 5rem 0;
    gap: 2rem;
    .events {
        width: 50%;
        position: relative;
        .world{
            width: 100%;
        }
        
        .event{
            width: 15px;
            position: absolute;
            cursor: pointer;

            &.newyork{
                left: 110px;
                top: 90px;
            }

            &.london{
                left: 50%;
                top: 60px;
            }

            &.melbourne{
                bottom: 90px;
                right: 60px;
            }
        
        }

        .info-ny{
            box-shadow: 0 0 20px $border_gray;
            width: 40%;
            padding: .8rem;
            position: absolute;
            left: 110px;
            top: 110px;
            background-color: white;
        }

        .info-mb{
            box-shadow: 0 0 20px $border_gray;
            width: 40%;
            padding: .8rem;
            position: absolute;
            bottom: 10px;
            right: 80px;
            background-color: white;
        }

        .info-ln{
            box-shadow: 0 0 20px $border_gray;
            width: 40%;
            padding: .8rem;
            position: absolute;
            left: 55%;
            top: 60px;
            background-color: white;
        }

    }
    
    .contact-from{
        width: 50%;
        h2{
            font-size: 2rem;
        }

        p{
            margin: .5rem 0;
        }

        hr{
            width: 10%;
            margin-bottom: 2rem;
        }
        .input-style{
            border-top: 0;
            border-left: 0;
            border-right: 0;
            border-bottom: 1px solid $border_gray;
            font-size: .6rem;
            padding-left: 10px;
        }

        input{
            width: 48%;
            padding-bottom: 5px;
            
            &#name{
                margin-right: 2%;
            }
        }

        textarea{
            margin-top: 1rem;
            width: 100%;
        }

        button{
            display: block;
            border: 0;
            padding: .7rem 1rem;
            margin-top: 1rem;
            font-size: .6rem;

            span{
                font-size: 1rem;
                margin-left: 1rem;
            }
        }
    }

}
</style>