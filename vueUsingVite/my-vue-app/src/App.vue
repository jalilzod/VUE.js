<script>
import cartIcon from './assets/images/shop.png';
import delIcon from './assets/images/del.png';
import likeEmpty from './assets/images/likeEmpt.png';
import likeFill from './assets/images/likeFill.png';
import BookItem from './components/BookItem.vue';

export default {
  components: {
    BookItem
  },
  data() {
    return {
      cartIcon,
      delIcon,
      likeEmpty,
      likeFill,
      books: [
        { name: 'C Prime', author: 'Stephen Prata', price: 23.5, isClicked: false },
        { name: 'Java Core', author: 'Cay Horstmann', price: 30.5, isClicked: false },
        { name: 'Spring Framework', author: 'Craig Walls', price: 15.5, isClicked: false }
      ],
      cart: [],
      total: 0
    }
  },
  methods: {
    addToCart(book) {
      this.cart.push(book);
      this.total += book.price;
    },
    removeFromCart(book) {
      const i = this.cart.indexOf(book);
      if (i !== -1) {
        this.cart.splice(i, 1);
        this.total -= book.price;
      }
    }
  }
}
</script>

<template>
  <div>
    <ul>
      <BookItem
        v-for="book in books"
        :key="book.name"
        :book="book"
        :cart-icon="cartIcon"
        :like-empty="likeEmpty"
        :like-fill="likeFill"
        @add-to-cart="addToCart"
      />
    </ul>

    <h2>🛒 Cart — Total: {{ total }}$</h2>
    <ul>
      <li v-for="item in cart" :key="item.name">
        {{ item.name }} — {{ item.price }}
        <img @click="removeFromCart(item)" :src="delIcon" alt="delete" />
      </li>
    </ul>
  </div>
</template>
