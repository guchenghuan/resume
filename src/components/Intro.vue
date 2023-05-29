<template>
  <div>
    <div class="intro-me">
      <div class="cover-main">
        <div class="cover-main-left">
          <p>
            非科班出身，大学期间学过C++，后来18年大学毕业，开始接触编程，颇感兴趣。于是独立自学
            Web
            开发技术。入坑后，成为疯狂的技术追求者，占据了18-19一年所有周末学习代码。业务测试出身，一步步做到业务线的前端开发。
          </p>
          <p style="margin-top: 10px">
            拥有丰富的测试工具开发经验，前端开发经验。担任测试工具组的Owner，QA前端组的Owner
          </p>
          <p style="margin-top: 10px">我可以使用它们来创造工作中需要的一切：</p>
          <ul>
            <li>JavaScript</li>
            <li>TypeScript</li>
          </ul>
          <p style="margin-top: 10px">我可以使用它们来十分出色的完成工作：</p>
          <p><strong>技术：</strong></p>
          {{ skills.techs.join(", ") }}
          <p style="margin-top: 10px"><strong>测试 & 部署：</strong></p>
          {{ skills.tests.join(", ") }}
          <p style="margin-top: 10px">
            <strong>业务倾向：</strong>
          </p>
          测试业务方向的应用设计开发、复杂的应用开发，落地到实际工作使用中
          对业务有实际的正向反馈，同时它也能被赋予 <strong>'意义'</strong>
        </div>
        <div class="cover-img" id="main"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Intro",
  props: {
    skills: {
      type: Object,
      required: true,
    },
  },
  mounted() {
    this.initLine();
  },
  methods: {
    initLine() {
      var chartDom = document.getElementById("main");
      var myChart = this.$echarts.init(chartDom);
      var option;

      option = {
        radar: {
          indicator: [
            { name: "JavaScript", max: 100 },
            { name: "TypeScript", max: 100 },
            { name: "css", max: 100 },
            { name: "Vue", max: 100 },
            { name: "React", max: 100 },
            { name: "Node.js", max: 100 },
            { name: "ES6", max: 80 },
            { name: "Golang", max: 100 },
          ],
          axisName: {
            formatter: "{value}",
            color: "#1d2129",
          },
        },
        series: [
          {
            name: "Score",
            type: "radar",
            data: [
              {
                value: [95, 90, 80, 95, 90, 70, 50, 70],
                name: "Score",
                areaStyle: {
                  color: new this.$echarts.graphic.RadialGradient(0.1, 0.6, 1, [
                    {
                      color: "#b8d1e1",
                      offset: 0,
                    },
                    {
                      color: "#b8d1e1",
                      offset: 1,
                    },
                  ]),
                },
              },
            ],
            label: {
              show: true,
              formatter: function (params) {
                return params.value;
              },
            },
          },
        ],
      };
      option && myChart.setOption(option);
    },
  },
};
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
