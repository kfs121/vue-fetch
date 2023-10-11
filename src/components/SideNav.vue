<template>
  <nav>
    <a :href="upTo">Up</a>
    <a :href="downTo">Down</a>
  </nav>
</template>

<script>
export default {
  props: {
    upTo: String,
    downTo: String
  },
}

</script>

<style lang="scss" scoped>
  nav{
    position: fixed;
    right: 32px;
    top: 70%;
    display: flex;
    flex-direction: column;
    justify-content: center;

    a{
      line-height: 60px;
      text-align: center;
      display: block;
      width: 60px;
      height: 60px;
      border-radius: 30px;
      margin: 2rem;
      box-shadow: 2px 2px 5px 1px;
      background-image: linear-gradient(to bottom right, white 70%, rgb(168, 168, 168));
      color: black;
      
      &:hover{
        background-image: linear-gradient(to bottom right, rgb(238, 238, 238) 70%, rgb(117, 117, 117));
      }
    }
  }
</style>