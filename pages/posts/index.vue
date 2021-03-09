<template>
  <div class="post-page">
    <PostList :posts="loadedPosts" />
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'
export default {
  components: {
    PostList,
  },
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          loadedPosts: [
            {
              id: '1',
              title: 'My Awesome Post',
              previewText: 'Hey look at my awesome new post!',
              thumbnail:
                'https://hub.packtpub.com/wp-content/uploads/2018/05/programming.jpg',
            },
            {
              id: '2',
              title: 'Wow another awesome post',
              previewText: 'This is another awesome post made by me.',
              thumbnail:
                'https://hub.packtpub.com/wp-content/uploads/2018/05/programming.jpg',
            },
            {
              id: '3',
              title: 'Not as awesome post',
              previewText:
                'This is another post, but it is not as awesome, sorry',
              thumbnail:
                'https://hub.packtpub.com/wp-content/uploads/2018/05/programming.jpg',
            },
          ],
        })
      }, 1000)
    })
      .then((data) => {
        return data
      })
      .catch((e) => {
        context.error(new Error())
      })
  },
}
</script>

<style scoped>
.post-page {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
