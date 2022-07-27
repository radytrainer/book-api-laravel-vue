<template>
  <div class="form-container">
        <form @submit.prevent="addBook">
            <div class="form-group">
                <input type="text" placeholder="Book title" v-model="title">
            </div>
            <div class="form-group">
                <input type="text" placeholder="Author" v-model="author">
            </div>
            <div class="form-group">
                <button type="submit">Add Book</button>
            </div>
        </form>
  </div>
</template>

<script>
export default {
    data() {
        return {
            title: '',
            author: '',
        }
    },
    methods:{
        addBook() {
            let newBook = {
                title: this.title,
                author: this.author, 
            } 
            this.$emit('addBook', newBook);
        }
    }
}
</script>

<style>
.form-container {
    margin-top: 10px;
    border-radius: 4px;
    box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
    padding: 10px;
    border-top:7px solid #e56e6e;
}
input {
    width: 100%;
    box-sizing: border-box;
    padding: 10px;
}
.form-group {
    margin-top: 10px;
}
.form-group button {
     padding: 10px;
    cursor: pointer;
    border:none;
    background: #f76363;
    color:#fff;
    border-radius: 40px;
    width: 100px;
}
</style>