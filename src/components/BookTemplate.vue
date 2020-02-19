<template>
  <div class="book-preview" >
    <h3>{{book.title}}</h3>
  </div>
</template>

<script>

export default {
props: ['book'],

data: function () {
  return {
    data: this.book
  }
}
}
</script>

<style>

.book-preview {
  height: 250px;
  width: 200px;
  margin: 0 0  0 10px;
  border-left: black 1px solid;
  display: flex;
  justify-content: flex-end;
  flex-direction: column
}

.book-preview h3 {
  font-size: 1.2em;
  margin: 3px;
  color: white
}
</style>