<template>
  <article>
    <h3>{{ post.title }}</h3>
    <p>{{ post.body }}</p>
  </article>
</template>

<script>
export default {
  //Props используется для получения данных из родительского помпонента
  //В нашем случае из цикла родительского компонента
  props: ["post"],
};
</script>