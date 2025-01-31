<template lang="html">
  <div class="home-container">
    <div class="home-cards">
      <CardBlock />
      <SiteSpeed />
    </div>
    <div class="home-cards">
      <UserBarCharts />
    </div>
  </div>
</template>

<script setup>
import CardBlock from "@/components/cards/CardBlock.vue";
import SiteSpeed from "@/components/cards/SiteSpeed.vue";
import UserBarCharts from "@/components/charts/UserBarCharts.vue";
</script>

<style scoped lang="scss">
.home {
  &-container {
    max-width: 100%;
    width: 100%;
    display: flex;
    flex-direction: column;
    box-sizing: border-box;
    padding: 2rem;
    gap: 2rem;
    overflow-y: auto;
  }

  &-cards {
    display: flex;
    gap: 20px;
    width: 100%;

    @media(max-width: 1280px) {
      flex-direction: column;
    }

    &>div {
      max-width: 100%;
      width: 100%;
      height: 100%;
    }

    .graph {
      width: calc(50% - 10px);

      @media (max-width: 1280px) {
        width: 100%;
      }
    }
  }
}

@media (max-width: 1280px) {
  .home-cards {}
}

@media (max-width: 1024px) {
  .home {
    &-cards {
      flex-direction: column;
    }
  }
}
</style>
