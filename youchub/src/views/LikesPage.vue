<script>
// import ProductCard from "../components/ProductCard.vue";
import Navbar from "../components/Navbar.vue";
import VideoCard from "../components/VideoCard.vue";
import { useAllStore } from "../stores/all";
import { mapState, mapActions } from "pinia";

export default {
  name: "LikesPage",
  data() {
    return {
      currentPage: 0,
      // likes: [
      //   {
      //     link: "https://i.ytimg.com/vi/TOrFzCfwPrg/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDpcYPdcPmJyOFL4OG0i8TQjxOYVg",
      //     title:
      //       "Uncle Roger Review REYNOLD POERNOMO Fried Rice (Masterchef Finalist)",
      //     channel: "mrnigelng",
      //     views: "6.3M",
      //     publishedDate: "20111031",
      //   },
      //   {
      //     link: "https://i.ytimg.com/vi/TOrFzCfwPrg/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDpcYPdcPmJyOFL4OG0i8TQjxOYVg",
      //     title:
      //       "Uncle Roger Review REYNOLD POERNOMO Fried Rice (Masterchef Finalist)",
      //     channel: "mrnigelng",
      //     views: "6.3M",
      //     publishedDate: "20111031",
      //   },
      //   {
      //     link: "https://i.ytimg.com/vi/TOrFzCfwPrg/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDpcYPdcPmJyOFL4OG0i8TQjxOYVg",
      //     title:
      //       "Uncle Roger Review REYNOLD POERNOMO Fried Rice (Masterchef Finalist)",
      //     channel: "mrnigelng",
      //     views: "6.3M",
      //     publishedDate: "20111031",
      //   },
      //   {
      //     link: "https://i.ytimg.com/vi/TOrFzCfwPrg/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDpcYPdcPmJyOFL4OG0i8TQjxOYVg",
      //     title:
      //       "Uncle Roger Review REYNOLD POERNOMO Fried Rice (Masterchef Finalist)",
      //     channel: "mrnigelng",
      //     views: "6.3M",
      //     publishedDate: "20111031",
      //   },
      //   {
      //     link: "https://i.ytimg.com/vi/TOrFzCfwPrg/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDpcYPdcPmJyOFL4OG0i8TQjxOYVg",
      //     title:
      //       "Uncle Roger Review REYNOLD POERNOMO Fried Rice (Masterchef Finalist)",
      //     channel: "mrnigelng",
      //     views: "6.3M",
      //     publishedDate: "20111031",
      //   },
      //   {
      //     link: "https://i.ytimg.com/vi/TOrFzCfwPrg/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDpcYPdcPmJyOFL4OG0i8TQjxOYVg",
      //     title:
      //       "Uncle Roger Review REYNOLD POERNOMO Fried Rice (Masterchef Finalist)",
      //     channel: "mrnigelng",
      //     views: "6.3M",
      //     publishedDate: "20111031",
      //   },
      //   {
      //     link: "https://i.ytimg.com/vi/TOrFzCfwPrg/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDpcYPdcPmJyOFL4OG0i8TQjxOYVg",
      //     title:
      //       "Uncle Roger Review REYNOLD POERNOMO Fried Rice (Masterchef Finalist)",
      //     channel: "mrnigelng",
      //     views: "6.3M",
      //     publishedDate: "20111031",
      //   },
      //   {
      //     link: "https://i.ytimg.com/vi/TOrFzCfwPrg/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDpcYPdcPmJyOFL4OG0i8TQjxOYVg",
      //     title:
      //       "Uncle Roger Review REYNOLD POERNOMO Fried Rice (Masterchef Finalist)",
      //     channel: "mrnigelng",
      //     views: "6.3M",
      //     publishedDate: "20111031",
      //   },
      // ],
    };
  },
  components: {
    // ProductCard,
    Navbar,
    VideoCard,
  },
  computed: {
    ...mapState(useAllStore, ["likes"]),
  },
  methods: {
    ...mapActions(useAllStore, ["fetchLikes"]),
  },
  created() {
    this.fetchLikes();
  },
};
</script>

<template>
  <main>
    <Navbar page="likes" />
    <!-- tambah searchbar + btn speech recognition, akun, tombol lonceng di navbar  -->
    <section class="container-fluid my-3" id="home-section">
      <h1 class="text-center">
        <!-- <span class="material-symbols-outlined"> favorite </span> -->
        Liked Videos
        <!-- <span class="material-symbols-outlined"> favorite </span> -->
      </h1>
      <div class="ms-sm-auto px-md-5">
        <div>
          <!-- tambah button isi category2 -->
          <CategoryBar />
        </div>
        <div v-if="likes.length > 0" class="row gx-5 p-3">
          <VideoCard
            v-for="(like, i) in likes"
            :key="i"
            :video="like.Video"
            :date="like.Video.publishedDate.slice(0, 10)"
            page="likes"
          />
        </div>
        <div class="text-center pt-4" v-else>
          <img src="../assets/box.png" width="230" alt="" />
          <div class="row m-5">
            <p class="fw-bold fs-4 mb-2">Nothing to see here..</p>
            <p class="fs-6">
              Looks like you haven't added anything to your list
            </p>
            <div class="">
              <a
                @click.prevent="$router.push('/')"
                class="btn btn-dark rounded-pill fw-bold px-5 text-decoration-none"
                >Start adding one!</a
              >
            </div>
          </div>
        </div>
        <!-- pagination -->
        <!-- <div v-if="totalPage > 1" class="d-flex justify-content-end mt-5">
            <nav aria-label="">
              <ul class="pagination">
                <li
                  class="page-item"
                  :class="currentPage === 0 ? 'disabled' : ''"
                >
                  <a
                    @click.prevent="handleClick(currentPage - 1)"
                    class="page-link"
                    >Previous</a
                  >
                </li>
                <li
                  v-for="index in totalPage"
                  :key="index"
                  class="page-item"
                  :class="currentPage === index - 1 ? 'disabled' : ''"
                >
                  <a
                    @click.prevent="handleClick(index - 1)"
                    class="page-link"
                    href="#"
                    >{{ index }}</a
                  >
                </li>
                <li
                  class="page-item"
                  :class="currentPage === totalPage - 1 ? 'disabled' : ''"
                >
                  <a
                    @click.prevent="handleClick(currentPage + 1)"
                    class="page-link"
                    href="#"
                    disabled
                    >Next</a
                  >
                </li>
              </ul>
            </nav>
          </div> -->
      </div>
    </section>
  </main>
</template>
