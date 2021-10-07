<template>

  <div class="container">
    <main>
      <h1>{{post.title}}</h1>
      <div class="content">
        <div>{{post.body}}</div>
      </div>
    </main>
  </div>
</template>

<script>


    export default {
        name: 'index',
        data() {
            return {
                post: []
            }
        },
        methods: {
            async getPost() {
                console.log(this.$route.params.id)
                const post = await this.$axios.get('https://jsonplaceholder.typicode.com/posts/' + this.$route.params.id);
                this.post = post.data;
                console.log(this.post)
            },
        },
        mounted() {
            this.getPost();
        }
    }
</script>
<style lang="scss">
  header {
    height: 15em;
  }

  h1 {
    color: white;
    margin-bottom: 1em;
  }

  .content {
    background: white;
    border-radius: 1em;
    padding: 1em;
  }

  .container ul {
    list-style-type: none;
    padding: 0;
  }

  main {
    margin-top: -9em;
  }

  .content img {
    width: 100%;
  }

  @media only screen and(min-width: 768px) {
    .content {
      padding: 2em;
    }
  }

</style>
