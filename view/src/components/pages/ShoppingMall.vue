<template>
  <!--search bar layout-->
  <div class="search-bar">
    <van-row>
      <van-col span="3"><img :src="locationIcon" width="100%" /></van-col>
      <van-col span="16">serach input</van-col>
      <van-col span="5">button</van-col>
    </van-row>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      message: 'Message',
      locationIcon: require('../../assets/images/location.png')
    }
  }
}
</script>

<style>
.search-bar{
  height: 2.2rem;
  background-color: #d8b338;
  line-height:2.2rem;
}
</style>
