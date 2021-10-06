<template>
  <div>
    <div class="hero">
      <div class="container">
        <h1>Welcome to Ny Blog</h1>
        <p class="subtitle">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Assumenda at debitis, est hic
          magni vel?</p>
        <NuxtLink to="/contact" class="hire">Hire me</NuxtLink>
      </div>
    </div>
    <div class="container">
      <main>
        <h2>Latest thoughts</h2>
        <ul>
          <li v-for="(post, index) in posts" :key="index">
            <img src="image.png" alt="">
            <div class="content">
              <!--              <NuxtLink :to="{path:post.id}">{{post.title}}</NuxtLink>-->
              <p>{{post.body}}</p>

            </div>
          </li>
        </ul>
      </main>
    </div>
  </div>
</template>

<script>


    export default {
        name: 'index',
        data() {
            return {
                posts: []
            }
        },
        methods: {
            async getPosts() {
                const posts = await this.$axios.get('https://jsonplaceholder.typicode.com/posts');
                this.posts = posts.data;
                console.log(this.posts)
            },
        },
        mounted() {
            this.getPosts();
        }
    }
</script>
<style lang="scss">
  .hero {
    background-color: $primary-color;
    color: white;
    text-align: center;
    padding-top: 2em;

    h1 {
      margin-bottom: 1em;
    }

    .hire {
      background: darken($primary-color, 20%);
      padding: 0.5em 3em;
      margin: 2em 0 3em;
      display: inline-block;
      border-radius: 10px;
      color: $accent-color;
      text-decoration: none;
    }
  }

  .container ul {
    list-style-type: none;
    padding: 0;
  }

  main {

    li {
      background: white;
      border-radius: 1em;
      padding: 0.8em;
      margin: 1em 0;
      box-shadow: 15px 21px 40px 0px rgba(0, 0, 0, 0.04);
    }

    img {
      width: 100%;
      border-radius: 0.5em;
    }

    .content{
      padding: 0.5em;
    }
  }
</style>
