<template>
    <form v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)" action="#" class="" method="post">
        <input type="text" name="title" id="book-title" v-model="bookTitle" placeholder="Book Title">
        <input type="text" name="author" id="book-author" v-model="bookAuthor" placeholder="Book Auhor">
        <button type="submit" name="button">Add Book</button>
    </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookTitle: "",
      bookAuthor: ""
    };
  },
  methods: {
    bookSubmit(bookTitle, bookAuthor) {
      this.$emit("addBook", bookTitle, bookAuthor);
    }
  }
};
</script>

<style>
</style>
