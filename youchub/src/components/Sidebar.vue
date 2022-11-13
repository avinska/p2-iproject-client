<script>
import { useAllStore } from "../stores/all";
import { mapActions, mapState } from "pinia";

export default {
  name: "Sidebar",
  components: {},
  data() {
    return {};
  },
  computed: {
    ...mapState(useAllStore, ["isPremium"]),
  },
  methods: {
    ...mapActions(useAllStore, ["showErrorAlert"]),
    handleClick() {
      console.log("miawww");
      if (this.isPremium) {
        this.$router.push("/likes");
      } else {
        this.showErrorAlert(
          "You need to subscribe to our premium plan to enjoy this feature"
        );
      }
    },
  },
};
</script>

<template>
  <nav
    class="col-md-3 col-lg-2 d-md-block bg-white sidebar collapse"
    id="sidebar-menu"
  >
    <div class="position-sticky pt-4 ms-1">
      <ul class="nav flex-column border-bottom py-3">
        <li class="nav-item">
          <a
            @click.prevent="$router.push('/')"
            class="nav-link"
            href=""
            id="nav-dashboard"
          >
            <span class="icon material-symbols-outlined me-3">home</span>Home</a
          >
        </li>
        <li class="nav-item">
          <a
            @click.prevent="handleClick"
            class="nav-link"
            href=""
            id="nav-category"
          >
            <span class="icon material-symbols-outlined me-3">thumb_up</span
            >Liked Videos</a
          >
        </li>
        <li class="nav-item">
          <a @click.prevent="" class="nav-link" href="" id="nav-product">
            <span class="icon material-symbols-outlined me-3"
              >subscriptions</span
            >Subscriptions</a
          >
        </li>
      </ul>
      <ul class="nav flex-column border-bottom py-3">
        <li class="nav-item">
          <a
            @click.prevent=""
            class="nav-link active"
            href=""
            id="nav-dashboard"
          >
            <span class="icon material-symbols-outlined me-3">history</span
            >History</a
          >
        </li>
        <li class="nav-item">
          <a @click.prevent="" class="nav-link" href="" id="nav-product">
            <span class="icon material-symbols-outlined me-3"
              >smart_display</span
            >Your Videos</a
          >
        </li>
        <li class="nav-item">
          <a @click.prevent="" class="nav-link" href="" id="nav-category">
            <span class="icon material-symbols-outlined me-3">schedule</span
            >Watch Later</a
          >
        </li>
        <li class="nav-item">
          <a @click.prevent="" class="nav-link" href="" id="nav-product">
            <span class="icon material-symbols-outlined me-3"
              >video_library</span
            >Library</a
          >
        </li>
        <li class="nav-item">
          <a @click.prevent="" class="nav-link" href="" id="nav-product">
            <span class="icon material-symbols-outlined me-3"
              >playlist_play</span
            >Rituals</a
          >
        </li>
      </ul>
      <h6
        class="sidebar-heading d-flex justify-content-between align-items-center px-3 mt-4 mb-1 text-muted text-uppercase"
      >
        <span>Subscriptions</span>
      </h6>
      <ul class="nav flex-column mb-2">
        <li class="nav-item">
          <a @click.prevent="" class="nav-link">
            <img
              src="https://yt3.ggpht.com/ytc/AMLnZu8fOEH7slYkWSVPXc5-7aiKhsz93NRtulPKHzAv3Q=s88-c-k-c0x00ffffff-no-rj"
              alt=""
              class="img-fluid rounded-circle me-2"
              width="30"
            />
            Yulia Batschun
          </a>
        </li>
        <li class="nav-item">
          <a @click.prevent="" class="nav-link">
            <img
              src="https://yt3.ggpht.com/ytc/AMLnZu-VqpYmb-17O5nhVIBX3cA18oMQh0sy-sJ690AqTA=s88-c-k-c0x00ffffff-no-rj"
              alt=""
              class="img-fluid rounded-circle me-2"
              width="30"
            />
            Devina Hermawan
          </a>
        </li>
        <li class="nav-item">
          <a @click.prevent="" class="nav-link">
            <img
              src="https://yt3.ggpht.com/ytc/AMLnZu-suO17gEU9kg0AEe5wR_qDCYdQeDeC1ANzq21BrA=s88-c-k-c0x00ffffff-no-rj"
              alt=""
              class="img-fluid rounded-circle me-2"
              width="30"
            />
            Jess Dang
          </a>
        </li>
        <li class="nav-item">
          <a @click.prevent="" class="nav-link">
            <img
              src="https://yt3.ggpht.com/ytc/AMLnZu-gvNMCqNLnYDrF2a3kwHe7cSfmcA_9guf13AHGBg=s88-c-k-c0x00ffffff-no-rj"
              alt=""
              class="img-fluid rounded-circle me-2"
              width="30"
            />
            Ken Jee
          </a>
        </li>
        <li class="nav-item">
          <a @click.prevent="" class="nav-link">
            <img
              src="https://yt3.ggpht.com/ytc/AMLnZu8nk-3KY81Pc22NNYXv4HSa1z5hpfL5zo8U8dZ_8A=s88-c-k-c0x00ffffff-no-rj"
              alt=""
              class="img-fluid rounded-circle me-2"
              width="30"
            />
            Cooking With Dog
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>
