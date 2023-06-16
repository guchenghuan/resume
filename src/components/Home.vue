<template>
  <div>
    <div class="info">
      <h1 class="name">{{ name }}</h1>
      <p>
        电话: <strong class="tel">{{ tel }}</strong> 邮件:
        <strong class="email">{{ email }}</strong>
        工作经验:
        <strong class="email">{{ ages }}</strong
        >年
      </p>
    </div>

    <div class="contact">
      <h4>个人链接</h4>
      <hr />
      <div class="blogs">
        个人主页:
        <strong
          ><a :href="website" target="_blank">{{ website }}</a
          >（个人网站）</strong
        >
      </div>
      <div class="links">
        Github:
        <strong
          ><a :href="github" target="_blank">{{ github }}</a
          >(筹备开源中...)</strong
        >
      </div>
      <div class="links">
        掘金:
        <strong
          ><a :href="juejin" target="_blank">{{ juejin }}</a
          >(3.3W+ 阅读量)</strong
        >
      </div>
    </div>
    <div class="skills">
      <h4>个人优势</h4>
      <hr />
      <Advance :advance="advance"></Advance>
    </div>
    <div v-if="works" class="interns">
      <h4>工作经历</h4>
      <hr />
      <List :source="works"></List>
    </div>
    <div class="skills">
      <h4>技术剖面</h4>
      <hr />
      <Intro :skills="skills" />
    </div>
    <div class="edu">
      <h4>教育背景</h4>
      <hr />
      <List :source="edus"></List>
    </div>
  </div>
</template>

<script>
import List from "./List";
import Advance from "./Advance";
import Intro from "./Intro";
import info from "../assets/info";

export default {
  name: "Home",
  data() {
    return info;
  },
  components: {
    List,
    Advance,
    Intro,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.info {
  .name {
    text-align: center;
  }

  p {
    text-align: center;
  }

  .links,
  .blogs {
    //text-align: center;
  }
}

a {
  color: #42b983;
  text-decoration: none;
}
</style>
