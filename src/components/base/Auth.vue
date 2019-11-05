<template>
    <div class="auth-wrapper">
      <div class="auth">
        <div class="auth-info">
          <div class="auth-img">
            <ImageView
              src="https://www.youbaobao.xyz/mpvue-res/logo.jpg"
              round
              height="100%"
              mode="scaleToFill"
            ></ImageView>
          </div>
          <div class="sub-title">登陆民宿短租</div>
          <div class="title">全球民宿任你选</div>
        </div>
        <button
          class="auth-btn"
          open-type="getUserInfo"
          @getuserinfo="getUserInfo"
        >
          授权登陆
        </button>
      </div>
    </div>
</template>

<script>
  import ImageView from './ImageView'
  export default {
    components: {ImageView},
    methods: {
      getUserInfo () {
        this.$emit('getUserInfo')
      }
    }
  }
</script>

<style lang="scss" scoped>
  .auth-wrapper {
    position: fixed;
    left: 0;
    top: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    background: #999;
    z-index: 1000;
    .auth {
      position: relative;
      width: 270px;
      height: 248px;
      background: #f5f5f5;
      border-radius: 18px;
      .auth-info {
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-top: 22.5px;
        .auth-img {
          width: 74px;
          height: 74px;
        }
        .sub-title {
          font-size: 13px;
          color: #999;
          line-height: 18.5px;
          margin-top: 18px;
        }
        .title {
          font-size: 16px;
          font-weight: 600;
          color: #333;
          line-height: 22.5px;
          margin-top: 3.5px;
        }
      }
      .auth-btn {
        position: absolute;
        bottom: 0;
        width: 100%;
        height: 49px;
        line-height: 49px;
        font-size: 15px;
        color: #fff;
        background-image: linear-gradient(90deg, #1EA3F5 0%, #0F87FC 100%);
        border-radius: 0 0 18px 18px;
      }
    }
  }
</style>
