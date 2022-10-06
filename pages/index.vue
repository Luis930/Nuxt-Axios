<template>
  <div>
    <h1 class='m3'>Posts</h1>
    <Post
    v-for="post of posts"
    :key="post.id"
    :name='post.title'
    :id='post.id' />
  </div>
</template>

<script>
import axios from 'axios'
import Post from '../components/Post.vue'

export default {
  components:{
    Post
  },
  name: 'IndexPage',
  head(){
    return{
    title:'App Nuxt',
    meta:[{
      hid:'Description',
      name:'Description',
      content:'Website'
    }],
    htmlAttrs:{
      lang:'en'
    }
    }
  },
  data(){
    return{
      posts:[]
    }
  },
  async created(){
      try {
        const res = await axios.get('https://jsonplaceholder.typicode.com/posts')
        this.posts = res.data
        console.log(res)
      } catch (error) {
        console.log(error)
      }
  }
}
</script>
