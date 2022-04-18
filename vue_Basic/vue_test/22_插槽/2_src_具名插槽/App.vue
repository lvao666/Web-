<template>
    <div class="container">
      <Category title="美食">
        <img slot="center" src="https://s3.ax1x.com/2021/01/16/srJlq0.jpg" alt="">
        <a slot="footer" href="javascript:;">更多美食</a>
      </Category>

      <Category title="游戏">
        <ul slot="center">
          <li v-for="(g,index) in games" :key="index">{{g}}</li>
        </ul>
        <div class="foot" slot="footer">
          <a href="javascript:;">单机游戏</a>
          <a href="javascript:;">网络游戏</a>
        </div>
      </Category>

      <Category title="电影">
        <video slot="center" controls src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4"></video>
        <!-- <template slot="footer"> -->
          <template v-slot:footer> <!-- 这种写法，只能在使用template时可以使用 -->
          <div class="foot">
            <a href="javascript:;">经典</a>
            <a href="javascript:;">热门</a>
            <a href="javascript:;">推荐</a>
          </div>
          <h4>欢迎前来观影</h4>
        </template>
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
  .container,
  .foot{
    display: flex;
    justify-content: space-around;
  }
  video{
    width: 100%;
  }
  h4{
    text-align: center;
  }
</style>
