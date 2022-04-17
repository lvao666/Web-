<template>
    <div class="demo">
        <h2 class="qwe">姓名：{{name}}</h2>
        <h2>性别：{{sex}}</h2>
    </div>
</template>

<script>
export default {
    name:'Student',
    data() {
        return {
            name:'Tom',
            sex:'男'
        }
    },
}
</script>
<style lang="less" scoped>
    .demo{
        background-color: #bfa;
        .qwe{
            font-size: 40px;
        }
    }
</style>
