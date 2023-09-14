<template>
  <div class="post-list">
    <div v-for="post in posts" :key="post.id">
        <SinglePost :post="post" />
      <!-- <h3>{{ post.title }}</h3> -->
    </div>
  </div>
</template>

<script>
import { onMounted, onUnmounted, onUpdated } from 'vue';
import SinglePost from './SinglePost.vue'
export default {
  props: ["posts"],
  components: {SinglePost},
  setup(props){
    //props.posts
    onMounted(() => {
    }),
    onUnmounted(() => {

    }),
    onUpdated(() => {

    })

  }
};
</script>

<style></style>
