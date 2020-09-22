<template>
  <div class="home">
    <img
      alt="Vue logo"
      src="../assets/logo.png"
    >
    <hello-world msg="Welcome to Your Vue.js App" />
    <shopping-cart
      :list="list"
      @add-course="addCourse"
    />
    <div v-if="list.length==0">
      没有任何课程信息
    </div>
    <ul v-else style="list-style:none">
      <li
        v-for="item in list"
        :key="item"
        @click="selectedItem=item"
        :class="{highlight:selectedItem==item}"
      >
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import ShoppingCart from '@/components/shopping-cart.vue';

export default {
  name: 'Home',
  //局部注册组件
  components: {
    HelloWorld,
    ShoppingCart
  },
  data() {
    return {
      list: [],
      selectedItem:''
    }
  },
  methods: {
    addCourse(val) {
      this.list.push(val);
    }
  },
}
</script>
<style scoped>
  .highlight {
    background: pink;
  }
</style>
