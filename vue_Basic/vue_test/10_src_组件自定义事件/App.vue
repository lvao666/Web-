<template>
    <div class="app">
        <h1>{{msg}}{{studentName}}</h1>
        <!-- 通过父组件给子组件传递函数类型的props实现：子给父传递数据 -->
        <School :getSchoolName="getSchoolName"/>

        <!-- 通过父组件给子组件绑定一个自定义事件实现：子给父传递数据（第一种写法，使用@或v-on） -->
        <!-- <Student v-on:atguigu="getStudentName" @demo="m1"/> -->

        <!-- 通过父组件给子组件绑定一个自定义事件实现：子给父传递数据（第二种写法，使用ref） -->
        <Student ref="student" @click.native="show"/>  
    </div>
</template>

<script>
    import Student from './components/Student.vue'
    import School from './components/School.vue'
    
    export default {
        name:'App',
        components:{Student,School},
        data() {
            return {
                msg:'你好啊！！',
                studentName:''
            }
        },
        methods: {
            getSchoolName(name){
                console.log('App收到了学校名：',name)
            },
            getStudentName(name,...params){
                console.log('App收到了学生名：',name,params)
                this.studentName = name
            },
            m1(){
                console.log('demo触发了！')
            },
            show(){
                alert('hello')
            }
        },
        mounted(){
            this.$refs.student.$on('atguigu',this.getStudentName)  //当定自定义事件
            // 这里箭头函数没有自己的this，会向外层找
            /* this.$refs.student.$on('atguigu',(name,params)=>{
                console.log('App收到了学生名：',name,params)
                console.log(this)
                this.studentName = name
            })   */


            // this.$refs.student.$once('atguigu',this.getStudentName)   //当定自定义事件（一次性）
        },
    }
</script>
<style>
    .app{
        background-color: gray;
        padding: 10px;
    }
</style>