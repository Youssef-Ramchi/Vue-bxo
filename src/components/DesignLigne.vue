<template>
  <div class="hello">
    <img src="@/assets/design.png" />
  </div>
</template>

<script>
export default {
  name: "DesignLigne",
  props: {
    msg: String,
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.hello {
  margin: 0 0 40px 130px;
  img {
    width: 250px;
    opacity: 85%;
  }
}
@media (max-width: 500px) {
  .hello {
    display: none;
  }
}
</style>
