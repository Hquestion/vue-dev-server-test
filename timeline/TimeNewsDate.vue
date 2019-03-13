<template>
    <div class="wk-card-date" :class="[size]">
        <div class="date-box">
            <div class="wk-card-date_day">{{day}}</div>
            <div class="wk-card-date_month">{{month}}</div>
        </div>
        <div class="wk-card-date_bg"></div>
    </div>
</template>

<script>
    function prefixNumber(number) {
        if (+number < 10) {
            return '0' + number;
        } else {
            return '' + number;
        }
    }
    export default {
        name: "TimeNewsDate",
        props: {
            date: {
                type: String,
                default: '2019-03-13'
            },
            size: {
                type: String,
                default: 'normal'
            }
        },
        computed: {
            dateObj() {
                return new Date(this.date.replace(/-/g, '/'));
            },
            day() {
                return prefixNumber(this.dateObj.getDate());
            },
            month() {
                return `${this.dateObj.getMonth() + 1}月`;
            }
        }
    }
</script>

<style lang="scss" scoped>
    .wk-card-date {
        width: 100%;
        height: 60/3.75+vw;
        position: relative;
        overflow: hidden;
        text-align: center;
        .date-box {
            position: absolute;
            width: 100%;
            height: 100%;
            left:0;
            top: 0;
            text-align: center;
            z-index: 2;
        }
        .wk-card-date_bg {
            position: absolute;
            left: -40%;
            top: 0;
            width: 100%;
            height: 16/3.75+vw;
            background: #ffd705;
            transform: skewX(-20deg);
        }
        .wk-card-date_day {
            font-size: 26/3.75+vw;
            line-height: 1.1;
            color: #333;
        }
        .wk-card-date_month {
            font-size: 14/3.75+vw;
            color: #dedede;
        }
    }
</style>
