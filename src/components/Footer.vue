<template>
  <div class="bg-secondary">
    <div class="container py-3">
      <div class="row pt-1 align-items-center">
        <div
          class="col-xl-6 col-bg-6 col-md-6 col-sm-12 pbelow"
          style="color: white;"
        >
          
        </div>

        <div class="col-xl-6 col-bg-6 col-md-6 col-sm-12">
          <div class="text-center">
            <button
              class="btn btn-outline-secondary mx-2 "
              @click="open('facebook')"
            >
              <i class="fab fa-facebook"></i>
            </button>
            <button
              class="btn btn-outline-secondary mx-2"
              @click="open('instagram')"
            >
              <i class="fab fa-instagram"></i>
            </button>
            <button
              class="btn btn-outline-secondary mx-2"
              @click="open('youtube')"
            >
              <i class="fab fa-youtube"></i>
            </button>
            <button
              class="btn btn-outline-secondary mx-2"
              @click="open('resume')"
            >
              <i class="fa fa-file"></i>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import info from "../../info";

export default {
  name: "Footer",
  data() {
    return {
      instagram: info.links.instagram,
      facebook: info.links.facebook,
      youtube: info.links.youtube,
      resume: info.links.resume,
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
span {
  font-weight: 500;
}

.btn {
  border-color: white;
  color: white;
}

.btn:hover {
  background-color: white;
  border-color: white;
  color: gray;
}

.btn:focus {
  background-color: white;
  border-color: white;
  color: gray;
}

@media screen and (max-width: 580px) {
  .pbelow {
    padding-bottom: 20px;
    text-align: center;
  }
}
</style>
