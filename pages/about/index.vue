<template>
  <section id="about-page" v-editable="blok">
    <h1>{{ title }}</h1>
    <div class="post-thumbnail" :style="{backgroundImage: 'url(' + image + ')'}"></div>
    <p>{{ content }}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return context.app.$storyapi
      .get('cdn/stories/about', {
        version: context.isDev ? 'draft' : 'published'
      })
      .then(res => {
        console.log(res.data)
        return {
          blok: res.data.story.content,
          image: res.data.story.content.Image,
          title: res.data.story.content.Title,
          content: res.data.story.content.Content
        }
      })
  }
}
</script>

<style>
#about-page {
  width: 80%;
  max-width: 500px;
  margin: auto;
}

#about-page p {
  white-space: pre-line;
}

.post-thumbnail {
  width: 100%;
  height: 300px;
  background-size: cover;
  background-position: center;
}
</style>


 
