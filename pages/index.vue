<template>
  <div class="">
    <nav
      class="navbar navbar-expand-lg navbar-dark bg-success"
      style="backgroung: #3a8d41;"
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
          <ul class="navbar-nav ml-auto">
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
    isLoading: true
  },
  components: {
    ContentLoader
  },
  data: function() {
    return {
      items: [
        {
          id: 1,
          name: "Brown Brim",
          imageUrl: "https://i.ibb.co/ZYW3VTp/brown-brim.png",
          price: 25
        },
        {
          id: 2,
          name: "Blue Beanie",
          imageUrl: "https://i.ibb.co/ypkgK0X/blue-beanie.png",
          price: 18
        },
        {
          id: 3,
          name: "Brown Cowboy",
          imageUrl: "https://i.ibb.co/QdJwgmp/brown-cowboy.png",
          price: 35
        },
        {
          id: 4,
          name: "Grey Brim",
          imageUrl: "https://i.ibb.co/RjBLWxB/grey-brim.png",
          price: 25
        },
        {
          id: 5,
          name: "Green Beanie",
          imageUrl: "https://i.ibb.co/YTjW3vF/green-beanie.png",
          price: 18
        },
        {
          id: 6,
          name: "Palm Tree Cap",
          imageUrl: "https://i.ibb.co/rKBDvJX/palm-tree-cap.png",
          price: 14
        },
        {
          id: 7,
          name: "Red Beanie",
          imageUrl: "https://i.ibb.co/bLB646Z/red-beanie.png",
          price: 18
        },
        {
          id: 8,
          name: "Wolf Cap",
          imageUrl: "https://i.ibb.co/1f2nWMM/wolf-cap.png",
          price: 14
        },
        {
          id: 9,
          name: "Blue Snapback",
          imageUrl: "https://i.ibb.co/X2VJP2W/blue-snapback.png",
          price: 16
        },
        {
          id: 30,
          name: "Camo Down Vest",
          imageUrl: "https://i.ibb.co/xJS0T3Y/camo-vest.png",
          price: 325
        },
        {
          id: 31,
          name: "Floral T-shirt",
          imageUrl: "https://i.ibb.co/qMQ75QZ/floral-shirt.png",
          price: 20
        },
        {
          id: 32,
          name: "Black & White Longsleeve",
          imageUrl: "https://i.ibb.co/55z32tw/long-sleeve.png",
          price: 25
        },
        {
          id: 33,
          name: "Pink T-shirt",
          imageUrl: "https://i.ibb.co/RvwnBL8/pink-shirt.png",
          price: 25
        },
        {
          id: 34,
          name: "Jean Long Sleeve",
          imageUrl: "https://i.ibb.co/VpW4x5t/roll-up-jean-shirt.png",
          price: 40
        },
        {
          id: 35,
          name: "Burgundy T-shirt",
          imageUrl: "https://i.ibb.co/mh3VM1f/polka-dot-shirt.png",
          price: 25
        }
      ]
    };
  },
  components: {
    Logo
  },
  mounted: function() {},
  methods: {},
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
/* .container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
} */
</style>
