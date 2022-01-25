<template>
    <form @submit.prevent>
        <input
          v-bind:value="title"
          @input="title = $event.target.value"
              class="input"
          type="text"
          placeholder="name"
        >
        <input
          v-bind:value="body"
          @input="body = $event.target.value"
          class="input"
          type="text"
          placeholder="dfa"
        >
        <button @click="createPost">create</button>
    </form>
    <div class="post" v-for="post in posts">
      <div>Name: {{ post.title }}</div>
      <div>desc: {{ post.body }}</div>
    </div>
</template>
<script>
export default {
  data() {
    return {
      posts: [
        { id: 1, title: "java", body: "Desc" },
        { id: 2, title: "java", body: "yda" },
      ],
      title:'',
      body:''
    };
  },
  methods: {
    createPost(event) {
      
      const Newpost = {
        id: 5,
        title: this.title,
        body: this.body,
      }
      debugger
      this.posts.push(Newpost)
      this.title= ''
    },
  },
};
</script>

<style>
* {
  margin: 0%;
  padding: 0%;
  box-sizing: border-box;
}
.post {
  padding: 15px;
  border: 1px solid teal;
}
</style>  