<template>
  <section class="post-list">
    <PostPreview
      id="1"
      :is-admin="isAdmin"
      thumbnail="https://hub.packtpub.com/wp-content/uploads/2018/05/programming.jpg"
      title="Hello There!"
      previewText="My First Post"
    />

    <PostPreview
      id="2"
      :is-admin="isAdmin"
      thumbnail="https://hub.packtpub.com/wp-content/uploads/2018/05/programming.jpg"
      title="Hello again!"
      previewText="My Second Post"
    />
  </section>
</template>

<script>
import PostPreview from '@/components/Posts/PostPreview'
export default {
  components: {
    PostPreview,
  },
  props: {
    isAdmin: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style scoped>
.post-list {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
</style>
