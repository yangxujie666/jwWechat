<template>
  <div class="user-wrapper">
    <div class="img-wrapper">
      <img :src="imgTitle" alt="" mode="widthFix">
    </div>
    <div class="userinfo-wrapper">
      <div class="user-info user-info-items">
        <div class="userinfo" @click="bindViewTap">
          <img class="userinfo-avatar" v-if="userInfo.avatarUrl" :src="userInfo.avatarUrl" background-size="cover" />
          <img class="userinfo-avatar" v-if="!userInfo.avatarUrl" src="/static/tabs/user/tx@3x.png" background-size="cover" />
          <div class="userinfo-nickname">
            <card :text="userInfo.nickName"></card>
          </div>
        </div>
      </div>
      <div class="user-handle user-info-items">
        <div class="user-admin user-control">
          <img class="icon" src="/static/tabs/user/sz@3x.png" background-size="cover" />
          <div class="contro-text">账户管理</div>
        </div>
        <div class="user-adress user-control">
          <img class="icon" src="/static/tabs/user/map@3x.png" background-size="cover" />
          <div class="contro-text">地址管理</div>
        </div>
      </div>
      <div class="user-telephone user-info-items">
        <img class="telephone-img" src="/static/tabs/user/tel@3x.png" background-size="cover" />
        <i class="telephone-text">010-82868686</i>
      </div>
    </div>
  </div>
</template>

<script>
import imgTitle from 'static/tabs/user/ttbg@3x.png'
import card from '@/components/card'
export default {
  data () {
    return {
      imgTitle:imgTitle,
      userInfo: {
        nickName: '昵称',
        avatarUrl: ''
      }
    }
  },
  onLoad() {
    console.log("onlo")
    wx.setNavigationBarTitle({
      title: '个人中心'
    })
  },
  methods: {
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    }
  },

  created () {
    // let app = getApp()
  },
  components: {
    card
  }
}
</script>

<style scoped>
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 78px;
  height:78px;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}
.user-wrapper{
  width: 100vw;
  height:100vh;
  position: relative;
}
.img-wrapper img{
  width: 100%;
}
.userinfo-wrapper{
  position: absolute;
  width: 347px;
  height: 66%;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  margin: auto;
  display: flex;
  flex-direction: column;
  box-shadow:  0 6px 4px 1px rgba(231,236,250,1);
  background: #fff;
  padding:0 14px;
  box-sizing: border-box;
}
.user-info-items{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  border-bottom: 1px solid #eaeaea;
}
.user-info-items:last-child{
  border-bottom: none;
}
.user-info{
  height:140px;
}
.user-handle{
  height:98px;
  flex-direction: row;
}
.contro-text{
  font-size: 14px;
  color: #333333;
}
.icon{
  width: 26px;
  height: 28px;
  margin-bottom: 10px;
}
.user-control{
  flex:1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.telephone-img{
  width: 23px;
  height: 28px;
}
.telephone-text{
  font-size: 16px;
  font-style:italic;
  color: #333333;
  margin-left: 8px;
}
.user-telephone{
  flex:1;
  flex-direction: row;
}

</style>
