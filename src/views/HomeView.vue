<template>
  <div class="home">
    <div class="grid-two">
      <div class="grid-left">
        <design-ligne />
        <lan-header />
      </div>
      <div class="grid-right">
        <lan-details />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import DesignLigne from "@/components/DesignLigne.vue";
import LanHeader from "@/components/LanHeader.vue";
import LanDetails from "@/components/LanDetails.vue";

export default {
  name: "HomeView",
  components: {
    DesignLigne,
    LanHeader,
    LanDetails,
  },
};
</script>

<style lang="scss" scoped>
.home {
  .grid-two {
    padding: 0 50px;
    margin: 0 0 50px;
    display: grid;
    grid-template-columns: repeat(8, 1fr);
    grid-template-areas: "left left left left right right right right";
    align-items: end;
    .grid-left {
      grid-area: left;
      grid-column-start: 1;
    }
    .grid-right {
      grid-area: right;
    }
  }
}

@media (max-width: 500px) {
  .home {
    .grid-two {
      display: block;
      padding: 15px;
      margin: 0;
    }
  }
}
</style>
