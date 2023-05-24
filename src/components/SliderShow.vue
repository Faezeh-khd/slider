<template>
  <div class="">
    <b-container>
      <b-row class="slider pt-4">
        <b-col
          cols="12"
          lg="5"
          md="5"
          class="d-flex align-items-start flex-column"
        >
          <div class="content-top fadeInDown mb-auto p-2">
            <h6>CLOSCA BOTTELE</h6>
            <p class="display-3">Savanna</p>
            <p class="display-6">$39.90</p>
          </div>

          <div class="content-bottem fadeInDown p-2">
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
            <img class="main-img fade-in" src="../assets/slide-flusk-1.png" />
            <img class="main-img fade-out" src="../assets/slide-flusk-2.png" />
          </div>
        </b-col>
        <b-col
          cols="12"
          lg="4"
          md="4"
          class="d-flex align-items-end flex-column p-0"
        >
          <div class="slidesNum me-3">
            <span class="current-slide fadeInDown">01</span>
            <span class="fadeOutDown">02</span>
            <span>/04</span>
          </div>
          <div class="wrapper-next-img my-5 d-flex align-items-center">
            <img class="next-img fade-in" src="../assets/slide-flusk-2.png" />
            <img class="next-img fade-out" src="../assets/slide-flusk-1.png" />
          </div>
          <div class="navigation-btn mt-5 me-3">
            <!-- <b-icon
              icon="arrow-left-circle"
              class="prev-btn"
              variant="secondary"
              aria-label="Prev"
            ></b-icon> -->
            <b-button
              variant="outline-secondary"
              class="prev-button fill-color rounded-circle p-3 m-2"
            >
              <b-icon-arrow-left variant="secondary"></b-icon-arrow-left
            ></b-button>
            <b-button
              variant="outline-secondary"
              class="next-button fill-color rounded-circle p-3 m-2"
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
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.slider {
  animation: changeColor 3s infinite;
  animation-direction: alternate;
}
.wrapper-main-img {
  position: relative;
}

.main-img {
  position: absolute;
  top: 15%;
  width: 60%;
  /* transition: all 0.5s ease; */
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
  animation: fadeInDown 3s infinite;
}
@keyframes fadeInDown {
  0%,
  100% {
    opacity: 0;
    -webkit-transform: translateY(-20px);
  }
  50% {
    opacity: 1;
    -webkit-transform: translateY(0);
  }
}
.fadeOutDown {
  animation: fadeOutDown 3s infinite;
}
@keyframes fadeOutDown {
  0%,
  100% {
    opacity: 1;
    -webkit-transform: translateY(0px);
  }
  50% {
    opacity: 0;
    -webkit-transform: translateY(20px);
  }
}
.fade-in {
  animation-name: fade-in;
  animation-duration: 3s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
.fade-out {
  animation-name: fade-out;
  animation-duration: 3s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}

@keyframes fade-in {
  from {
    opacity: 0;
    width: 50%;
  }

  to {
    opacity: 1;
  }
}
@keyframes fade-out {
  from {
    opacity: 1;
  }
  to {
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
.prev-button {
  animation-delay: 3s;
}
.fill-color {
  animation-name: fill-color;
  animation-duration: 6s;
  animation-iteration-count: infinite;
}
@keyframes fill-color {
  0%,
  100% {
    background-color: transparent;
    /* background: linear-gradient(to left, grey 50%, transparent 50%);
    background-size: 200% 100%;
    background-position: bottom left;
  */
  }

  50% {
    /* background-color: gray; */
    /* text-color: #ffffff'; */
    /* background-position: bottom right; */
    background-position: right top;
  }
}
</style>
