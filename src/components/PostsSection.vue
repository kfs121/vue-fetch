<template>
  <SideNav :downTo="lastElementId" :upTo="'#'"></SideNav>
  <section>
    <h2>방명록</h2>
    <ul>
      <li v-for="post in posts" :key="post.id">
        <span class="id">{{ post.id }}</span>
        <p>{{ post.title }}</p>
      </li>
    </ul>
  </section>
</template>

<script>
import SideNav from './SideNav.vue';
export default {
  data() {
    return {
      posts: [],
    }
  },
  methods: {
    getPost() {
      fetch("https://jsonplaceholder.typicode.com/todos")
        .then(res => {
          return res.json();
        })
        .then((data) => {
          this.posts = data;
        })
        .catch(e => {
          console.error(e);
        });
    }
  },
  props:{
    lastElementId:String
  },
  components:{
    SideNav
  },
  created() {
    this.getPost();
  },
  mounted(){
    console.log(this.posts.length);
  }
}
</script>
  
<style lang="scss" scope>
// body {
//   * {
//     outline: 1px dotted red;
//   }
// }

section {
  width: 1200px;
  margin: 40px auto;
  padding: 40px;

  h2{
    text-align: center;
    padding: 1rem 0;
    font-size: 2.5rem;
  }

  ul {
    

    li {
      margin: .5rem 0;
      display: flex;
      border: 1px solid #ccc;

      .id {
        flex: 1;
        display: flex;
        justify-content: center;
        align-items: center;
        color: #888;
      }

      p {
        border-left: 1px solid #ccc;
        padding: .4rem 0;
        padding-left: 2rem;
        flex: 8;
        color: white;
      }
    }
  }
}
</style>