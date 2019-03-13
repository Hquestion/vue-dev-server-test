<template>
    <div class="wk-news-card">
        <div class="news-card_header"></div>
        <div class="news-card_main">
            <CardDate class="date_left" :date="news.date"></CardDate>
            <div class="news-detail">
                <div class="news-detail_header">{{news.title}}</div>
                <div class="news-detail_mark">
                    <div class="news-from">{{news.from}}</div>
                    <div class="news-read">阅读{{news.readCount}}</div>
                </div>
            </div>
        </div>
        <div class="news-card-footer"></div>
    </div>
</template>

<script>
    import CardDate from "./CardDate.vue";
    export default {
        name: "NewsCard",
        components: {CardDate},
        props: {
            news: {
                type: Object,
                default: () => ({
                    date: '2019-3-14',
                    title: '关于对南京市文化消费政府补贴项目的审计通知',
                    from: '南京市文化广电新闻出版局',
                    readCount: '2222'
                })
            }
        }
    }
</script>

<style lang="scss" scoped>
    .wk-news-card {
        position: relative;
        width: 100%;
        height: 100/3.75+vw;
        padding-top: 10/3.75+vw;
        .news-card_header {
            position: absolute;
            left: 0;
            top: 0;
            width: 100%;
            height: 10/3.5+vw;
            border-top-left-radius: 10/3.5+vw;
            border-top-right-radius: 10/3.5+vw;
            background: #dedede;
        }
        .news-card_main {
            display: flex;
            justify-content: flex-start;
            align-items: center;
            background: #fff;
            padding: 20/3.75+vw 10/3.75+vw 10/3.75+vw 0;
            .date_left {
                width: 60/3.75+vw;
                height: 70/3.75+vw;
            }
            .news-detail {
                flex: 1;
                height: 70/3.75+vw;
                margin-left: 10/3.75+vw;
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
                    color: #dedede;
                    font-size: 12/3.75+vw;
                    display: flex;
                    justify-content: space-between;
                    align-items: center;
                    margin-top: 16/3.75+vw;
                }
            }
        }
        .news-card-footer {
            height: 10/3.75+vw;
            width: 100%;
            background: linear-gradient(top, #e5e5e5, #f2f2f2);
            background: -webkit-linear-gradient(top, #e5e5e5, #f2f2f2);
        }
    }
</style>
