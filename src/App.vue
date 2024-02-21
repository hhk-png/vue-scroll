<script setup lang="ts">
import { onMounted, ref } from 'vue';

const scrollContainerDOM = ref<HTMLElement>();
/**
 * 滑动：
 *  1. scrollIntoView() 方法可以自动回到上次浏览的位置。
 *  2. 使用window.scrollTo()，但是该方法需要使用定时器多次调用才能实现滑动效果。
 *  3. 使用vuerouter的scrollBehavior 方法，该方法需要在路由切换时才会触发。
 *    https://router.vuejs.org/zh/guide/advanced/scroll-behavior
 * 
*/
onMounted(() => {
  scrollContainerDOM.value?.scrollIntoView()
});

const scroll = () => {
  window.scrollTo(0, 100);
};

</script>

<template>
  <button @click="scroll">scroll</button>
  <div ref="scrollContainerDOM">
    <div v-for="(item, index) in 50" :key="item" class="scroll-div">{{ index }}</div>
  </div>
</template>

<style scoped>
.scroll-div {
  height: 15em;
  width: 100px;
  background-color: aqua;
  border: 1px solid black;
}
</style>
