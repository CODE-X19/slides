<template>
  <div class="container">
    <div class="slide">
      <div
        class="item"
        style="background-image: url('/assets/Zuma.webp');"
      >
        <div class="content" v-if="currentIndex === 0">
          <div class="name" style="color: rgb(248, 202, 202);">Zuma Rock, Niger</div>
          <div class="des">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ab, eum!</div>
          <button>See More</button>
        </div>
      </div>
      <div
        class="item"
        style="background-image: url('/assets/Awhum (Ohum) Cave, Enugu.jpg');"
      >
        <div class="content" v-if="currentIndex === 1">
          <div class="name">AWHUM WATERFALL</div>
          <div class="des">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ab, eum!</div>
          <button>See More</button>
        </div>
      </div>
      <div
        class="item"
        style="background-image: url('/assets/The Obudu Holy Mountain, Cross River State2.webp');"
      >
        <div class="content" v-if="currentIndex === 2">
          <div class="name">The Obudu Holy Mountain</div>
          <div class="des">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ab, eum!</div>
          <button>See More</button>
        </div>
      </div>
      <div
        class="item"
        style="background-image: url('/assets/Gurara Waterfall, Niger.jpg');"
      >
        <div class="content" v-if="currentIndex === 3">
          <div class="name">Gurara Waterfall</div>
          <div class="des">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ab, eum!</div>
          <button>See More</button>
        </div>
      </div>
      <div
        class="item"
        style="background-image: url('/assets/Idanre Hill, Ondo.jpg');"
      >
        <div class="content" v-if="currentIndex === 4">
          <div class="name">Idanre Hill, Ondo</div>
          <div class="des">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ab, eum!</div>
          <button>See More</button>
        </div>
      </div>
      <div
        class="item"
        style="background-image: url('/assets/Agbokim Waterfall.jpg');"
      >
        <div class="content" v-if="currentIndex === 5">
          <div class="name">Agbokim Waterfall</div>
          <div class="des">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ab, eum!</div>
          <button>See More</button>
        </div>
      </div>
    </div>
    <div class="button">
      <button @click="prev" class="prev"><i class="fa-solid fa-arrow-left"></i></button>
      <button @click="next" class="next"><i class="fa-solid fa-arrow-right"></i></button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
    };
  },
  methods: {
    next() {
      this.currentIndex = (this.currentIndex + 1) % 6;
    },
    prev() {
      this.currentIndex = (this.currentIndex - 1 + 6) % 6;
    }
  }
};
</script>

<style scoped>
/* Add your CSS here */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #98d3fa;
  overflow: hidden;
}

.container {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 1000px;
  height: 600px;
  background: #f5f5f5;
  box-shadow: 0 30px 50px #dbdbdb;
}

.container .slide .item {
  width: 200px;
  height: 300px;
  position: absolute;
  top: 50%;
  transform: translate(0, -50%);
  border-radius: 20px;
  box-shadow: 0 30px 50px #505050;
  background-position: 50% 50%;
  background-size: cover;
  display: inline-block;
  transition: 0.5s;
}

.slide .item:nth-child(1),
.slide .item:nth-child(2) {
  top: 0;
  left: 0;
  transform: translate(0, 0);
  border-radius: 0;
  width: 100%;
  height: 100%;
}

.slide .item:nth-child(3) {
  left: 50%;
}

.slide .item:nth-child(4) {
  left: calc(50% + 220px);
}

.slide .item:nth-child(5) {
  left: calc(50% + 440px);
}

/* here n = 0, 1, 2, 3,... */
.slide .item:nth-child(n + 6) {
  left: calc(50% + 660px);
  opacity: 0;
}

.item .content {
  position: absolute;
  top: 50%;
  left: 100px;
  width: 300px;
  text-align: left;
  color: #eee;
  transform: translate(0, -50%);
  font-family: system-ui;
  display: none;
}

.slide .item:nth-child(2) .content {
  display: block;
}

.content .name {
  font-size: 40px;
  text-transform: uppercase;
  font-weight: bold;
  opacity: 0;
  animation: animate 1s ease-in-out 1 forwards;
}

.content .des {
  margin-top: 10px;
  margin-bottom: 20px;
  opacity: 0;
  animation: animate 1s ease-in-out 0.3s 1 forwards;
}

.content button {
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  opacity: 0;
  animation: animate 1s ease-in-out 0.6s 1 forwards;
}

@keyframes animate {
  from {
    opacity: 0;
    transform: translate(0, 100px);
    filter: blur(33px);
  }
  to {
    opacity: 1;
    transform: translate(0);
    filter: blur(0);
  }
}

.button {
  width: 100%;
  text-align: center;
  position: absolute;
  bottom: 20px;
}

.button button {
  width: 40px;
  height: 35px;
  border-radius: 8px;
  border: none;
  cursor: pointer;
  margin: 0 5px;
  border: 1px solid #000;
  transition: 0.3s;
}

.button button:hover {
  background: #ababab;
  color: #fff;
}
</style>