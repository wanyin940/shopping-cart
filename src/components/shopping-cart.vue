<template>
    <div>
        <input type="text" @keydown.enter="addCourse" v-model="course">
        <button @click="addCourse"> + Add</button>
    </div>
</template>

<script>
    export default {
        name:'shopping-cart',
        props:{
            list:{
                type: Array,
                require:true,
                default: () => []
            }
        },
        data() {
            return {
                course: ''
            }
        },
        methods: {
            addCourse() {
                this.$emit('add-course', this.course)
                this.course = '';
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>