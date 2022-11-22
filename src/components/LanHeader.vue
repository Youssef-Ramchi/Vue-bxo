<template>
  <div class="test">
    <h1>
      We are profissional
      <span
        ><span>{{ name }}</span> pro</span
      >
    </h1>
    <div class="get-start">
      <button>More...</button>
      <p>
        We are your friend that help you build business, for privacy you have to
        flip the card!
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "LanHeader",
  data() {
    return {
      name: "We are",
    };
  },
};
</script>

<style lang="scss" scoped>
.test {
  font-family: outfit;
  h1 {
    font-family: outfit;
    font-size: 80px;
    font-weight: 400;
    width: 90%;
    letter-spacing: 3px;
    line-height: 1;
    margin: 20px 0 30px;
    color: #1a1a1a;
    span {
      font-size: 60px;
      font-weight: 500;
      span {
        font-weight: 100;
        color: black;
      }
    }
  }
  .get-start {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-areas: "start para para para";
    align-items: center;
    button {
      grid-area: start;
      grid-column-start: 1;
      width: 100%;
      background-color: black;
      padding: 15px 0;
      color: white;
      text-align: center;
      font-size: 17px;
      font-weight: 300;
      letter-spacing: 0.5px;
      font-family: outfit;
      cursor: pointer;
    }
    p {
      grid-area: para;
      width: 58%;
      margin-left: 35px;
      font-size: 16px;
      color: #343434;
    }
  }
}

@media (max-width: 500px) {
  .test {
    font-family: outfit;
    margin: 70px 0 45px;
    h1 {
      font-family: outfit;
      font-size: 40px;
      font-weight: 400;
      width: 90%;
      letter-spacing: 3px;
      line-height: 1;
      margin: 20px 0 20px;
      color: #1a1a1a;
      span {
        font-size: 30px;
        font-weight: 500;
        span {
          font-weight: 100;
          color: black;
        }
      }
    }
    .get-start {
      display: grid;
      grid-template-columns: repeat(6, 1fr);
      grid-template-areas: "start start para para para para";
      align-items: center;
      button {
        grid-area: start;
        grid-column-start: 1;
        width: 100%;
        background-color: black;
        padding: 15px 0;
        color: white;
        text-align: center;
        font-size: 16px;
        font-weight: 300;
        letter-spacing: 0.5px;
        font-family: outfit;
        cursor: pointer;
        border: none;
      }
      p {
        grid-area: para;
        width: calc(100% - 15px);
        margin-left: 20px;
        font-size: 16px;
        color: #343434;
      }
    }
  }
}
</style>
