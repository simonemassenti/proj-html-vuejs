<script>
export default {
    data() {
        return{
            links: [
                "About Me",
                "About Us",
                "Language Packs",
                "Became a coach",
                "Montly events"
            ]
        }
    }
}
</script>

<template>
    <div class="wrapper">
        <div class="container">

            <div class="col">
                <h3 class="title">About</h3>
                <hr>
                <p class="subtitle">We created Everlead to effectively become the stepping stone towards meeting all your
                    goals & achieving business success.</p>
                <div class="social">
                    <i class="fa-brands fa-linkedin-in brands"></i>
                    <i class="fa-brands fa-facebook-f brands"></i>
                    <i class="fa-brands fa-twitter brands"></i>
                </div>
            </div>

            <div class="col">
                <h3 class="title">Twitter</h3>
                <hr>
                <ul>
                    <li>
                        <div>
                            <i class="fa-brands fa-twitter twitter"></i>
                        </div>
                        <p class="subtitle">
                            <span class="underline">@aliasadadm</span> Hi <span class="underline">@aliasadadm</span>, can you please submit a ticket at <span class="underline">https://t.co/JLV61aXG7d</span> and one of our support agent... <span class="underline">https://t.co/yk57k1S9bS</span>
                        </p>
                    </li>

                    <li>
                        <div>
                            <i class="fa-brands fa-twitter twitter"></i>
                        </div>
                        <p class="subtitle">
                            <span class="underline">@HenrySefaBoaky1</span> Check out our theme Gioia which as all necessary elements to build a multi vendor marketplace. <span class="underline">https://t.co/c9BlYxZBlL</span>
                        </p>
                    </li>
                </ul>
                
                
            </div>

            <div class="col">
                <h3 class="title">Importaant Links</h3>
                <hr>
                <ul v-for="link in links">
                    <li>
                        <a href="">{{ link }}</a>
                    </li>
                </ul>
            </div>

            <div class="col contact-col">
                <h3 class="title">Contact Me</h3>
                <hr>
                <ul>
                    <li>
                        <i class="fa-solid fa-location-dot contact"></i>
                        457 BigBlue Street, NY 10013
                    </li>

                    <li>
                        <i class="fa-solid fa-phone contact"></i>
                        (351) 5512-2579
                    </li>

                    <li>
                        <i class="fa-regular fa-envelope contact"></i>
                        everlead@mikado.com
                    </li>
                </ul>
            </div>

        </div>
    </div>

    <div class="footer-bottom">
        Copyright Everlead&copy;MikadoThemes
    </div>
</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;

.wrapper {
    padding: 5rem 0;
    background-color: $bg_footer;

    .container {
        width: 70%;
        margin: 0 auto;
        display: flex;
        .col {
            width: calc(100% / 4 - 1.2rem);
            margin-right: 1.2rem;
            .title {
                color: white;
            }

            hr {
                width: 10%;
            }

            p{
                font-size: .6rem;
                margin-bottom: 1rem;
            }
            .brands {
                margin-right: .5rem;
                font-size: .6rem;
                width: 1.2rem;
                text-align: center;
                padding: .3rem;
                background-color: white;
                border-radius: 50%;
                color: $bg_footer;
            }

            ul{
                list-style-type: none;

                li{
                    display: flex;
                    margin-top: 1rem;
                    color: $gray_text;
                    font-size: .6rem;

                    .twitter{
                        font-size: .8rem;
                    }

                    .underline{
                        text-decoration: underline;
                    }

                    a{
                        color: $gray_text;
                        text-decoration: none;
                        font-size: .6rem;
                    }

                    .contact{
                        margin-right: .5rem;
                    }

                    .contact-col{
                        margin-right: 5rem;
                    }
                }
            }
        }

    }
}

.footer-bottom {
    background-color: $main-color;
    color: $gray_text;
    font-size: .6rem;
    padding: .4rem 0;
    text-align: center;
}
</style>