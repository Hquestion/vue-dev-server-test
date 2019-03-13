<template>
    <div class="time-line-panel">
        <div class="left">

        </div>
        <TimeNewsCard></TimeNewsCard>
    </div>
</template>

<script>
    import TimeNewsCard from "./TimeNewsCard.vue";
    export default {
        name: "TimelinePanel",
        components: {TimeNewsCard}
    }
</script>

<style lang="scss" scoped>
    .time-line-panel {
        padding-left: 40/3.75+vw;
        min-height: 80/3.75+vw;
        position: relative;
        .left {
            height: 100%;
            width: 2/3.75+vw;
            background: #dedede;
            position: absolute;
            left: 15/2/3.75+vw;
            top: 0;
        }
    }
</style>
