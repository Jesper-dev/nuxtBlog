<template>
  <div class="single-post">
    <section class="post">
      <h1 class="post-title">{{ loadedPost.title }}</h1>
      <div class="post-details">
        <div class="post-detail">
          Last Updated On {{ loadedPost.updatedDate }}
        </div>
        <div class="post-detail">Written By {{ loadedPost.author }}</div>
      </div>
      <p class="post-content">{{ loadedPost.content }}</p>
    </section>
    <section class="post-feedback">
      <p>Let me know what you think about the post!</p>
      <a href="feedback@my-awesome-domain.com"
        >feedback@my-awesome-domain.com</a
      >
    </section>
  </div>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          loadedPost: {
            id: '1 ',
            title: 'My Awesome Post (ID: ' + context.route.params.id + ')',
            previewText: 'Hey look at my awesome new post!',
            author: 'Jesper',
            updatedDate: new Date(),
            content: 'Dummy text',
            thumbnail:
              'https://hub.packtpub.com/wp-content/uploads/2018/05/programming.jpg',
          },
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
.single-post {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>
