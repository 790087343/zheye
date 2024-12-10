<template>
  <div class="dropdown d-block">
    <a
      href="#"
      class="btn btn-outline-light dropdown-toggle my-2"
      @click.prevent="toggleOpen"
    >
      {{ title }}
    </a>
    <!-- <slot></slot> -->
    <ul class="dropdown-menu d-block" v-if="isOpen">
      <li><a href="#" class="dropdown-item">新建文章</a></li>
      <li><a href="#" class="dropdown-item">编辑文章</a></li>
    </ul>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "DropdownList",
  props: {
    title: {
      type: String,
      required: true,
    },
  },
  setup() {
    const isOpen = ref(false);

    const toggleOpen = () => {
      isOpen.value = !isOpen.value;
    };

    return {
      isOpen,
      toggleOpen,
    };
  },
});
</script>
