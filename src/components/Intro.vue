<template>
  <div>
    <div class="intro-me">
      <div class="cover-main">
        <div class="cover-main-left">
          <p style="margin-top: 10px">
            拥有丰富的测试工具开发经验，前端开发经验。
          </p>
          <!-- <p style="margin-top: 10px">我可以使用它们来创造工作中需要的一切：</p>
          <ul>
            <li>JavaScript</li>
            <li>TypeScript</li>
            <li>Node.js</li>
            <li>JAVA</li>
          </ul> -->
          <p style="margin-top: 10px">我可以使用它们来十分出色的完成工作：</p>
          <p><strong>技术：</strong></p>
          {{ skills.techs.join(', ') }}
          <p style="margin-top: 10px"><strong>测试 & 部署：</strong></p>
          {{ skills.tests.join(', ') }}
          <p style="margin-top: 10px">
            <strong
              >座右铭：生活的海洋并不像碧波涟漪的西子湖，随着时间的流动，它时而平静如镜，时而浪花飞溅，时而巨浪冲天……人们在经受大风大浪的考验之后，往往会变得更加坚强。</strong
            >
          </p>
        </div>
        <div class="cover-img" id="main"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Intro',
  props: {
    skills: {
      type: Object,
      required: true,
    },
  },
  mounted() {
    this.initLine()
  },
  methods: {
    initLine() {
      var chartDom = document.getElementById('main')
      var myChart = this.$echarts.init(chartDom)
      var option

      option = {
        radar: {
          indicator: [
            { name: 'JavaScript', max: 100 },
            { name: 'TypeScript', max: 100 },
            { name: 'css', max: 100 },
            { name: 'Vue', max: 100 },
            { name: 'React', max: 100 },
            { name: 'Node.js', max: 100 },
            { name: 'ES6', max: 100 },
            { name: 'JAVA', max: 100 },
          ],
          axisName: {
            formatter: '{value}',
            color: '#1d2129',
          },
        },
        series: [
          {
            name: 'Score',
            type: 'radar',
            data: [
              {
                value: [95, 90, 80, 95, 90, 90, 80, 75],
                name: 'Score',
                areaStyle: {
                  color: new this.$echarts.graphic.RadialGradient(0.1, 0.6, 1, [
                    {
                      color: '#b8d1e1',
                      offset: 0,
                    },
                    {
                      color: '#b8d1e1',
                      offset: 1,
                    },
                  ]),
                },
              },
            ],
            label: {
              show: true,
              formatter: function (params) {
                return params.value
              },
            },
          },
        ],
      }
      option && myChart.setOption(option)
    },
  },
}
</script>

<style scoped lang="scss">
.intro-me {
  font-size: 0.9em;
  padding-left: 10px;
}
.cover-main {
  margin-top: 5px;
  display: flex;
  justify-content: space-between;
  .cover-main-left {
    width: 60%;
  }
}
.cover-img {
  position: relative;
  overflow: hidden;
  width: 320px;
  height: 318px;
  padding: 0px;
  margin: 0px;
  border-width: 0px;
  cursor: default;
}
</style>
