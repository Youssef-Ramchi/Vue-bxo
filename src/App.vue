<template>
  <nav>
    <div class="blur"></div>
    <h2>BXO</h2>
    <ul>
      <li class="mar">
        <a><router-link to="/">Home</router-link></a>
      </li>
      <li>
        <a><router-link to="/about">About</router-link></a>
      </li>
      <li>
        <a><router-link to="/profile">Profile</router-link></a>
      </li>
      <li>
        <a><router-link to="/profile">Reviews</router-link></a>
      </li>
      <li class="mobile-contact">
        <a><router-link to="/profile">Contact Us</router-link></a>
      </li>
    </ul>
    <h3>Contact Us</h3>
    <img :src="src" @click="moveBar()" class="menu" />
  </nav>
  <router-view />
</template>

<script>
export default {
  data() {
    return {
      iright: "-210px",
      display: "none",
      src: require("@/assets/menu.svg"),
      opacity: "0",
      json: '"@vue/cli-plugin-eslint": "~5.0.0",',
    };
  },
  methods: {
    moveBar() {
      if (this.src === require("@/assets/menu.svg")) {
        this.display = "block";
        setTimeout(
          () => (
            (this.iright = "0px"),
            (this.src = require("@/assets/back.svg")),
            (this.opacity = "15%")
          ),
          10
        );
      } else {
        (this.iright = "-210px"),
          (this.src = require("@/assets/menu.svg")),
          (this.opacity = "0%"),
          setTimeout(() => (this.display = "none"), 500);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  display: grid;
  grid-template-columns: repeat(16, 1fr);
  grid-template-areas: "logo logo logo logo lists lists lists lists lists lists lists lists lists lists con con";
  align-items: center;
  padding: 10px 50px;
  font-family: Arial;
  font-weight: 100;
  img {
    display: none;
  }
  .blur {
    display: none;
  }
  h2 {
    grid-area: logo;
    grid-column-start: 1;
    font-size: 25px;
  }
  ul {
    grid-area: lists;
    grid-column-end: 14;
    text-align: right;
    font-size: 15px;
    transition: 0.5s ease;
    .mobile-contact {
      display: none;
    }
    li {
      display: inline;
      padding-left: 40px;
      a {
        font-weight: bold;
        text-decoration: none;
        color: #606060;

        &.router-link-exact-active {
          color: black;
        }
      }
    }
  }
  h3 {
    grid-area: con;
    width: 100%;
    background-color: black;
    padding: 15px 0;
    color: white;
    text-align: center;
    font-size: 15px;
  }
}
@media (max-width: 500px) {
  nav {
    display: grid;
    grid-template-columns: repeat(15, 1fr);
    grid-template-areas: "logo logo logo logo logo logo logo logo logo logo logo logo logo logo menu";
    padding: 0 10px;
    .blur {
      display: block;
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: black;
      opacity: v-bind(opacity);
      z-index: 1;
    }
    img {
      display: block;
      grid-area: menu;
      width: 100%;
      z-index: 2;
    }
    ul {
      width: 40%;
      background-color: black;
      padding: 20px;
      display: v-bind(display);
      position: absolute;
      top: -15px;
      right: v-bind(iright);
      text-align: center;
      z-index: 2;
      transition: 0.5s ease;
      .mar {
        margin-top: 73px;
      }
      .mobile-contact {
        display: block;
      }
      li {
        display: block;
        padding-left: 0px;
        margin-bottom: 25px;
        a {
          font-weight: bold;
          text-decoration: none;
          color: #8f8f8f;
          font-size: 17px;
          font-weight: 600;

          &.router-link-exact-active {
            color: white;
            font-weight: 600;
          }
        }
      }
    }
    h3 {
      display: none;
    }
  }
}
</style>
