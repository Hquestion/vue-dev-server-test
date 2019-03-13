<template>
    <div class="wk-time-news-card">
        <div class="news-card_main">
            <TimeNewsDate class="date_left" :date="news.date"></TimeNewsDate>
            <div class="news-detail">
                <div class="news-detail_header">{{news.title}}</div>
                <div class="news-detail_mark">
                    <div class="news-from">{{news.from}}</div>
                    <span>&nbsp;&nbsp;/&nbsp;&nbsp;</span>
                    <div class="news-read">阅读{{news.readCount}}</div>
                </div>
            </div>
            <div class="news-poster" v-if="news.poster">
                <img :src="news.poster">
            </div>
        </div>
        <div class="arrow"></div>
        <div class="dot"></div>
    </div>
</template>

<script>
    import TimeNewsDate from "./TimeNewsDate.vue";
    export default {
        name: "TimeNewsCard",
        components: {TimeNewsDate},
        props: {
            news: {
                type: Object,
                default: () => ({
                    date: '2019-3-14',
                    title: '关于对南京市文化消费政府补贴项目的审计通知',
                    from: '文化',
                    readCount: '2222',
                    poster: 'http://www.runoob.com/wp-content/uploads/2014/07/gradient_radial.jpg'
                })
            }
        }
    }
</script>

<style lang="scss" scoped>
    .wk-time-news-card {
        padding: 10/3.75+vw;
        position: relative;
        border-radius: 10/3.75+vw;
        background: #fff;
        box-shadow: 0 0 30/3.75+vw 5/3.75+vw #e2e2e2;
        & + .wk-time-news-card {
            margin-top: 10/3.75+vw;
        }
        .news-card_main {
            display: flex;
            align-items: flex-start;
            justify-content: flex-start;
            .date_left {
                width: 50/3.75+vw;
            }
            .news-detail {
                margin-left: 10/3.75+vw;
                flex:1;
                display: flex;
                flex-wrap: wrap;
                flex-direction: column;
                align-items: flex-start;
                justify-content: space-between;
                .news-detail_header {
                    overflow: hidden;
                    text-overflow:ellipsis;
                    display: -webkit-box;
                    -webkit-line-clamp: 2;
                    -webkit-box-orient: vertical;
                    color: #464646;
                    font-size: 16/3.75+vw;
                    line-height: 1.2;
                    min-height: 40/ 3.75+vw;
                }
                .news-detail_mark {
                    display: flex;
                    font-size: 12/3.75+vw;
                    color: #dedede;
                    margin-top: 16/3.75+vw;
                }
            }
            .news-poster {
                margin-left: 10/3.75+vw;
                width: 90/3.75+vw;
                height: 80/3.75+vw;
                img {
                    width: 100%;
                    height: 100%;
                }
            }
        }
        .dot{
             position: absolute;
             content: '\20';
             display: block;
             width: 25/3.75+vw;
             height: 25/3.75+vw;
             background: #f2f2f2;
             left: -38/3.75+vw;
             top: 50%;
             transform: translateY(-50%);
            &:after {
                position: absolute;
                content: '\20';
                left: 7.5/3.75+vw;
                top: 7.5/3.75+vw;
                width: 10/3.75+vw;
                height: 10/3.75+vw;
                background: #999;
                border-radius: 5/3.75+vw;
            }
         }
        .arrow {
            position: absolute;
            left: -23/3.75+vw;
            top: 50%;
            transform: translateY(-50%);
            border-left: 8/3.75+vw solid transparent;
            border-top: 12/3.75+vw solid transparent;
            border-right: 16/3.75+vw solid #fff;
            border-bottom: 12/3.75+vw solid transparent;
            z-index: 2;
        }
    }
</style>
