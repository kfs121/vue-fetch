<template>
  <div id="wrap">
    <h1 :style="titleStlye" id="main-title">{{ welcomeMsg }}</h1>
    <PostsSection :lastElementId="'#last'"></PostsSection>
    <div id="last"></div>
  </div>
</template>


<script>
import PostsSection from './components/PostsSection.vue';
export default {
  data() {
    return {
      welcomeMsg: '어서오세요!!!',
      titleStlye: {
        textAlign: 'center',
        fontSize: '56px',
        marginTop: '3rem'
      }
    }
  },
  components: {
    PostsSection
  }
}
</script>


<style lang="scss">
@font-face {
  font-family: 'Pretendard-Regular';
  src: url('https://cdn.jsdelivr.net/gh/Project-Noonnu/noonfonts_2107@1.1/Pretendard-Regular.woff') format('woff');
  font-weight: 400;
  font-style: normal;
}

// body * {outline: 1px dotted red;}

html {
  scroll-behavior: smooth;
}

* {
  margin: 0;
  padding: 0;
}

a {
  color: inherit;
  text-decoration: none;
}

li {
  list-style-type: none;
}

img {
  display: block;
}

button {
  outline: none;
  background-color: inherit;
  border: none;
}

body {
  font-family: 'Pretendard-Regular', sans-serif;
}


#wrap{
  background: url("https://images.wallpaperscraft.com/image/single/planet_galaxy_universe_121293_1920x1080.jpg") no-repeat center / cover;
  background-attachment: fixed;
  widows: 100%;
  color: white;
}

</style>