<template>
  <div class="welcom">
    <div class="grid-right">
      <div class="y"><span>A</span></div>
      <div class="done" @click="blackclick()" v-on:mouseleave="mouseoutblack()">
        <h2>Professionals</h2>
        <h1>5.2m</h1>
        <div class="push-black"></div>
        <div :class="classtwo">
          For <br />
          Rating
        </div>
      </div>
    </div>
    <div class="grid-left">
      <div class="done-two" @click="showme()" v-on:mouseleave="mouseout()">
        <h2>project done</h2>
        <h1>24k</h1>
        <div class="push"></div>
        <div :class="classone">
          For <br />
          Project
        </div>
      </div>
      <div
        class="done-three"
        @click="HasalaClick()"
        v-on:mouseleave="HasalMouseout()"
      >
        <h2>Your earnings</h2>
        <h1>2.7k dh</h1>
        <div class="hasala-p">
          For <br />
          Earnings
        </div>
        <img src="@/assets/Hasala.png" class="hasala" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LanDetails",
  data() {
    return {
      displayStyleone: "inline",
      displayStyletwo: "inline",
      displayStylethree: "inline",
      classone: "shap",
      classtwo: "shaptwo",
    };
  },
  methods: {
    showme() {
      this.classone = "with-anim";
      setTimeout(() => (this.displayStyleone = "none"), 500);
    },
    blackclick() {
      this.classtwo = "with-anim";
      setTimeout(() => (this.displayStyletwo = "none"), 500);
    },
    HasalaClick() {
      setTimeout(() => (this.displayStylethree = "none"), 500);
    },
    HasalMouseout() {
      setTimeout(() => (this.displayStylethree = "inline"), 500);
    },
    mouseout() {
      this.classone = "shap";
      setTimeout(() => (this.displayStyleone = "inline"), 200);
    },
    mouseoutblack() {
      this.classtwo = "shaptwo";
      setTimeout(() => (this.displayStyletwo = "inline"), 200);
    },
  },
};
</script>

<style lang="scss" scoped>
.welcom {
  direction: rtl;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-areas: "left left right right";
  align-items: center;
  font-family: outfit;
  .grid-left {
    grid-area: left;
    grid-column-start: 1;
    .done-two {
      width: 250px;
      height: 250px;
      background-color: #3f70cb;
      position: relative;
      overflow: hidden;
      cursor: pointer;
      h1 {
        position: absolute;
        bottom: 15px;
        right: 20px;
        font-size: 45px;
        color: #d7d7d7;
        font-weight: 300;
        margin: 0;
      }
      h2 {
        position: absolute;
        top: 15px;
        right: 20px;
        color: #d7d7d7;
        font-size: 19px;
        font-weight: 300;
        margin: 0;
      }
      .push {
        width: 100%;
        height: 100%;
        background-color: #3f70cb;
        position: absolute;
        z-index: 1;
        display: v-bind(displayStyleone);
      }
      .shap {
        background-color: #e9e9e9;
        width: 100px;
        height: 100px;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%) rotateZ(0deg);
        z-index: 2;
        transition: 0.3s ease;
        display: v-bind(displayStyleone);
        animation: shapingopo 0.7s;
        text-align: end;
        padding: 15px;
        font-size: 19px;
        color: #2558b5;
      }
      .shap:hover {
        width: 105px;
        height: 105px;
      }
      .with-anim {
        animation: shaping 0.7s;
        background-color: #e9e9e9;
        width: 100px;
        height: 100px;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%) rotateZ(0deg);
        z-index: 2;
        transition: 1s ease;
        display: v-bind(displayStyleone);
        text-align: end;
        padding: 15px;
        font-size: 19px;
        color: #2558b5;
      }
    }
    .done-three {
      width: 250px;
      height: 250px;
      background-color: black;
      margin-top: 50px;
      cursor: pointer;
      position: relative;
      h1 {
        position: absolute;
        bottom: 15px;
        right: 20px;
        font-size: 45px;
        color: #d7d7d7;
        font-weight: 300;
        margin: 0;
      }
      h2 {
        position: absolute;
        top: 15px;
        right: 20px;
        color: #d7d7d7;
        font-size: 19px;
        font-weight: 300;
        margin: 0;
      }
      img {
        width: 100%;
        height: 100%;
        display: v-bind(displayStylethree);
        z-index: 1;
        transition: 1s ease;
        position: absolute;
      }
      .hasala-p {
        position: absolute;
        top: 15px;
        left: 20px;
        font-size: 19px;
        z-index: 2;
        color: #e9e9e9;
        font-weight: 300;
        position: absolute;
        display: v-bind(displayStylethree);
        text-align: end;
      }
    }
  }
  .grid-right {
    grid-area: right;
    .y {
      width: 250px;
      height: 250px;
      line-height: 200px;
      background-image: url("data:image/svg+xml,%3csvg width='100%25' height='100%25' xmlns='http://www.w3.org/2000/svg'%3e%3crect width='100%25' height='100%25' fill='none' stroke='black' stroke-width='3' stroke-dasharray='23 14' stroke-dashoffset='26' stroke-linecap='butt'/%3e%3c/svg%3e");
      text-align: center;
      span {
        display: inline-block;
        vertical-align: middle;
        line-height: normal;
        font-size: 185px;
      }
    }
    .done {
      width: 250px;
      height: 250px;
      background-color: black;
      margin-top: 50px;
      position: relative;
      overflow: hidden;
      cursor: pointer;

      .push-black {
        width: 100%;
        height: 100%;
        background-color: black;
        position: absolute;
        z-index: 1;
        display: v-bind(displayStyletwo);
      }
      .shaptwo {
        background-color: #e9e9e9;
        width: 100px;
        height: 100px;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%) rotateZ(0deg);
        z-index: 2;
        transition: 0.3s ease;
        display: v-bind(displayStyletwo);
        animation: shapingopo 0.7s;
        text-align: end;
        padding: 15px;
        font-size: 19px;
      }
      .shaptwo:hover {
        width: 105px;
        height: 105px;
      }
      .with-anim {
        animation: shaping 0.7s;
        background-color: #e9e9e9;
        width: 100px;
        height: 100px;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%) rotateZ(0deg);
        z-index: 2;
        transition: 1s ease;
        display: v-bind(displayStyletwo);
        text-align: end;
        padding: 15px;
        font-size: 19px;
      }
      h1 {
        position: absolute;
        bottom: 15px;
        left: 20px;
        font-size: 45px;
        color: #d7d7d7;
        font-weight: 300;
        margin: 0;
      }
      h2 {
        position: absolute;
        top: 15px;
        left: 19px;
        color: #d7d7d7;
        font-size: 21px;
        font-weight: 300;
        margin: 0;
      }
    }
  }
}
@keyframes shaping {
  0% {
    width: 100px;
    height: 100px;
    opacity: 100%;
    transform: translate(-50%, -50%) rotateZ(0deg);
    font-size: 19px;
    padding: 15px;
  }
  50% {
    opacity: 100%;
  }
  100% {
    width: 250px;
    height: 250px;
    opacity: 0%;
    transform: translate(-50%, -50%) rotateZ(180deg);
    font-size: 30px;
    padding: 20px;
  }
}
@keyframes shapingopo {
  from {
    width: 250px;
    height: 250px;
    opacity: 0%;
    transform: translate(-50%, -50%) rotateZ(180deg);
    font-size: 30px;
    padding: 20px;
  }
  50% {
    opacity: 100%;
  }
  to {
    width: 100px;
    height: 100px;
    opacity: 100%;
    transform: translate(-50%, -50%) rotateZ(0deg);
    font-size: 19px;
    padding: 15px;
  }
}

@media (max-width: 500px) {
  .welcom {
    direction: ltr;
    display: block;
    align-items: center;
    font-family: outfit;
    .grid-right {
      .done {
        width: 100%;
        height: 200px;
        margin: 30px 0;
        .shaptwo {
          text-align: start;
        }
      }
      .y {
        width: 150px;
        height: 150px;
        span {
          font-size: 110px;
          vertical-align: initial;
        }
      }
    }
    .grid-left {
      .done-two {
        width: 100%;
        height: 200px;
        margin: 30px 0;
        .shap {
          text-align: start;
        }
      }
      .done-three {
        width: 100%;
        height: 200px;
        margin: 30px 0;
        background-color: black;
        img {
          width: 200px;
          height: 199px;
          position: absolute;
          right: 0;
        }
        .hasala-p {
          text-align: start;
        }
      }
    }
  }
}
</style>
