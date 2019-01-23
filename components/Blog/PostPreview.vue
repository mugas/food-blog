<template>
  <nuxt-link :to="id">
    <article class="post-preview">
      <div :style="{backgroundImage: thumbnailImage}" class="post-preview-thumbnail"></div>
      <div class="post-preview-content">
        <h1>{{ title }}</h1>
        <p>{{ excerpt }}</p>
      </div>
    </article>
  </nuxt-link>
</template>


<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    excerpt: {
      tye: String,
      required: true
    },
    thumbnailImage: {
      type: String,
      required: true
    },
    id: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
a {
  text-decoration: none;
  color: black;
}
.post-preview {
  border-radius: 3px;
  box-shadow: 1px 1px 5px 1px rgba(0, 0, 0, 0.5);
  width: 90%;
  margin: auto;
  height: 20rem;
}
</style>

