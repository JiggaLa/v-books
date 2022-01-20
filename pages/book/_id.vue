<script>
export default {
  data() {
    return {
      isbn: undefined,
      book: undefined,
    }
  },

  fetch() {
    console.log(this.$route.params.id)
    this.isbn = `ISBN:${this.$route.params.id}`

    const openLibraryAPIUrl = `https://openlibrary.org/api/books?bibkeys=${this.isbn}&format=json&jscmd=data`

    this.$axios
      .get(openLibraryAPIUrl)
      .then((res) => {
        this.book = res.data[this.isbn]
        console.log(this.book)
      })
      .catch((err) => {
        console.error(err)
      })
  },

  fetchOnServer: false,
}
</script>

<template>
  <main class="container min-h-[100vh]">
    <section
      class="
        relative
        flex flex-col
        items-center
        w-full
        mb-16
        min-h-[100vh]
        2xl:min-h-[auto]
      "
    >
      <Header />

      <div
        class="
          absolute
          w-[800px]
          h-[800px]
          mt-[-13%]
          rounded-[50%]
          bg-[#f8e6e5]
          blur-[200px]
          lg:mr-0 lg:mt-[-17%]
          md:mt-[-40%]
        "
      ></div>

      <div
        v-if="$fetchState.pending"
        class="w-full h-[100vh] flex justify-center items-center"
      >
        <SkChase />
      </div>

      <section v-else-if="$fetchState.error" class="book-detail-wrapper">
        Book not found.
      </section>

      <section v-else-if="book" class="book-detail-wrapper">
        <div class="flex items-start w-full md:flex-col md:items-stretch">
          <div
            class="book-cover"
            :style="{
              backgroundImage: `url(${book ? book.cover.large : ''})`,
            }"
          ></div>
          <div
            class="
              flex flex-col
              items-start
              ml-10
              w-[50%]
              lg:w-[50%]
              md:w-full md:ml-0 md:mt-10
            "
          >
            <h1
              class="
                font-bold
                text-[70px]
                lg:w-full lg:text-[66px]
                md:text-[60px]
                sm:text-[50px]
              "
            >
              {{ book.title }}
            </h1>

            <span
              v-if="book"
              class="mt-5 mb-16 text-[#929292] text-4xl flex flex-col"
              >by
              <span
                v-for="author in book.authors"
                :key="author.name"
                class="my-2"
                >{{ author.name }}</span
              >
            </span>

            <span class="my-1 text-[#929292] text-lg"
              ><strong>Published:</strong> {{ book.publish_date }}</span
            >

            <span class="my-1 text-[#929292] text-lg"
              ><strong>Number of pages:</strong>
              {{ book.number_of_pages }}</span
            >

            <span class="my-1 text-[#929292] text-lg"
              ><strong>ISBN 10:</strong> {{ book.identifiers.isbn_10[0] }}</span
            >

            <span class="my-1 text-[#929292] text-lg"
              ><strong>classification:</strong>
              {{
                book.classifications
                  ? book.classifications.lc_classifications[0]
                  : 'Not available'
              }}</span
            >
          </div>
        </div>
      </section>
    </section>
  </main>
</template>



<style lang="scss" scoped>
.v-brand-wrapper,
.book-detail-wrapper {
  @apply relative z-20 w-full max-w-[1440px] pt-6 px-16 flex flex-col items-start;

  @screen md {
    @apply px-6;
  }
}

.book-detail-wrapper {
  @apply my-28;

  @screen md {
    @apply mt-20;
  }
}

.book-cover {
  @apply w-[345px] h-[513px] rounded-3xl bg-[#dedede] drop-shadow-2xl bg-center bg-no-repeat bg-cover;

  @screen lg {
    @apply h-[473px];
  }

  @screen md {
    @apply h-[120vw] w-full;
  }
}
</style>