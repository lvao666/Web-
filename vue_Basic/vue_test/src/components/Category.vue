<template>
    <div class="category">
        <h3>{{title}}分类</h3>
        <slot :games="games">我是默认插槽</slot>
    </div>
</template>

<script>
    export default {
        name:'Category',
        props:['title'],
         data(){
            return{
                games:['CF','LOL','超级玛丽','红色警戒'],
            }
        }
    }
</script>

<style>
    .category{
        background-color: skyblue;
        width: 200px;
        height: 300px;
    }
    h3{
        text-align: center;
        background-color: #bfa;
    }
    img{
        width: 100%;
    }
</style>