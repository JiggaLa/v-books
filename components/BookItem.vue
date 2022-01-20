<script>
export default {
  props: {
    coverUrl: { type: String, default: '' },
    title: { type: String, default: 'Book title' },
    authors: { type: Array, default: () => [] },
    isbn: { type: String, default: '' },
  },

  methods: {
    goToBook() {
      this.$router.push({ path: `/book/${this.isbn}` })
    },
  },
}
</script>

<template>
  <div class="w-full cursor-pointer" @click="goToBook()">
    <div
      class="book-cover"
      :style="{ backgroundImage: `url(${coverUrl})` }"
    ></div>
    <h3 class="text-2xl mt-8 mb-2 font-semibold">{{ title }}</h3>
    <div v-for="author in authors" :key="author.name">
      {{ author.name }}
    </div>
  </div>
</template>



<style lang="scss" scoped>
.book-cover {
  @apply w-full h-[513px] rounded-3xl bg-[#dedede] drop-shadow-2xl bg-center bg-no-repeat bg-cover;

  @apply hover:border-[6px] hover:border-blue-500;

  @apply transition-all duration-300 ease-v-ease;

  @screen lg {
    @apply h-[473px];
  }

  @screen md {
    @apply h-[64vw];
  }

  @screen sm {
    @apply h-[130vw];
  }
}
</style>