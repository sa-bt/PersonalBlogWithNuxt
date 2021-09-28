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
.container{
  background: $primary-color;
  }
</style>
