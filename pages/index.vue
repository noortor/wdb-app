<template>
  <section class="container">
    <div>
      <img src="../assets/berkeley-skyline.png" />
      <img class="ucb-logo" src="../assets/berkeley-logo (1).png" />
      <div v-for="post in posts.posts" :key="post">
        <NuxtLink :to="{ name: 'post.id', params: { stuff: post} }">
          <div class="post-box">
            <p>Posted by {{post.author}}</p>
            <h1 class="post-title">{{post.title}}</h1>
            <p class="post-content">{{post.content}}</p>
          </div>
        </NuxtLink>
      </div>
      <h1 class="title">wdb-nuxt</h1>
      <h2 class="subtitle">Nuxt.js project</h2>
      <div class="links">
        <a href="https://nuxtjs.org/" target="_blank" class="button--green">Documentation</a>
        <a href="https://github.com/nuxt/nuxt.js" target="_blank" class="button--grey">GitHub</a>
      </div>
    </div>
  </section>
</template>

<script>
import AppLogo from "~/components/AppLogo.vue";
import data from "../data.json";
export default {
  components: {
    AppLogo
  },
  data() {
    return {
      posts: data
    };
  }
};
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

.ucb-logo {
  padding-left: 50px;
}

.post-title {
}

.post-content {
  margin: auto;
  width: 30%;
}

.post-box {
  border: 4px solid blue;
  margin-bottom: 40px;
}
</style>

