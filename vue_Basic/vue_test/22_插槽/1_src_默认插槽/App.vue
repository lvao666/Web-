<template>
    <div class="container">
      <Category title="美食">
        <img src="https://s3.ax1x.com/2021/01/16/srJlq0.jpg" alt="">
      </Category>

      <Category title="游戏">
        <ul>
          <li v-for="(g,index) in games" :key="index">{{g}}</li>
        </ul>
      </Category>

      <Category title="电影">
        <video controls src="http://clips.votwaerts-gmbh.de/big_buck_bunny.mp4"></video>
      </Category>
    </div>
</template>

<script>
  import Category from './components/Category.vue'

  export default {
    name: "App",
    components:{Category},
    data(){
      return{
        foods:['火锅','烧烤','麻辣小龙虾','牛排'],
        games:['CF','LOL','超级玛丽','红色警戒'],
        films:['《教父》','《复联》','《蜘蛛侠》','《碟中谍》']
      }
    }
  };
</script>

<style>
  .container{
    display: flex;
    justify-content: space-around;
  }
  video{
    width: 100%;
  }
</style>
