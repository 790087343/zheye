<template>
  <!-- <navbar>
    <div
      class="container fluid bg-light border radius p-2 mb-2 d-flex justify-content-between"
    >
      <a href="#" class="navbar-brand d-block p-2">
        <span class="ms-2">者也专栏</span>
      </a>
      <div v-if="!user.isLogin">
        <button class="btn btn-outline-primary me-2">登录</button>
        <button class="btn btn-outline-primary">注册</button>
      </div>
      <div v-else>
        <button class="btn btn-outline-primary">欢迎您, {{ user.name }}</button>
      </div>
    </div>
  </navbar> -->

  <nav class="navbar navbar-dark bg-primary justify-content-between mb-4 px-4">
    <a class="navbar-brand" href="#">者也专栏</a>
    <ul v-if="!user.isLogin" class="list-inline mb-0">
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light">登录</a>
      </li>
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light">注册</a>
      </li>
    </ul>
    <ul v-else class="list-inline mb-0">
      <li class="list-inline-item">
        <Dropdown :title="`你好 ${user.name}`">
          <!-- <a href="#" class="btn btn-outline-light dropdown-toggle text-light">
            你好 {{ user.name }}
          </a> -->
        </Dropdown>
      </li>
    </ul>
  </nav>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import Dropdown from "./DropdownList.vue";
export interface UserProps {
  isLogin: boolean;
  name?: string;
  id?: number;
}

export default defineComponent({
  name: "GlobalHeader",
  props: {
    user: {
      type: Object as PropType<UserProps>,
      required: true,
    },
  },
  components: {
    Dropdown,
  },
});
</script>
