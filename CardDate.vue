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
        name: "CardDate",
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
                return `${this.dateObj.getFullYear()}-${prefixNumber(this.dateObj.getMonth() + 1)}`.slice(2);
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
            left: -6.8vw;
            top: 3.6/3.75+vw;
            width: 100%;
            height: 10vw;
            background: #ffd705;
            transform: skewX(-20deg);
        }
        .wk-card-date_day {
            font-size: 36/3.75+vw;
            line-height: 1.2;
            color: #333;
            font-style: italic;
            font-weight: bold;
        }
        .wk-card-date_month {
            font-size: 14/3.75+vw;
            color: #dedede;
        }
    }
</style>
