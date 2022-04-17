<template>
    <div class="student">
        <h2>姓名：{{name}}</h2>
        <h2>性别：{{sex}}</h2>
        <button @click="sendStudentName">把学生名给School组件</button>
    </div>
</template>

<script>
export default {
    name:'Student',
    data() {
        return {
            name:'Tom',
            sex:'男',
        }
    },
    methods:{
        sendStudentName(){
            this.$bus.$emit('hello',this.name)
        }
    }
}
</script>
<style lang="less" scoped>
    .student{
        background-color: #bfa;
        padding: 5px;
        margin-top: 30px;
    }
</style>
