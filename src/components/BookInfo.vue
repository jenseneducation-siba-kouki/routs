<template>
  <div class="book-info" >
    <h3 class="book-title">{{book.title}}</h3>
    <h2>By {{book.author}}</h2>
    <p>{{book.plot}}</p>
    <div class="info-box">
        <p><strong>Audience:</strong> {{book.audience}}</p>
        <p><strong>First published:</strong> {{book.year}}</p>
        <p><strong>Pages:</strong> {{book.pages}}</p>
        <p><strong>Publisher:</strong> {{book.publisher}}</p>
    </div>
    <button>Oh, I want to read it!</button>
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

</style>