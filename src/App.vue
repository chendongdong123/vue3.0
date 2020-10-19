<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <h2>红色浪漫点餐系统</h2>
    <div>请选择第一位美女为你服务</div>
    <p>
      <button
        v-for="(item, index) in girls"
        :key="{ index }"
        @click="selectGirlFun(index)"
      >
        {{ index }}:-{{ item }}
      </button>
    </p>
    <div>你选择了【123123{{ selectGirl }}】姑娘为你服务</div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
// reactive
export default defineComponent({
  name: 'App',
  setup() {
    const girls = ref(['大脚', '刘颖', '小红'])
    const selectGirl = ref('')
    const selectGirlFun = (index: number) => {
      selectGirl.value = girls.value[index]
    }
    return {
      girls,
      selectGirl,
      selectGirlFun,
    }
  },
})
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
