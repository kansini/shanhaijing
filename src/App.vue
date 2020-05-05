<template>
    <div id="app">
        <shortcut />
        <transition :name="transitionName">
            <router-view class="child-view"/>
        </transition>
    </div>
</template>
<script>
    import shortcut from '@/components/Shortcut'

    export default {
        name: 'App',
        components: {
            shortcut
        },
        data() {
            return {
                transitionName: 'slide-left'
            }
        },
        watch: {
            '$route'(to, from) {
                if (to.path == '/') {
                    this.transitionName = 'slide-left';
                } else {
                    this.transitionName = 'slide-right';
                }
            }
        }
    }
</script>

<style lang="scss">
    body {
        font-family: "xiaokai";
        //font-family: kangxizidianti;
    }
</style>
