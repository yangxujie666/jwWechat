
<template>
  <div>
      <swiper v-if="imgUrls.length > 0" indidator-dots="imgUrls.length > 1" >
        <block v-for="(item, index) in imgUrls" :key="index" >
          <swiper-item>
            <image :src="item" mode="scaleToFill" class="banner-img"></image>
          </swiper-item>
        </block>
      </swiper>

    <ul class="container log-list">
      <li v-for="(items, index) in titles" :class="{ red: aa }" :key="index" class="log-item" @click="switchPage(index)">
        <div class="title-img">
          <img :src="items.urls" alt="">
        </div>
        <div class="title-text">
          {{items.name}}
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  import { formatTime } from '@/utils/index'
  import card from '@/components/card'

  import banner1 from '../../../static/tabs/home/banner1.png'
  import banner2 from '../../../static/tabs/home/banner02.png'
  import banner3 from '../../../static/tabs/home/banner03.png'
  import banner4 from '../../../static/tabs/home/banner04.png'

  import img1 from '../../../static/tabs/home/home-icon1.png'
  import img2 from '../../../static/tabs/home/home-icon2.png'
  import img3 from '../../../static/tabs/home/home-icon3.png'
  import img4 from '../../../static/tabs/home/home-icon4.png'
  import img5 from '../../../static/tabs/home/home-icon5.png'
  import img6 from '../../../static/tabs/home/home-icon6.png'

  export default {
    components: {
      card
    },

    data () {
      return {
        logs: [

        ],
        imgUrls: [banner1,banner2,banner3,banner4],
        titles:[
          {
            name:'小时工',
            urls:img1
          },
          {
            name:'育儿嫂',
            urls:img2
          },
          {
            name:'月嫂服务',
            urls:img3
          },
          {
            name:'产妇服务',
            urls:img4
          },
          {
            name:'保姆',
            urls:img5
          },
          {
            name:'开荒',
            urls:img6
          }
        ]
      }
    },

    created () {
      let logs
      if (mpvuePlatform === 'my') {
        logs = mpvue.getStorageSync({key: 'logs'}).data || []
      } else {
        logs = mpvue.getStorageSync('logs') || []
      }
      this.logs = logs.map(log => formatTime(new Date(log)))
    },
    methods:{
      switchPage(index){
        var url ="";
        // if (mpvuePlatform === 'wx') {
        //   mpvue.switchTab({ url })
        // } else {
        //   mpvue.navigateTo({ url })
        // }
        if(index == 0){
          url = '../detiles/hour/main'
        }else if(index == 1){
          url = '../detiles/yuerSao/main'
        }else if(index == 2){
          url = '../detiles/yuesao/main'
        }else if(index == 3){
          url = '../detiles/chanfu/main'
        }else if(index == 4){
          url = '../detiles/baomu/main'
        }else if(index == 5){
          url = '../detiles/kaihuang/main'
        }
        mpvue.navigateTo({ url })
      }
    }
  }
</script>

<style scoped>
.log-list {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  height: 370rpx;
}

.log-item {
  width: 33.3%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 185rpx;
  background: #fafaff;
  cursor: pointer;
}
.log-item:nth-of-type(even){
    background: #f3f3f8;
}
.log-item .title-text{
 /* font-size: 24px;*/
}
.log-item img{
  width: 23px;
  height: 29px;
}
swiper{
  height:435px;
}
.banner-img{
  width: 100%;
  height: 100%;
}
</style>
