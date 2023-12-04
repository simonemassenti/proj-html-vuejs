<script>
export default {
    data() {
        return {
            menu: [
                {
                    name: "Home",
                    activated: true
                },
                {
                    name: "Pages",
                    activated: false
                },
                {
                    name: "Blog",
                    activated: false
                },
                {
                    name: "Shop",
                    activated: false
                },
                {
                    name: "Events",
                    activated: false
                },
                {
                    name: "Elements",
                    activated: false
                }
            ]
        }
    }
}
</script>

<template>
    <header>
        <img src="../assets/img/img/logo-img-01.png" alt="Logo Everlead">
        <ul>
            <li v-for="item in menu" :class="item.activated ? 'active' : ''">
                <a href="">
                    <span v-if="item.activated">&RightArrow;</span>
                    {{ item.name }}
                </a>
            </li>
            <li><i class="fa-solid fa-magnifying-glass"></i></li>
            <li class="m-0"><i class="fa-solid fa-list"></i></li>
        </ul>
    </header>
</template>

<style scoped lang="scss">
header {
    height: 100px;
    display: flex;
    justify-content: space-between;
    width: 90%;
    align-items: center;
    position: fixed;
    left: 50%;
    transform: translate(-50%);

    img {
        width: 8.5rem;
        align-self: center;
    }

    ul {
        display: flex;
        list-style-type: none;


        li {
            margin-right: 1.5rem;
            text-transform: uppercase;
            font-size: .7rem;
            font-weight: 600;
            text-align: center;

            a {
                color: inherit;
                text-decoration: none;
            }
        }

    }


}

.m-0 {
    margin: 0;
}

.fa-magnifying-glass {
    transform: scaleX(-1);
}

.active {
    color: #FF4612;
}
</style>