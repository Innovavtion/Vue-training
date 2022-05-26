<template>
  <div id="app">
    <input type="text" v-model="search" />
    <div v-for="post in filtredPost" :key="post.id">
      <post :post="post"></post>
    </div>
  </div>
</template>

<script>
//Добавление компонентов или по другому инициализация
import Post from "./components/Post";

export default {
  name: "App",

  components: {
    Post,
  },

  data() {
    return {
      posts: [
        {
          id: 1,
          title: "Post 1",
          body: "Vue.js is cool",
        },
        {
          id: 2,
          title: "Post 2",
          body: "JavaScript is cool",
        },
      ],
      search: "",
    };
  },

  //Computed свойство срабатывает сразу при открытии страницы
  computed: {
    //Метод который фильтрует массив posts и возвращает его
    filtredPost() {
      return this.posts.filter((post) => post.title.includes(this.search));
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
