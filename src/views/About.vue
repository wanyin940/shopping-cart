<template>
  <div class="about">
    <h1 @click="test">This is an about page</h1>
  </div>
</template>
<script>
  export default{
    methods: {
      test() {
        // eslint-disable-next-line no-debugger
        debugger;
        console.log('test')
      }
    },
  }
</script>
