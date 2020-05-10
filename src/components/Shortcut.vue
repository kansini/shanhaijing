<template>
    <div class="shortcut">
        <div class="btn-cover" @click="$router.push('/')" v-if="$route.path != '/'"></div>
        <div class="btn-fullscreen" :class="{isFullscreen:isFullscreen}" @click="toggleFullscreen"></div>
        <a href="https://github.com/kansini/shanhaijing" target="_blank" class="btn-github"></a>
        <div class="btn-nav" v-if="$route.path != '/'" @click="handleToNav"></div>
    </div>

</template>

<script>
    import screenfull from 'screenfull'

    export default {
        name: "Shortcut",
        data() {
            return {
                isFullscreen: false
            }
        },
        methods: {
            toggleFullscreen() {
                screenfull.toggle()
                this.isFullscreen = !this.isFullscreen
            },
            handleToNav() {
                this.$emit('openNav')
            }
        }
    }
</script>

<style lang="scss" scoped>
    .shortcut {
        position: fixed;
        left: 0;
        top: 0;
        width: 100%;
        height: 64px;
        padding: 16px 24px;
        box-sizing: border-box;
        display: flex;
        justify-content: flex-end;
        z-index: 1;

        [class^='btn-'] {
            width: 24px;
            height: 24px;
            cursor: pointer;
            opacity: .8;
            transition: all ease .4s;

            &:hover {
                opacity: 1;
                transform: scale(1.05);
            }

            &:not(:first-child) {
                margin-left: 16px;
            }
        }

        .btn-github {
            background: url("../assets/img/logo-gihub.svg") no-repeat center;
            background-size: 100%;
        }

        .btn-fullscreen {
            background: url("../assets/img/ico-fullscreen.svg") no-repeat center;
            background-size: 100%;
        }

        .isFullscreen {
            background: url("../assets/img/ico-exitFullscreen.svg") no-repeat center;
            background-size: auto 100%;
        }

        .btn-cover {
            background: url("../assets/img/ico-context.svg") no-repeat center;
            background-size: auto 100%;
        }

        .btn-nav {
            background: url("../assets/img/ico-nav.svg") no-repeat center;
            background-size: auto 100%;
        }


    }

</style>
