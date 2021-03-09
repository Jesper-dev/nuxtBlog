<template>
  <div class="homeWrapper">
    <section class="intro">
      <h1>Get latest tech news!</h1>
    </section>
    <PostList :posts="loadedPosts" />
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'
export default {
  components: {
    PostList,
  },
  //Denna kan bara bli kallad i pages
  //AsyncData gör så att sidan chillar tills datan blivit laddad och sen visar den sidan
  asyncData(context, callback) {
    console.log(context)
    setTimeout(() => {
      callback(null, {
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
  },
  // data() {
  //   return {}
  // },
}
</script>

<style scoped>
.intro {
  height: 300px;
  position: relative;
  padding: 30px;
  box-sizing: border-box;
  background-image: url('~assets/images/main-page-background.jpg');
  background-position: center;
  background-size: cover;
}

.intro h1 {
  position: absolute;
  top: 10%;
  left: 5%;
  width: 90%;
  font-size: 1.5rem;
  color: black;
  background-color: rgb(211, 211, 211);
  padding: 10px;
  border-radius: 10px;
  box-shadow: 3px 3px 3px black;
  box-sizing: border-box;
  border: 1px solid black;
}

@media (min-width: 768px) {
  .intro h1 {
    font-size: 2rem;
  }
}
</style>
