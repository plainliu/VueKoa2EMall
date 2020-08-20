<template>
  <div>
    <!--search bar layout-->
    <div class="search-bar">
      <van-row>
        <van-col span="3"><img :src="locationIcon" width="100%" /></van-col>
        <van-col span="16">
          <input type="text" class="search-input"/>
        </van-col>
        <van-col span="5">
          <van-button size="mini">查找</van-button>
        </van-col>
      </van-row>
    </div>

    <!--swipwer area-->
    <div class="swiper-area">
      <van-swipe :autoplay="1000">
          <van-swipe-item v-for="(banner,index) in bannerPicArray" :key="index">
              <img v-lazy="banner.imageUrl" width="100%"/>
          </van-swipe-item>
      </van-swipe>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data: function () {
    return {
      locationIcon: require('../../assets/images/location.png'),
      bannerPicArray: [
        {imageUrl: 'https://cube.elemecdn.com/6/94/4d3ea53c084bad6931a56d5158a48jpeg.jpeg'},
        {imageUrl: 'https://cube.elemecdn.com/6/94/4d3ea53c084bad6931a56d5158a48jpeg.jpeg'},
        {imageUrl: 'https://cube.elemecdn.com/6/94/4d3ea53c084bad6931a56d5158a48jpeg.jpeg'}
      ]
    }
  },
  created () {
    axios({
      url: 'http',
      method: 'get'
    })
    .then(response => {
      console.log(response)
    })
    .catch(error => {
      console.log(error)
    })
  }
}
</script>

<style>
.search-bar{
  height: 2.2rem;
  background-color: #d8b338;
  line-height:2.2rem;
}
.search-input{
    width:100%;
    height: 1.3rem;
    border-top:0px;
    border-left:0px;
    border-right:0px;
    border-bottom: 1px solid 1px !important ;
    background-color: #d8b338;
    color:#fff;
}
.location-icon{
    padding-top: .2rem;
    padding-left: .3rem;
}

.swiper-area{
      width:20rem;
      clear:both;
  }
</style>
