<template>
  <div class="content">
    <router-link to="/"><button class="back">BACK</button></router-link>
    <router-view/>
  <div class="book-container">
    
    <BookTemplate class="big-book" v-bind:book="book" :style="{ backgroundColor: book.color}"/>
    <BookInfo class="book-info" v-bind:book="book"/>
  </div>
  </div>  
</template>

<script>
// @ is an alias to /src
import BookTemplate from '@/components/BookTemplate.vue'
import BookInfo from '@/components/BookInfo.vue'

export default {
  name: 'BookItem',
  computed: {
    books(){
      return this.$root.$data.books
    },
    book() {
      return this.books[this.$route.params.id - 1]
    }
  },

  components: {
    BookTemplate,
    BookInfo
  },

  methods: {
  }
}
</script>

<style lang="scss">

.content {
  background-color: black;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  .back {
    margin-top: 80px;
    margin-left: 120px;
    position: absolute;
    padding: 10px;
    border-radius: 10px;
    border: none;
    &:hover {
      cursor: pointer;
    }
  }
}

.book-info {
  height: 450px;
  width: 350px;
  margin: 20px;
  color: white;
  display:flex;
  flex-direction:column;

  button {
  width: 180px;
  height: 30px;
  margin-top: auto;
  }
  h3 {
  font-size: 1.7em;
  }

 h2 {
  font-size: 1em;
  margin-bottom: 30px;
  font-weight: 600;
  }

  

  .info-box {
    padding: 10px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    background-color: rgb(29, 27, 27);
    margin-top: 40px;

    p {
    font-size: .8em
    }
  }
}




.book-container {
  display: flex;
  margin: auto;
}

 .big-book {
  height: 450px;
  width: 350px;
  margin: 20px;
  border: 0 0 0 10px;
  border-left: black 1px solid ;
  display: flex;
  justify-content: flex-end;
  flex-direction: column;
}

.big-book h3 {
  color: black;
  font-size: 1.2em;
  margin: 20px
}
</style>