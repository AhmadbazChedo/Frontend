<template>
  <div class="book-list">
    <h2>Meine Bücher</h2>
    <div v-if="books.length === 0">
      <p>Keine Bücher gefunden.</p>
    </div>
    <div v-else>
      <ul>
        <!-- v-for Schleife zum Rendern jedes Buches direkt innerhalb der gleichen Komponente -->
        <li v-for="book in books" :key="book.id" class="book-item">
          <h3>{{ book.title }}</h3>
          <p><strong>Autor:</strong> {{ book.author }}</p>
          <p><strong>Genre:</strong> {{ book.genre }}</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BookList',
  data() {
    return {
      // Beispielhafte Bücherliste
      books: [
        { id: 1, title: 'Der Herr der Ringe', author: 'J.R.R. Tolkien', genre: 'Fantasy' },
        { id: 2, title: '1984', author: 'George Orwell', genre: 'Dystopie' },
        { id: 3, title: 'Die Unendliche Geschichte', author: 'Michael Ende', genre: 'Fantasy' },
      ],
    };
  },
};
</script>

<style scoped>
.book-list {
  font-family: Arial, sans-serif;
}

h2 {
  text-align: center;
}

ul {
  list-style-type: none;
  padding: 0;
}

.book-item {
  border: 1px solid #ddd;
  padding: 15px;
  margin: 10px 0;
  border-radius: 5px;
  background-color: #f9f9f9;
}

.book-item h3 {
  margin: 0 0 10px 0;
}

.book-item p {
  margin: 5px 0;
}
</style>

