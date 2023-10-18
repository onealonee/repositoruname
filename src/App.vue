<template>
  <div class="app">
    <PostForm
        @create="createPost"
    />
    <PostList
        :posts="posts"
        @remove="removePost"
    />
  </div>
</template>

<script>
import PostList from "@/components/PostList.vue";
import PostForm from "@/components/PostForm.vue";
export default {
  components: {
    PostForm, PostList
  },
  data() {
    return{
      posts: [
        {id: 1, title: 'Javacript', body: 'Описание поста'},
        {id: 2, title: 'Javacript 2', body: 'Описание поста 2'},
        {id: 3, title: 'Javacript 3', body: 'Описание поста 3'},
      ],
    }
  },
  methods: {
    createPost(post){
      this.posts.push(post);
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app  {
  padding: 20px;
}

</style>