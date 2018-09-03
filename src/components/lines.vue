<template>
    <div id="main1" style="width: 7rem;height: 6.5rem;">

    </div>
</template>

<script>
    import echarts from 'echarts'
    export default {
        name: "lines",
        data () {
            return {
                charts: '',

                opinionData:[
                    {value:335, name:'直接访问'},
                    {value:310, name:'邮件营销'},
                    {value:234, name:'联盟广告'},
                    {value:135, name:'视频广告'},
                    {value:1548, name:'搜索引擎'}
                ]
            }
        },
        methods:{
            drawPie(id){
                this.charts = echarts.init(document.getElementById(id))
                this.charts.setOption({
                    grid: {
                        left: '3%',
                        right: '4%',
                        bottom: '3%',
                        containLabel: true
                    },
                    tooltip: {
                        trigger: 'axis',

                    },

                    xAxis:  {
                        type: 'category',
                        boundaryGap: false,
                        data: ['00:00', '01:15', '02:30', '03:45', '05:00', '06:15', '07:30', '08:45', '10:00', '11:15', '12:30', '13:45', '15:00', '16:15', '17:30', '18:45', '20:00', '21:15', '22:30', '23:45']
                    },
                    yAxis: {
                        type: 'value',
                        axisLabel: {
                            formatter: '{value} W'
                        },
                        axisPointer: {
                            snap: true
                        }
                    },

                    series: [
                        {
                            name:'用电量',
                            type:'line',
                            symbol: "circle",
                            data: [300, 280, 250, 260, 270, 300, 550, 500, 400, 390, 380, 390, 400, 500, 600, 750, 800, 700, 600, 400],
                            itemStyle : {
                                normal : {
                                    color:'#f9444d',

                                }
                            },
                        }
                    ]
                })
            }
        },
        mounted(){
            this.$nextTick(function() {
                this.drawPie('main1')
            })
        }
    }
</script>

<style scoped>

</style>