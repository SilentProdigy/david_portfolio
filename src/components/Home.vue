<template>
  <div
    :class="{ 'bg-dark': nightMode, 'bg-white': !nightMode }"
    class="pt-5 p-st"
    id="banner-section"
    v-bind:style="{ 'background-image': 'url(' + bgimage + ')' }"
  >
    <div
      class="container"
      data-aos="fade"
      data-aos-once="true"
      data-aos-duration="1000"
    >
      <div class="row align-items-center">
        <div class="col-xl-6 col-bg-6 col-md-6 col-sm-12 text-center">
          <img :src="picture" />
        </div>
        <div class="col-xl-6 col-bg-6 col-md-6 col-sm-12 pt-5" id="description">
          <span
            class="home-title text-light"
            >Welcome!</span
          >
          <div>
            <p v-html="description" class="text-light"></p>
          </div>
          <div class="text-center pb-4">
            <button
              class="btn btn-outline-secondary mx-2"
              @click="open('instagram')"
              v-tooltip.bottom="'Instagram'"
            >
              <i class="fab fa-instagram"></i>
            </button>
            <button
              class="btn btn-outline-secondary mx-2"
              @click="open('facebook')"
              v-tooltip.bottom="'Facebook'"
            >
              <i class="fab fa-facebook"></i>
            </button>
            <button
              class="btn btn-outline-secondary mx-2"
              @click="open('youtube')"
              v-tooltip.bottom="'Twitter'"
            >
              <i class="fab fa-twitter"></i>
            </button>
            <button
              class="btn btn-outline-secondary mx-2"
              @click="open('resume')"
              v-tooltip.bottom="'Resume'"
            >
              Download my CV <i class="fas fa-link"></i>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import info from "../../info";

import Wave from "./helpers/Wave";

export default {
  name: "Home",
  components: {
    Wave,
  },
  props: {
    nightMode: {
      type: Boolean,
    },
  },
  data() {
    return {
      picture: info.flat_picture,
      description: info.description,
      name: info.name,
      instagram: info.links.instagram,
      facebook: info.links.facebook,
      youtube: info.links.youtube,
      resume: info.links.resume,
      bgimage: info.banner_image
    };
  },
  methods: {
    open(link) {
      switch (link) {
        case "instagram":
          window.open(this.instagram, "_blank");
          break;
        case "facebook":
          window.open(this.facebook, "_blank");
          break;
        case "youtube":
          window.open(this.youtube, "_blank");
          break;
        case "resume":
          window.open(this.resume, "_blank");
          break;
      }
    },
  },
};
</script>

<style scoped>
.home-title {
  font-size: 32px;
  font-weight: 500;
}

#banner-section{
  background-size: cover;
  background-attachment: fixed;
  background-repeat: no-repeat;
}

#description{
  background-color: rgba(0,0,0,0.8);
}


img {
  max-width: 700px;
  max-height: 600px;
  margin-top: 80px;
}

@media only screen and (max-width: 580px) {
  img {
    object-fit: cover;
    border-radius: 50%;
    height: 500px;
    width: 500px;
    margin-top: 10px;
    margin-bottom: 10px;
    border: 2px solid rgb(205, 205, 205);
    background-color: rgba(0,0,0,0.8);
  }
}

.fa {
  font-size: 15px;
}

.btn {
  border-color: #759CC9;
  color: #759CC9;
}

.btn:hover {
  background-color: #759CC9;
  border-color: #759CC9;
  color: white;
}

.btn:focus {
  background-color: #759CC9;
  border-color: #759CC9;
  color: white;
}

.btn:focus {
  outline: none !important;
}

p {
  text-align: justify;
  font-weight: 400;
}

/* LEAVES */
</style>
