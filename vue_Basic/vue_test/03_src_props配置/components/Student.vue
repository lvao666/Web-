<template>
    <div>
        <h1>{{msg}}</h1>
        <h2>姓名：{{name}}</h2>
        <h2>性别：{{sex}}</h2>
        <h2>年龄：{{myAge}}</h2>
        <button @click="updateAge">点我增加年龄</button>
    </div>
</template>

<script>
export default {
    name:'Student',
    data() {
        return {
            msg:'我是一个尚硅谷的学生',
            myAge:this.age
        }
    },
    methods: {
        updateAge(){
            this.myAge++
        }
    },
    props:['name','age','sex']  //简单接收

    // 接收的同时对数据进行类型限制
    /* props:{
        name:String,
        age:Number,
        sex:String
    } */

    // 接收数据的同时对数据：进行类型限制 + 默认值的指定 + 必要性的限制
    /* props:{
        name:{
            type:String,  //name的类型是字符串
            required:true, //name是必要的
            default:99
        },
        age:{
            type:Number,
            default:99
        },
        sex:{
            type:String,
            required:true
        }
    } */
}
</script>
