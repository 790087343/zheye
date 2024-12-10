<template>
  <div class="container">
    <global-header :user="currentUser"></global-header>
    <column-list :list="list"></column-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import "bootstrap/dist/css/bootstrap.min.css";
import ColumnList, { ColumnProps } from "./components/ColumnList.vue";
import GlobalHeader, { UserProps } from "./components/GlobalHeader.vue";

const testData: ColumnProps[] = [
  {
    id: 1,
    title: "test1 的专栏",
    description:
      "这是的 test1 的专栏，专门讨论关于测试的话题。在这里，你将发现很多关于测试的好文章！",
    avatar:
      "https://storage.googleapis.com/vue-mastery.appspot.com/flamelink/media/vue-mastery-logo.png",
  },
  {
    id: 2,
    title: "test2 的专栏",
    description:
      "这是的 test2 的专栏，专门讨论关于测试的话题。在这里，你将发现很多关于测试的好文章！",
    avatar:
      "https://storage.googleapis.com/vue-mastery.appspot.com/flamelink/media/vue-mastery-logo.png",
  },
  {
    id: 3,
    title: "test3 的专栏",
    description:
      "这是的 test3 的专栏，专门讨论关于测试的话题。在这里，你将发现很多关于测试的好文章！",
  },
  {
    id: 4,
    title: "test4 的专栏",
    description:
      "这是的 test4 的专栏，专门讨论关于测试的话题。在这里，你将发现很多关于测试的好文章！",
    avatar:
      "https://storage.googleapis.com/vue-mastery.appspot.com/flamelink/media/vue-mastery-logo.png",
  },
];

const currentUser: UserProps = {
  isLogin: true,
  name: "zhangsan",
};

export default defineComponent({
  name: "App",
  components: {
    ColumnList,
    GlobalHeader,
  },
  setup() {
    return {
      list: testData,
      currentUser,
    };
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
