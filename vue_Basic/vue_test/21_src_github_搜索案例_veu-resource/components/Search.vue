<template>
  <section class="jumbotron">
    <h3 class="jumbotron-heading">Search Github Users</h3>
    <div>
      <input
        type="text"
        placeholder="enter the name you search"
        v-model="keyWord"
      />&nbsp;<button @click="searchUsers">Search</button>
    </div>
  </section>
</template>

<script>

export default {
  name: "Search",
  data() {
    return {
      keyWord:''
    }
  },
  methods: {
    searchUsers(){
      // 请求前更新List的数据
      this.$bus.$emit('updataListData',{isFirst:false,isLoading:true,errMsg:'',users:[]})
      this.$http.get(`https://api.github.com/search/users?q=${this.keyWord}`).then(
        response => {
          console.log('请求成功')
          // this.$bus.$emit('getUsers',response.data.items)
          this.$bus.$emit('updataListData',{isLoading:false,errMsg:'',users:response.data.items})
        },
        error => {
          console.log('请求失败',error.message)
          this.$bus.$emit('updataListData',{isLoading:false,errMsg:error.message,users:[]})
        }
      )
    }
  },
  mounted() {
    
  },
};
</script>

<style>
</style>