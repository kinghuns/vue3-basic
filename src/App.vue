<script setup>
import { onMounted } from 'vue'
import { ref } from 'vue'
import BlogPost from './BlogPost.vue'
import AlertBox from './AlertBox.vue';
  
const posts = ref([
  { id: 1, title: 'My journey with Vue' },
  { id: 2, title: 'Blogging with Vue' },
  { id: 3, title: 'Why Vue is so fun' }
])
const postFontSize = ref(1);

onMounted(() => {
  console.log('App component mounted.')
});

</script>

<template>
  <div :style="{ fontSize: postFontSize + 'em'}">
  <BlogPost
  	v-for="post in posts"
	  :key="post.id"
  	:title="post.title"
    @enlarge-text="postFontSize += 0.1"
	/>
  </div>
  <AlertBox>
    Something went wrong! 
    Please try again later.
  </AlertBox> 
	
</template>