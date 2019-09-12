<template>
  <section class="hero is-medium is-primary is-bold">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            Welcome to the JavaScript SSR Blog.
          </h1>
          <h2 class="subtitle">
            Hope you find something you like.
          </h2>
        </div>
      </div>
      <posts></posts>
    </section>
</template>

<script>
import posts from '~/components/posts'
export default {
  head: {
    title: 'Home'
  },
  components: {
    posts
  }
}
</script>



