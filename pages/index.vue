<template>
  <a @click="loginWithKakao">
    <img src="/kakaoImage.png"/>
  </a>
</template>

<script>
export default {
  name: 'IndexPage',
  methods: {
    kakaoInit () {
      Kakao.init('05eb616e46ebedf4abe9e83e9b19dec6')// KaKao client key
      Kakao.isInitialized()
    },
    async loginWithKakao () {
      await Kakao.Auth.authorize({
        redirectUri: `${window.location.origin}/kakao-callback`
      })
    }
  },
  mounted () {
    this.kakaoInit()
  }
}
</script>