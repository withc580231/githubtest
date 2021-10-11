<template>
  <div>
    <Lines width="100%" height="400px" title="过去24小时空气质量指数" :echartsData="echartsData"></Lines>
  </div>
</template>

<script>
import Lines from '@/components/line.vue'
export default {
  components: {
    Lines
  },
  data () {
    return {
      echartsData: {
        x: ['09:00', '10:00', '11:00', '12:00', '13:00', '14:00', '15:00', '16:00', '17:00', '18:00', '19:00', '20:00'],
        y: [0, 5, 10, 15, 20, 25, 15, 0, 30, 10, 15, 20 ]
      }
    }
  }
}
</script>

<style scoped>

</style>
