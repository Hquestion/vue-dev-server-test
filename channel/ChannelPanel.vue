<template>
    <div class="wk-channel-panel">
        <div class="channel-panel_header">{{title}}</div>
        <div class="channel-panel_body" :class="[layout]">
            <div class="grid-item">1</div>
            <div class="grid-item">2</div>
            <div class="grid-item">3</div>
            <div class="grid-item">4</div>
            <div class="grid-item">5</div>
            <div class="grid-item">6</div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ChannelPanel',
    data() {
        return {};
    },
    props: {
        title: {
            default: '线上通道',
            type: String
        },
        layout: {
            type: String,
            default: 'grid'
        }
    }
}
</script>

<style lang="scss" scoped>
    .wk-channel-panel {
        width: 100%;
        text-align: center;
        .channel-panel_header {
            display: inline-block;
            padding: 5/3.75+vw 10/3.75+vw;
            height: 20/3.75+vw;
            font-size: 16/3.75+vw;
            background: #c32;
            color: #333;
            position: relative;
            border-top-left-radius: 5/3.75+vw;
            border-top-right-radius: 5/3.75+vw;
            &:before {
                content: '\20';
                position: absolute;
                left: -13/3.75+vw;
                bottom: 0;
                border-bottom: 30/3.75+vw solid #c32;
                border-top: 15/3.75+vw solid transparent;
                border-left: 15/3.75+vw solid transparent;
                border-right: 0 solid transparent;
            }
            &:after {
                content: '\20';
                position: absolute;
                right: -13/3.75+vw;
                bottom: 0;
                border-bottom: 30/3.75+vw solid #c32;
                border-top: 15/3.75+vw solid transparent;
                border-right: 15/3.75+vw solid transparent;
                border-left: 0 solid transparent;
            }
        }
        .channel-panel_body {
            border: 1px solid #c32;
            min-height: 50/3.75+vw;
            border-radius: 5/3.75+vw;
            border-bottom: 5px solid #c32;
            &.grid {
                display: grid;
                grid-template-columns: 33.3% 33.3% 33.3%;
                grid-template-rows: 25vw 25vw;
                .grid-item {
                    width: 20vw;
                    height: 20vw;
                    position: relative;
                    left: 50%;
                    top: 2.5vw;
                    border-radius: 20vw;
                    border: 1px dashed #c32;
                    transform: translateX(-50%);
                }
            }
        }
    }
</style>
