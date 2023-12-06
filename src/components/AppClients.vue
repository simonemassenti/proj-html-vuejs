<script>
export default{
    data() {
        return{
            clients: [
                {
                    image: "03",
                    hover: "04-1"
                },
                {
                    image: "05",
                    hover: "06-1"
                },
                {
                    image: "07",
                    hover: "08-1"
                },
                {
                    image: "09",
                    hover: "10-1"
                },
                {
                    image: "01",
                    hover: "02"
                }

            ]
        }
    },
    methods: {
        getImagePath(img) {
            return new URL(`../assets/img/img/h4-clients-img-${img}.png`, import.meta.url).href;
        },
    }
}

</script>

<template>
<div class="container">
    <div class="row">
        <div class="client" v-for="client in clients">
            <img class="client-img" :src="getImagePath(client.image)" alt="">
            <img class="client-h" :src="getImagePath(client.hover)" alt="">
        </div>
    </div>
</div>


</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;

.container{
    width: 70%;
    margin: 0 auto;
    padding-bottom: 5rem;

    .row{
        display: flex;
        justify-content: space-between;
        position: relative;
        
        .client-h{
            display:none;
        }
        .client:hover .client-h{
            display: block;
        }

        .client:hover .client-img{
            display: none;
        }

        

    }


}


</style>