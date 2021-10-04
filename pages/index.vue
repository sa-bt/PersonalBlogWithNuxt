<template>
  <h2>salam</h2>
  <h2>ss</h2>
</template>

<script>
  import {posts} from '~/api/posts'
export default {
    name:'index',
async asyncData(){
        const posts=await  this.$axios.get(`'https://jsonplaceholder.typicode.com/posts`);
    console.log(posts)
        return{posts:posts}
}
}
</script>
