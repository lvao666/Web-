<template>
    <div>
        <Student name="Jerry" sex="女" :age="15"/>
    </div>
</template>

<script>
    import Student from './components/Student.vue'
    
    export default {
        name:'App',
        components:{Student},
    }
</script>
