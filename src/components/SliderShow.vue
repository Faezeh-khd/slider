<template>
  <div class="d-flex align-items-center justify-content-center min-vh-100">
    <b-container class="slider">
      <b-row class="pt-4">
        <b-col
          cols="12"
          lg="5"
          md="5"
          class="d-flex align-items-start flex-column"
        >
          <div
            class="content-top mb-auto p-2"
            v-bind:class="{ fadeInDown: isActive }"
          >
            <h6>CLOSCA BOTTELE</h6>
            <p class="display-3">Savanna</p>
            <p class="display-6">$39.90</p>
          </div>

          <div
            class="content-bottem p-2"
            v-bind:class="{ fadeInDown: isActive }"
          >
            <p>
              Lorem ipsum dolor, sit amet consectetur adipisicing elit. Esse
              temporibus sapiente error perspiciatis ducimus quos, qui ea vel
              nemo veritatis iure, amet nobis molestiae, laudantium at. Alias
              rem odit ratione?
            </p>
            <p>
              <span class="p-1">SHOP NOW</span>
              <b-icon-arrow-right></b-icon-arrow-right>
            </p>
          </div>
        </b-col>
        <b-col cols="12" lg="3" md="3">
          <div class="wrapper-main-img d-flex justify-content-center">
            <div class="background-main-image"></div>
            <img
              class="main-img"
              v-bind:class="{ fadeIn: isActive }"
              src="../assets/slide-flusk-1.png"
            />
            <img
              class="main-img fadeOut"
              v-bind:class="{ fadeOut: isActive }"
              src="../assets/slide-flusk-2.png"
            />
          </div>
        </b-col>
        <b-col
          cols="12"
          lg="4"
          md="4"
          class="d-flex align-items-end flex-column p-0"
        >
          <div class="slidesNum me-3">
            <span class="current-slide" v-bind:class="{ fadeInDown: isActive }"
              >01</span
            >
            <span class="fadeOutDown" v-bind:class="{ fadeOutDown: isActive }"
              >02</span
            >
            <span>/04</span>
          </div>
          <div class="wrapper-next-img my-5 d-flex align-items-center">
            <img
              class="next-img"
              v-bind:class="{ fadeIn: isActive }"
              src="../assets/slide-flusk-2.png"
            />
            <img
              class="next-img"
              v-bind:class="{ fadeOut: isActive }"
              src="../assets/slide-flusk-1.png"
            />
          </div>
          <div class="navigation-btn mt-5 me-3">
            <b-button
              @click="hasAnimat"
              v-bind:class="{ fillColor: isActive }"
              variant="outline-secondary"
              class="prev-button rounded-circle p-3 m-2"
            >
              <b-icon-arrow-left variant="secondary"></b-icon-arrow-left
            ></b-button>
            <b-button
              @click="hasAnimat"
              v-bind:class="{ fillColor: isActive }"
              variant="outline-secondary"
              class="next-button rounded-circle p-3 m-2"
            >
              <b-icon-arrow-right variant="secondary"></b-icon-arrow-right
            ></b-button>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  name: "SliderShow",
  props: {
    msg: String,
  },
  data() {
    return { isActive: true };
  },
  methods: {
    hasAnimat: function () {
      this.isActive = false;
      setTimeout(() => {
        this.isActive = true;
      }, 6000);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.slider {
  /* animation: changeColor 3s infinite;
  animation-direction: alternate; */
  background-color: #e9c08c;
  margin: auto;
}
.wrapper-main-img {
  position: relative;
}

.main-img {
  position: absolute;
  top: 15%;
  width: 60%;
}
.background-main-image {
  height: 400px;
  width: 100%;
  background-color: #cfcfbe;
  border-radius: 175px;
}
.slidesNum {
  font-size: 25px;
  position: relative;
  overflow: hidden;
}
.current-slide {
  animation-delay: 1s;
  position: absolute;
}
.wrapper-next-img {
  height: 300px;
  width: 30%;
  position: relative;
  overflow: hidden;
}
.next-img {
  width: 100%;
  position: absolute;
  right: -50%;
}

.fadeInDown {
  animation: fadeInDown 4s infinite;
}
@keyframes fadeInDown {
  0%,
  100% {
    opacity: 0;
    -webkit-transform: translateY(-20px);
  }
  25%,
  50% {
    opacity: 1;
    -webkit-transform: translateY(0);
  }
}
.fadeOutDown {
  animation: fadeOutDown 4s infinite;
}
@keyframes fadeOutDown {
  0%,
  100% {
    opacity: 1;
    -webkit-transform: translateY(0px);
  }
  25%,
  50% {
    opacity: 0;
    -webkit-transform: translateY(20px);
  }
}
.fadeIn {
  animation-name: fadeIn;
  animation-duration: 6s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
.fadeOut {
  animation-name: fadeOut;
  animation-duration: 6s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
    width: 50%;
  }
  30%,
  100% {
    opacity: 1;
  }
}
@keyframes fadeOut {
  0%,
  30% {
    opacity: 1;
  }
  100% {
    opacity: 0;
    width: 50%;
  }
}
@keyframes changeColor {
  from {
    background-color: #ebd6bc;
  }
  to {
    background-color: #e9c08c;
  }
}
.prev-button,
.next-button {
  background: linear-gradient(to right, transparent 50%, #1f1e21 50%);
  background-size: 200% 100%;
  background-position: left top;
}
.prev-button:hover,
.next-button:hover {
  background-color: #1f1e21 !important;
}
.prev-button {
  animation-delay: 3s;
}
.fillColor {
  animation-name: fillColor;
  animation-duration: 6s;
  animation-iteration-count: infinite;
}

@keyframes fillColor {
  0%,
  100% {
    background-color: transparent;
  }

  50% {
    background-position: right top;
  }
}
</style>
