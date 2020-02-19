<template>
      <div class="home ">
        <h1>8 Classic Childrens books</h1>
          <div class="nav book-list">
            <router-link v-for="book in books" 
            :key="book.id" 
            :to="'/bookitem/' + book.id" 
            :style="{ backgroundColor: book.color}">
              <BookTemplate v-bind:book="book"/>
            </router-link>
            
          </div>
        <router-view/>
      </div>
</template>

<script>
// @ is an alias to /src
import BookTemplate from '@/components/BookTemplate.vue'

export default {
  name: 'Home',
  computed: {
    books(){
      return this.$root.$data.books
    }
  },
  components: {
    BookTemplate
  }
}
</script>

<style>
 .book-list {
   display: grid;
   grid-template-columns: 1fr 1fr 1fr 1fr;
   grid-template-rows: auto;
   width: 800px;
   margin: auto;
   justify-items: center;
   grid-gap: 10px;
 }

 h1 {
   margin: 50px 0 20px 100px;
 }
</style>