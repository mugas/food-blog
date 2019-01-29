<template>
  <div id="post">
    <div class="post-thumbnail">
      <h1></h1>
      <p></p>
    </div>
  </div>
</template>


<script>
export default {
  asyncData(context) {
    return context.app.$storyapi
      .get('cdn/stories/' + context.params.postId, {
        version: 'draft'
      })
      .then(res => {
        console.log(res.data)
      })
  }
}
</script>

