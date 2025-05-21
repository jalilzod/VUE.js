<template>
  <li>
    {{ book.name }} by {{ book.author }} — ${{ book.price }}
    <img
      @click="toggleLike"
      :src="book.isClicked ? likeFill : likeEmpty"
      alt="like"
    />
    <img
      @click="$emit('add-to-cart', book)"
      :src="cartIcon"
      alt="cart"
    />
  </li>
</template>

<script>
export default {
  name: 'BookItem',
  props: {
    book: Object,
    cartIcon: String,
    likeEmpty: String,
    likeFill: String
  },
  methods: {
    toggleLike() {
      this.book.isClicked = !this.book.isClicked;
    }
  }
}
</script>
