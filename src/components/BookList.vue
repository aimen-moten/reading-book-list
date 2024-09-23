<template>
    <div class="bookList">
        <BookItem
            v-for="book in books"
            :title="book.title"
            :author="book.author"
            :image="book.image"
            @bookSelected="showBookSelected">
            <template #genre>
                <p> {{ book.genre }}</p>
            </template>
            <template #rating>
                <p> {{ book.rating }}</p>
            </template>
        </BookItem>
    </div>
    <h3 class="bookCount">Total Number of Books: {{ books.length }} </h3>
</template>

<script>
import BookItem from './BookItem.vue'

export default {
    components: {
        BookItem
    },
    data() {
        return {
            books: [
                {
                    title: 'The Alchemist',
                    author: 'Paulo Coelho',
                    image:'http://www.freepdfbook.com/wp-content/uploads/2021/05/0ebe9efa94145d429dd90c6243ed2f82.jpeg',
                    genre: 'Fiction',
                    rating: '4.5/5'
                },
                {
                    title: 'Elise and the New Partisans',
                    author: 'Dominique Grange',
                    image:'https://m.media-amazon.com/images/I/818KqP+I-JL._SL1500_.jpg',
                    genre:'Fiction',
                    rating: '3.8/5'
                },
                {
                    "title": "The Forgotten Labyrinth",
                    "author": "Dinesh Deckker",
                    "image": "https://m.media-amazon.com/images/I/41ZLx8t5uCL._SY445_SX342_.jpg",
                    "genre": "Mystery/Thriller",
                    "rating": "4.2/5"
                },
                {
                    "title": "Beneath the Copper Skies",
                    "author": "Emè Savage",
                    "image": "https://m.media-amazon.com/images/I/41gZgROXkZL._SY445_SX342_.jpg",
                    "genre": "Historical Fiction",
                    "rating": "4.0/5"
                },
                {
                    "title": "The Quantum Paradox",
                    "author": "A.J Nova",
                    "image": "https://m.media-amazon.com/images/I/41a2lJPfF6L._SY445_SX342_.jpg",
                    "genre": "Science Fiction",
                    "rating": "4.5/5"
                }
            ]
        }
    },
    methods: {
        showBookSelected(bookName) {
            alert(`You selected ${bookName}`)
        }
    }
}

</script>