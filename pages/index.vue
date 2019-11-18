<template>
  <div class="">
    <nav
      class="navbar navbar-expand-lg navbar-dark"
      style="background: #3a8d41 !important;"
    >
      <div class="container">
        <a class="navbar-brand" href="#">
          <img src="~assets/Logo.png" width="80" />
        </a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ml-auto text-uppercase">
            <li class="nav-item active">
              <a class="nav-link" href="#">Login</a>
            </li>
            <li class="nav-item active">
              <a class="nav-link " href="#" tabindex="-1" aria-disabled="true"
                >Need Help</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- Navbar -->
    <div class="container mt-5">
      <b-carousel
        id="carousel-fade"
        style="text-shadow: 0px 0px 2px #000"
        fade
        indicators
        img-width="1024"
        img-height="480"
        :interval="4000"
        controls
      >
        <b-carousel-slide
          v-for="(item, index) in items"
          :key="index"
          :caption="item.name"
          :img-src="item.imageUrl"
        ></b-carousel-slide>
      </b-carousel>
    </div>
    <!-- Carousel -->
    <div class="container mt-5">
      <h2 class="mb-4">Merchant</h2>
      <div class="row">
        <div
          class="col-md-4 col-lg-3"
          v-for="(item, index) in items"
          :key="index"
          style="margin-bottom: 2rem;"
        >
          <div class="card my-card">
            <div class="" style="overflow: hidden;height: 250px;">
              <img
                :src="item.imageUrl"
                class="card-img-top"
                :alt="item.id"
                style="height: 250px;display: block;width: 100%;object-fit: cover; "
              />
            </div>
            <div class="card-body">
              <h5 class="card-title text-center">{{ item.name }}</h5>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from "~/assets/Logo.png";
import { SHOP_DATA } from "~/components/data";
import { ContentLoader } from "vue-content-loader";

export default {
  state: {
    isLoading: true,
    items: SHOP_DATA
  },
  components: {
    ContentLoader
  },
  data: function() {
    return SHOP_DATA;
  },
  components: {
    Logo
  },
  mounted: function() {},
  methods: {
    methodMap: function() {
      console.log(SHOP_DATA);
    }
  },
  computed: {}
};
</script>

<style>
body {
  background-color: #fafafa;
}
.my-card {
  border: 1px solid #eee;
}
.navbar-dark .navbar-nav .nav-link {
  color: "#fff";
}
.carousel-item {
  position: relative;
  display: none;
  float: left;
  width: 100%;
  height: 500px;
  margin-right: -100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
  transition: -webkit-transform 0.6s ease-in-out;
  -webkit-transition: -webkit-transform 0.6s ease-in-out;
  transition: transform 0.6s ease-in-out;
  transition: transform 0.6s ease-in-out, -webkit-transform 0.6s ease-in-out;
}

.carousel-item img {
  height: 600px;
  display: block;
  width: 100%;
  object-fit: cover;
}
</style>
