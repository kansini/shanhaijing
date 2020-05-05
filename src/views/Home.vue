<template>
    <div class="home">
        <div class="logo"></div>
        <div class="nav">
            <div class="nav-item" v-for="item in navs">
                <img :src="`../assets/img/nav-${item.img}.svg`" alt="">
            </div>
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
                    {"img": "god"},
                    {"img": "fish"},
                    {"img": "bird"},
                    {"img": "beast"}
                ]
            }
        },
    }
</script>
<style lang="scss" scoped>
    .home {
        position: relative;
        width: 100vw;
        height: 100vh;
        background: $base-bg;
        padding: 80px 96px;
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
                cursor: pointer;
                transition: all ease .4s;
                animation: scaleIn linear .6s forwards;
                transform: scale(0);


                &:hover {
                  filter: contrast(200%);
                }
            }

            @for $n from 1 through 5 {
                .nav-item:nth-child(#{$n}) {
                    animation-delay: $n * 0.2s
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
