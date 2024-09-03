<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">toggle posts</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostList from '@/components/PostList.vue';
import { ref } from 'vue';

// @ is an alias to /src

export default {
  name: 'HomeView',
  components: {
    PostList,
  },
  setup() {
    const posts = ref([
      {
        title: 'welcome to the blog',
        body: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Iure minima ut, voluptas dicta et incidunt recusandae quisquam iste repellendus assumenda, nulla vitae ducimus pariatur harum aspernatur delectus commodi dolorum deserunt ipsum, fugiat eius ea voluptatum ad sint? Sapiente, aspernatur modi quidem consequuntur porro ea. Consectetur laborum culpa quos recusandae doloremque dolore minus quis reiciendis consequatur, quisquam temporibus dolores necessitatibus commodi tenetur! Modi, libero, provident tenetur corrupti corporis, nulla nobis minima eius dignissimos inventore amet! Vero distinctio nihil corporis repudiandae sint optio ut atque maxime animi saepe qui labore aspernatur vel doloremque autem eum voluptatem earum, consequatur illo culpa incidunt repellendus!',
        id: 1,
      },
      { title: 'top 5 CSS tips', body: 'lorem ipsum', id: 2 },
    ]);
    const showPosts = ref(true);

    return { posts, showPosts };
  },
};
</script>
