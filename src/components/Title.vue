<template>
    <div class="title">
        <div class="title-item">
            <div>{{title.sn}}</div>
            <div>{{title.ganzhi}}</div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Title",
        props: {
            title: {
                type: Object,
                default: () => {
                    return {
                        "sn": "一",
                        "ganzhi": "甲子",
                        "hexagrams1": "乾下乾上",
                        "hexagrams2": "乾"
                    }
                }
            }
        }
    }
</script>

<style lang="scss" scoped>
    .title {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        position: relative;
        width: 64px;
        height: 520px;
        background: $color-red;
        color: #fff;
        font-size: 24px;
        margin: 0 40px;
        box-sizing: border-box;
        text-align: center;

        &::before {
            display: block;
            content: '';
            width: 64px;
            height: 16px;
            border-bottom: 4px solid #fff;
            background: $color-red;
            box-sizing: border-box;

        }

        &::after {
            content: '';
            width: 64px;
            height: 32px;
            background: $color-red;
            border-top: 4px solid #fff;
            box-sizing: border-box;
        }

        .title-item {
            width: 20px;

            div:nth-child(1) {
                margin-bottom: 16px;
            }
        }
    }
</style>
