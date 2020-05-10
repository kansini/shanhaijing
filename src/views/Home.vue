<template>
    <div class="home">
        <div class="logo"></div>
        <div class="nav">
            <router-link :to="item.path" tag="div" class="nav-item" v-for="item in navs" :key="item.img">
                <div class="nav-item-img" :style="{background:item.bg}">
                    <img :src="`../assets/img/nav-${item.img}.svg`">
                </div>
                <div class="nav-item-title">
                    <img :src="`../assets/img/title-${item.img}.svg`">
                </div>
            </router-link>
        </div>
    </div>
</template>

<script>


    export default {
        name: 'Home',
        components: {},
        data() {
            return {
                navs: [
                    {
                        "img": "shen",
                        "path": "detail",
                        "bg": "#F7D6A2"
                    },
                    {
                        "img": "fish",
                        "path": "detail",
                        "bg": "#259A6C"
                    },
                    {
                        "img": "bird",
                        "path": "detail",
                        "bg": "#5B7CC3"
                    },
                    {
                        "img": "beast",
                        "path": "detail",
                        "bg": "#845F4A"
                    },
                    //{"img": "country"}
                ]
            }
        }
    }
</script>
<style lang="scss" scoped>
    .home {
        position: relative;
        width: 100vw;
        height: 100vh;
        background: $base-bg;
        padding: 64px 40px;
        box-sizing: border-box;

        .logo {
            width: 100%;
            height: 240px;
            background: url("../assets/img/logo.svg") no-repeat center;
            background-size: auto 100%;
            animation: logo 1s linear forwards;
        }

        .nav {
            width: 100%;
            height: calc(100vh - 320px);
            display: flex;
            justify-content: space-between;
            align-items: center;


            .nav-item {
                display: flex;
                flex-direction: column;
                justify-content: space-between;
                align-items: center;
                cursor: pointer;
                animation: scaleIn linear .6s forwards;
                transform: scale(0);

                .nav-item-img {
                    width: 240px;
                    height: 240px;
                    border-radius: 240px;
                    overflow: hidden;
                    transition: all ease .4s;
                    margin-bottom: 16px;

                    img {
                        width: 100%;
                    }

                    &:hover {
                        transform: scale(1.1);
                    }
                }


            }

            @for $n from 1 through 6 {
                .nav-item:nth-child(#{$n}) {
                    animation-delay: $n * .5s
                }
            }

        }

        @keyframes scaleIn {
            0% {
                transform: scale(0);
            }
            100% {

                transform: scale(.85);
            }
        }

    }

    @keyframes logo {
        0% {
            opacity: 0;
            transform: scale(0);
        }
        80% {
            opacity: 1;
            transform: scale(.5);
        }
        100% {
            transform: scale(1);
        }
    }
</style>
