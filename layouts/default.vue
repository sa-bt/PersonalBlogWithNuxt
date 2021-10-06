<template>
    <div>
      <header>
        <div class="container">
          <div class="navbar">
            <NuxtLink to="/" class="logo">SABT</NuxtLink>

            <nav>
              <ul>
                <li>
                  <NuxtLink to="/who">Who?</NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/posts">Posts</NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/contact">Contact</NuxtLink>
                </li>
              </ul>
            </nav>
          </div>
        </div>
      </header>
      <Nuxt/>
    </div>
</template>

<script>
    export default {
        name: "default"
    }
</script>

<style scoped lang="scss">
*,
*:before,
*:after{
  box-sizing: border-box;
  margin: 0;
}
body{
  background: #ECECEC;
}
.container{
  margin: 0 auto;
  width: 90%;
  }
  header{
    background: $primary-color;
    padding: 1em 0;
    text-align: center;

    .navbar{
      display: flex;
      justify-content: space-between;
      font-weight: bold;
    }

    a{
      color: white;
      text-decoration: none;
    }

    nav{
      display: flex;

      ul{
        list-style-type: none;
        padding: 0;
        display: flex;
      }

      li a{
        font-weight: normal;
        padding: 0.5em;
      }
    }
  }

  @media only screen and(min-width:768px) {
    body{
      font-size: 18px;
    }
  }
</style>
