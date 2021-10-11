<template>
  <div id="myChart" :style="{ width: width, height: height }"></div>
</template>

<script>
export default {
  name: "hello",
  props: {
    width: {
      type: String,
      default: "300px",
    },
    height: {
      type: String,
      default: "300px",
    },
    title: {
      type: String,
      default: "echarts",
    },
    echartsData: {
      type: Object,
      default: null
    }
  },
  data () {
    return {
      myChart: ''
    }
  },
  mounted() {
    this.drawLine();
  },
  methods: {
    // 基于准备好的dom，初始化echarts实例
    drawLine() {
      let data = this.echartsData
      this.myChart = this.$echarts.init(document.getElementById("myChart"));
      // 绘制图表
      this.myChart.setOption({
        // 修改title字体
        title: { 
          text: this.title,
          x: 'center',
          y: 'top',
          textStyle: {
            color: 'blue',
            fontSize: 18
          }
        },
        // 鼠标移上去显示的数据
        tooltip: {
          trigger: 'axis'
        },
        // x轴数据
        xAxis: {
          type: "category",
          data: data.x,
        },
        // y轴数据
        yAxis: {
          type: "value",
        },
        series: [
          {
            data: data.y,
            color: '#6eaaee', // 线条颜色
            type: "line",
            smooth: true,
          },
        ],
      });
    },
  },
};
</script>

<style>
</style>