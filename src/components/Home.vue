<template>
  <div id="app" :class="{ backgroundTheme: !light }">
    <nav class="main-nav">
      <svg
        class="logo"
        :class="{ logoFillLight: !light }"
        xmlns="http://www.w3.org/2000/svg"
        width="141.2"
        height="18.5"
        viewBox="0 0 141.2 18.5"
      >
        <path
          d="M7 18.2h1.4L16.8.1h-2.2L8 15 2.5.2H0zm9.3 0l2.4-5.9h7.9l2.1 5.9h2.4L24.1.1h-1.7L14 18.2zm6.6-15.8L26 11h-6.7zM34 18.2h11.4v-1.7h-9.1V.1H34zm13.8 0h11.7v-1.6h-9.5V9.4h8.4V7.8H50V1.7h9.4V0H48zm15.3 0h2.2v-7.7a16.2 16.2 0 0 0 3.5-.1c4.4 7.5 5.7 8 8.4 8 .2 0 .4 0 .5-.3l.2-.8a4.8 4.8 0 0 1-2.5-1.3 34.4 34.4 0 0 1-4.3-6.1c1-.4 3.8-1.6 3.8-5a5.1 5.1 0 0 0-1.3-3.6C72.5.2 70.9 0 68 0h-4.9zM68 1.5c1.9 0 4.6 0 4.6 3.6s-3 4-5.2 4a15.8 15.8 0 0 1-2-.1V1.6l2.6-.1zM80.7 0v18.1h2.2V.1zm7.5 18.1l2.4-5.9h7.9l2.1 5.9h2.5L96 .1h-1.8L86 18.2zm6.6-15.8L98 11h-6.8zm10.8 15.8h2l-.4-14.8 13 15 1-.3V.1h-2l.5 14.4L107.3 0h-1.7zm20.7 0l2.4-5.9h7.9l2.1 5.9h2.5l-7-18.1h-1.8L124 18.2zm6.6-15.8L136 11h-6.7z"
        />
      </svg>

      <div class="burger-text">
        <div class="zum">
          <a href="#" :class="{ textThemeDark: light, textThemeLight: !light}">Zum Product</a>
        </div>
        <input type="checkbox" name="bar" id="bar" />
        <label for="bar">
          <div
            class="container"
            :class="{ change: isActive, textThemeDark: light }"
            @click="isActive = !isActive"
          >
            <div class="bar1" :class="{ barDark: light, barLight: !light}"></div>
            <div class="bar2" :class="{ barDark: light, barLight: !light}"></div>
            <div class="bar3" :class="{ barDark: light, barLight: !light}"></div>
          </div>
        </label>
        <div class="overall">
          <div class="card">
            <h3>Day</h3>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque
              quia perspiciatis cum earum minus iste.
            </p>
          </div>
          <div class="card">
            <h3>Night</h3>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque
              quia perspiciatis cum earum minus iste.
            </p>
          </div>
        </div>
      </div>
    </nav>
    <!-- section Slides -->

    <section class="slides-cont" v-for="article in showSlides" :key="article.id">
      <div v-if="article.night">{{ nightTheme() }}</div>
      <div v-else>{{ lightTheme() }}</div>

      <div class="slide">
        <img :src="article.image" />
        <div class="controls">
          <a class="prev" @click="prevSlide()">
            <i class="fas fa-chevron-circle-left"></i>
          </a>
          <a class="next" @click="nextSlide()">
            <i class="fas fa-chevron-circle-right"></i>
          </a>
        </div>
      </div>
      <div class="text" :class="{ backLight: !light, background: light}">
        <div class="sub-text" :class="{ textThemeDark: light, textThemeLight: light }">
          <p id="slideId" :class="{ textThemeLight: light, textThemeDark: !light}">{{ article.id }}</p>
          <p
            id="slideId"
            :class="{ textThemeLight: light, textThemeDark: !light}"
          >{{ article.intro }}</p>
          <div class="btn">
            <a href="#" :class="{ btnDark: !light, btnLight: light}">Weiterlesen</a>
          </div>
        </div>
      </div>
    </section>

    <!-- section flowers -->

    <section class="flowers-dots">
      <div class="two-flowers">
        <img src="\herb_hopfen.png" alt="green-flower" />
        <img src="\herb_passionsblume.png" alt="pink-flower" />
      </div>
      <div class="dots">
        <div class="new-dots">
          <span v-if="slideNumber !== 0" class="dot" @click="currentSlide(0)"></span>
          <span v-if="slideNumber !== 1" class="dot1" @click="currentSlide(1)"></span>
          <span v-if="slideNumber !== 2" class="dot2" @click="currentSlide(2)"></span>
        </div>
        <div class="svgs">
          <div>
            <svg
              v-if="slideNumber === 0"
              class="svg0"
              xmlns="http://www.w3.org/2000/svg"
              width="15"
              height="16"
              fill="#d9a0c1"
              viewBox="1 0 9 14"
            >
              <path
                d="M2 5.5a.5.5 0 0 0-.5-.5h-1a.5.5 0 0 0 0 1h1a.5.5 0 0 0 .5-.5zM2.4 8a.6.6 0 0 0-.42.18l-.8.8A.6.6 0 0 0 1 9.4a.6.6 0 0 0 1.02.42l.8-.8A.6.6 0 0 0 2.4 8zm3.1-6a.5.5 0 0 0 .5-.5v-1a.5.5 0 0 0-1 0v1a.5.5 0 0 0 .5.5zm3.1 1a.6.6 0 0 0 .42-.18l.8-.8A.6.6 0 0 0 10 1.6a.6.6 0 0 0-.6-.6.6.6 0 0 0-.43.18l-.8.8A.6.6 0 0 0 8.6 3zm-6.62-.18a.6.6 0 0 0 .84-.84l-.8-.8A.6.6 0 0 0 1.6 1a.6.6 0 0 0-.42 1.02zM10.5 5h-1a.5.5 0 0 0 0 1h1a.5.5 0 0 0 0-1zM9.02 8.18a.6.6 0 0 0-.84.84l.8.8a.6.6 0 0 0 .42.18.6.6 0 0 0 .6-.6.6.6 0 0 0-.18-.43zM5.5 9a.5.5 0 0 0-.5.5v1a.5.5 0 0 0 1 0v-1a.5.5 0 0 0-.5-.5zm0-7A3.5 3.5 0 1 0 9 5.5 3.5 3.5 0 0 0 5.5 2zm0 6A2.5 2.5 0 1 1 8 5.5 2.5 2.5 0 0 1 5.5 8z"
              />
            </svg>
          </div>
          <div>
            <svg
              v-if="slideNumber === 1"
              class="svg1"
              xmlns="http://www.w3.org/2000/svg"
              width="15"
              height="16"
              fill="#d9a0c1"
              viewBox="1 0 9 14"
            >
              <path
                d="M2 5.5a.5.5 0 0 0-.5-.5h-1a.5.5 0 0 0 0 1h1a.5.5 0 0 0 .5-.5zM2.4 8a.6.6 0 0 0-.42.18l-.8.8A.6.6 0 0 0 1 9.4a.6.6 0 0 0 1.02.42l.8-.8A.6.6 0 0 0 2.4 8zm3.1-6a.5.5 0 0 0 .5-.5v-1a.5.5 0 0 0-1 0v1a.5.5 0 0 0 .5.5zm3.1 1a.6.6 0 0 0 .42-.18l.8-.8A.6.6 0 0 0 10 1.6a.6.6 0 0 0-.6-.6.6.6 0 0 0-.43.18l-.8.8A.6.6 0 0 0 8.6 3zm-6.62-.18a.6.6 0 0 0 .84-.84l-.8-.8A.6.6 0 0 0 1.6 1a.6.6 0 0 0-.42 1.02zM10.5 5h-1a.5.5 0 0 0 0 1h1a.5.5 0 0 0 0-1zM9.02 8.18a.6.6 0 0 0-.84.84l.8.8a.6.6 0 0 0 .42.18.6.6 0 0 0 .6-.6.6.6 0 0 0-.18-.43zM5.5 9a.5.5 0 0 0-.5.5v1a.5.5 0 0 0 1 0v-1a.5.5 0 0 0-.5-.5zm0-7A3.5 3.5 0 1 0 9 5.5 3.5 3.5 0 0 0 5.5 2zm0 6A2.5 2.5 0 1 1 8 5.5 2.5 2.5 0 0 1 5.5 8z"
              />
            </svg>
          </div>
          <div>
            <svg
              v-if="slideNumber === 2"
              class="svg2"
              xmlns="http://www.w3.org/2000/svg"
              width="15"
              height="16"
              fill="#d9a0c1"
              viewBox="0 0 9 15"
            >
              <path
                d="M9.5 2a.4.4 0 0 0 .3-.3.4.4 0 0 0-.1-.4A6.1 6.1 0 0 0 5.9 0 5.7 5.7 0 0 0 0 5.5 5.7 5.7 0 0 0 5.9 11a6.2 6.2 0 0 0 4-1.4.4.4 0 0 0 0-.4.4.4 0 0 0-.3-.3 3.6 3.6 0 0 1-3.3-3.5A3.5 3.5 0 0 1 9.5 2m-4 3.4a4.3 4.3 0 0 0 3.1 4 5.3 5.3 0 0 1-2.7.8 5 5 0 0 1-5-4.7 5 5 0 0 1 5-4.7 5.4 5.4 0 0 1 2.6.6 4.3 4.3 0 0 0-3 4"
              />
            </svg>
          </div>
        </div>
      </div>
      <div class="big-flower">
        <img src="\herb_baldrian.png" alt="flower-right" />
      </div>
    </section>

    <!-- -----------footer--------- -->
    <footer>
      <a :class="{textThemeDark: light}" href="#">ratiopharm</a>
      <a :class="{textThemeDark: light}" href="#">Kontakt & Impressum</a>
    </footer>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      articles: [
        {
          id: "fruehstuecksideen",
          title: "7.30 Lass es dir schmecken",
          intro:
            "Guten Morgen! Wie startest du am besten in einen Tag ohne Stress? Mit einem ausgewogenen Frühstück natürlich!",
          image: "blog/fruehstuecksideen.jpg",
          time: { hour: 7, minute: 30, second: 0 },
          night: false
        },
        {
          id: "uebungen",
          title: "15.30 Kurzurlaub für die Seele",
          intro:
            "Auch die beste Planung kann Stress und Nervosität nicht immer verhindern. Wenn es doch einmal passiert, stell dich dem Stress nicht. Viel besser, du weichst aus.",
          image: "blog/ebungen.jpg",
          time: { hour: 15, minute: 30, second: 0 },
          night: false
        },
        {
          id: "sanft-hinuebergleiten",
          title: "21.30 Entspann dich",
          intro:
            "Es wird Zeit, zur Ruhe zu kommen und sich ohne Stress auf die Nacht einzustimmen. Jetzt ist Entspannung pur angesagt: Wenn du Lust hast, lass dir zum Beispiel ein schönes warmes Bad ein.",
          image: "blog/sanft-hinuebergleiten.jpg",
          time: { hour: 21, minute: 30, second: 0 },
          night: true
        }
      ],
      isActive: false,
      slideNumber: 0,

      light: false
    };
  },
  methods: {
    nextSlide() {
      this.slideNumber++;
      if (this.slideNumber > 2) {
        this.slideNumber = 0;
      }
    },
    prevSlide() {
      this.slideNumber--;
      if (this.slideNumber < 0) {
        this.slideNumber = 2;
      }
    },
    currentSlide(number) {
      this.slideNumber = number;
    },
    nightTheme() {
      this.light = false;
    },
    lightTheme() {
      this.light = true;
    }
  },
  computed: {
    showSlides() {
      let arr = [];
      let entries = this.articles[this.slideNumber];
      arr.push(entries);
      return arr;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.backgroundTheme {
  background: var(--darkBackground);
}
.btnDark {
  color: var(--light);
  background-color: var(--dark);
}
.btnLight {
  color: var(--dark);
  background-color: var(--light);
}
.logoFillLight {
  fill: var(--light);
}
.textThemeDark {
  color: var(--dark);
}
.textThemeLight {
  color: var(--light);
}
.backLight {
  background: var(--light);
}
.barLight {
  background-color: var(--light);
}
.barDark {
  background-color: var(--dark);
}
.background {
  background: var(--background);
}
.textTransparent {
  background: var(--transparent);
}

:root {
  --darkBackground: radial-gradient(#415d9b, #0b2a4b, #030f1f);
  --background: radial-gradient(circle at right, #163353, #0c1c31 50%);
  --light: #ffffff;
  --dark: #062647;
  --transparent: transparent;
  --grey: rgb(136, 136, 136);
}
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
#app {
  display: grid;
  height: 100vh;
  width: 100%;
  grid-template-columns: 100% auto;
  grid-template-rows: 11% 60% 19% 10%;
  grid-template-areas: "navbar" "main-one" "main-two" "footer";
}
label {
  width: 10px;
  height: 10px;
}
.main-nav {
  grid-area: navbar;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
.burger-text {
  display: flex;
  flex-direction: row;
  align-self: center;
  margin-top: 9px;
}
.container {
  width: 25px;
  cursor: pointer;
}
.logo {
  align-self: center;
  width: 110px;
}
.zum {
  margin-right: 40px;
  width: 30px;
}
.zum a {
  font-size: 10px;
  font-weight: bold;
  text-decoration: none;
}

/* -------------Main Burger Menu------------------ */

.bar1,
.bar2,
.bar3 {
  width: 23px;
  height: 2.8px;
  margin: 5px 0;
  transition: 0.4s;
  border-radius: 10px;
  -webkit-border-radius: 4px;
  -moz-border-radius: 4px;
  -ms-border-radius: 4px;
  -o-border-radius: 4px;
}

.change .bar1 {
  -webkit-transform: rotate(-45deg) translate(-7.5px, 6px);
  transform: rotate(-45deg) translate(-7.5px, 6px);
}

.change .bar2 {
  opacity: 0;
}

.change .bar3 {
  -webkit-transform: rotate(45deg) translate(-5px, -5px);
  transform: rotate(45deg) translate(-5px, -5px);
}

/* ---------other burger functions----------- */

#bar {
  display: none;
}

.overall {
  display: none;
  position: absolute;
  top: 11%;
  bottom: 0;
  width: 100%;
  right: 0;
  animation: anim 0.5s reverse;
}

@keyframes anim {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

#bar:checked ~ .overall {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  background: rgba(1, 20, 63, 0.9);
  opacity: 0.3;
  z-index: 3;
  animation: anim 0.5s forwards;
  -webkit-animation: anim 0.5s forwards;
}

.card {
  display: flex;
  flex-direction: column;
  align-self: center;
  align-items: center;
  max-width: 250px;
  text-align: center;
  color: white;
  font-weight: 20px;
  line-height: 30px;
  letter-spacing: 2px;
}

.card h3 {
  color: rgb(189, 52, 189);
}

/* ----------Slides----------- */
.slides-cont {
  grid-area: main-one;
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 100%;
  grid-template-areas: "text1 showcase";
}
.slide {
  grid-area: showcase;
  position: relative;
}
.slide img {
  width: 960px;
  height: 100%;
  object-fit: cover;
}

.text {
  grid-area: text1;

  display: flex;
  justify-content: center;
  align-items: center;
  max-height: 100%;
}

.sub-text {
  display: flex;
  flex-direction: column;
  align-items: left;
  font-size: 10px;
  width: 60%;
  min-width: 250px;
  line-height: 18px;
}
.sub-text p {
  margin: 5px;
  /* transform-origin: center center; */
  transform: scale(1);
  transition: transform 1.5s;
}
.sub-text p:nth-child(1) {
  font-size: 25px;
  line-height: 30px;
  font-weight: bold;
}
.sub-text p:nth-child(2) {
  font-size: 12px;
  font-weight: bold;
}
.btn {
  margin-top: 20px;
}
.btn a {
  padding: 0.6rem 1.3rem;
  text-decoration: none;
}
.controls {
  position: absolute;
  bottom: 40px;
  right: 35px;
  width: 62px;
}
.prev,
.next {
  cursor: pointer;
  color: white;
  font-size: 24px;
  transition: 0.6s ease;
}
.next {
  position: absolute;
  right: 0;
}

.prev:hover,
.next:hover {
  color: rgba(104, 104, 104, 0.8);
}

/* ----------------------flowers--------------------- */
.flowers-dots {
  grid-area: main-two;
  height: 160px;
  margin-top: -23px;
  z-index: 1;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.two-flowers {
  margin-top: -10px;
  z-index: 1;
}

.two-flowers img {
  z-index: 1;
  margin-left: 50px;
  width: 130px;
}
.two-flowers img:nth-child(2) {
  margin-left: -40px;
}

.big-flower {
  text-align: right;
  overflow: hidden;
}
.big-flower img {
  margin-right: -80px;
  margin-left: 100px;
  width: 200px;
  z-index: 1;
}

/* ----------dots----------- */
.path {
  width: 30px;
}
.dots {
  margin-top: 60px;
  width: 120px;
  display: flex;
  flex-direction: column;
}
.new-dots {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-areas: "dot0 dot1 dot2";
  width: 100%;
  z-index: 1;
  justify-items: center;
}

.svgs {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-areas: "svg0 svg1 svg2";
  width: 100%;
  justify-items: center;
  margin-top: -13px;
}
.svg {
  grid-area: svg0;
}
.svg1 {
  grid-area: svg1;
}

.svg2 {
  grid-area: svg2;
}

.dot {
  grid-area: dot0;
  cursor: pointer;
  width: 12px;
  height: 12px;
  background-color: var(--grey);
  border-radius: 50%;
  transition: background-color 0.6s ease;
}
.dot1 {
  display: flex;
  cursor: pointer;
  width: 12px;
  height: 12px;
  background-color: var(--grey);
  border-radius: 50%;
  transition: background-color 0.6s ease;
  grid-area: dot1;
}
.dot2 {
  display: flex;
  grid-area: dot2;
  cursor: pointer;
  width: 12px;
  height: 12px;
  background-color: var(--grey);
  border-radius: 50%;
  transition: background-color 0.6s ease;
}

.dot:hover {
  background-color: #717171;
}

/* Fading animation */

.fade {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.5s;
  animation-name: fade;
  animation-duration: 1.5s;
}

@-webkit-keyframes fade {
  from {
    opacity: 0.4;
  }
  to {
    opacity: 1;
  }
}

@keyframes fade {
  from {
    opacity: 0.4;
  }
  to {
    opacity: 1;
  }
}

/* -------------footer------------- */

footer {
  grid-area: footer;
  height: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  background: var(--transparent);
}

footer a {
  color: var(--light);
  text-decoration: none;
  align-self: center;
}

@media only screen and (max-width: 1450px) {
  .slide img {
    width: 900px;
  }
}

@media only screen and (max-width: 1100px) {
  .slide img {
    width: 600px;
  }
}

@media only screen and (max-width: 900px) {
  .slide img {
    width: 500px;
  }
  .two-flowers img {
    margin-left: 10px;
  }
  .big-flower img {
    width: 180px;
    margin-left: 50px;
  }
}
@media only screen and (max-width: 867px) {
  .slide img {
    width: 500px;
  }
  .sub-text p {
    width: 40%;
    min-width: 160px;
  }
  .two-flowers img {
    width: 120px;
    margin-top: 20px;
  }
}
@media only screen and (max-width: 767px) {
  .slide img {
    width: 400px;
  }
  .sub-text p {
    width: 40%;
    min-width: 250px;
  }
  .two-flowers img {
    width: 110px;
  }
}

@media screen and (max-width: 667px) {
  #app {
    grid-template-rows: 10% 73% 8% 9%;
    grid-template-areas: "navbar" "main-one" "main-two" "footer";
  }
  .burger-text {
    align-self: center;
    margin-right: 20px;
  }
  .slides-cont {
    grid-template-columns: 1fr;
    grid-template-rows: 50% 50%;
    grid-template-areas: "showcase" "text1";
  }
  .text {
    justify-content: start;
  }
  .sub-text {
    margin-left: 20px;
    width: 80%;
  }
  .sub-text p {
    width: 100%;
  }
  .slide img {
    width: 100%;
    height: 100%;
  }
  .container {
    margin-top: -5px;
  }
  .two-flowers {
    display: none;
  }
  .big-flower {
    display: none;
  }
  .flowers-dots {
    margin: 0 auto;
    height: 100%;
  }
  .btn {
    margin-top: 10px;
  }

  .controls {
    bottom: 15px;
    right: 25px;
  }
  .zum {
    font-size: 12px;
    margin-right: 30px;
    width: 30px;
  }
  #bar:checked ~ .overall {
    opacity: 0.2;
    top: 85px;
    height: 90.9%;
    animation: anim 0.5s forwards;
    -webkit-animation: anim 0.5s forwards;
  }
  .dots {
    margin-top: 20px;
  }
  .overall {
    margin-top: -28px;
  }
}
</style>
