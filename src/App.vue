<template>
  <div id="app">
    <!-- 头部-->
    <!-- <Myheader :poiInfo="poiInfo"></Myheader> -->
    <Myheader :poiInfo="poiInfo"></Myheader>
    <!-- 导航-->
    <Mynav></Mynav>
    <!-- <Mynav :commentNum="commentNum"></Mynav> -->
    <!-- <div class="nav"></div> -->
    <!-- 主体内容-->
    <div class="content"></div>
    <!--<div class="content">
    		   content
    </div>-->
    <!-- 路由出口 -->
    <!-- 路由匹配到的组件将渲染在这里 -->
    <!-- <keep-alive>
      <router-view></router-view>
    </keep-alive>-->
    <router-view></router-view>
  </div>
</template>

<script>
// 1、导入
// import Myheader from 'components/Header/Header';
import Mynav from "components/Nav/Nav";
import Myheader from "components/Header/Header";

export default {
  name: "app",
  components: {
    // 2、注册
    Myheader,
    Mynav,
  },
  data() {
    return {
      poiInfo: {},
    };
  },
  created() {
    // Make a request for a user with a given ID
    var that = this;
    this.$axios
      .get("/api/goods")
      .then(function (response) {
        // handle success
        var dataSource = response.data;
        if (dataSource.code == 0) {
          that.poiInfo = dataSource.data.poi_info;
          console.log(that);
        }
        // console.log(response);
      })
      .catch(function (error) {
        // handle error
        console.log(error);
      })
      .then(function () {
        // always executed
      });
  },
  //   data() {
  //     return {
  //       // header组件需要的信息(商家信息)
  //       poiInfo: {},
  //       commentNum: 0,
  //     };
  //   },
  //   created() {
  //     // 发起异步请求，获取数据

  //     var that = this;

  //     // 通过axios发起get请求
  //     this.$axios
  //       .get("/api/goods")
  //       .then(function (response) {
  //         // 获取到数据
  //         var dataSource = response.data;
  //         if (dataSource.code == 0) {
  //           that.poiInfo = dataSource.data.poi_info;
  //         }
  //       })
  //       .catch(function (error) {
  //         // 出错处理
  //         console.log(error);
  //       });

  //     // 通过axios发起get请求
  //     this.$axios
  //       .get("/api/ratings")
  //       .then(function (response) {
  //         // 获取到数据
  //         var dataSource = response.data;
  //         if (dataSource.code == 0) {
  //           that.commentNum = dataSource.data.comment_num;
  //         }
  //       })
  //       .catch(function (error) {
  //         // 出错处理
  //         console.log(error);
  //       });
  //   },
};
</script>

<style>
</style>