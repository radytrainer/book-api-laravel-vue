<template>
  <div class="card">
    <div class="card-title">
        <span>{{book.id}}</span>
    </div>
    <div class="card-body">
        <h2>{{book.title}}</h2>
    </div>
    <div class="card-footer">
        <h3>Author: <span class="author">{{book.author}}</span></h3>
        <button @click="deleteBook(book.id)">Delete</button>
    </div>
  </div>
</template>

<script>
export default {
    props: {
        book: Object
    },
    methods: {
        deleteBook(id) {
            this.$emit('deleteBook', id);
        }
    }
}
</script>

<style>
.card {
    margin-top: 10px;
    border-radius: 4px;
    box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
}
.card-title {
    padding: 10px;
    background: #ec7373;
}
.card-title span {
    background: #fff;
    border-radius: 50%;
    padding: 7px;
} 
.card-body {
    padding: 10px;
}
.card-footer {
    padding: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top:1px dotted #f76363;
}
.card-footer button {
    padding: 10px;
    cursor: pointer;
    border:none;
    background: #f76363;
    color:#fff;
    border-radius: 40px;
    width: 100px;
}
.card-body h2 {
    font-weight: 400;
    text-align: center;
    margin: 10px;
}
.card-footer h3 {
    font-weight: 300;
    margin: 0;
}
.author {
    color:#ec7373
}
</style>