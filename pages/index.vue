<template>
  <div class="product-page">
    <HeaderDesc />
    <HeaderMob />

    <div class="product_main-layout">
      <ProductBlock />
      <ProductDesctop />
    </div>

    <SimilarBlock />
  </div>
</template>

<script>
import HeaderDesc from "../components/headerDesc.vue";
import HeaderMob from "../components/headerMob.vue";
import ProductBlock from "../components/productBlock.vue";
import ProductDesctop from "../components/productDesctop.vue";
import SimilarBlock from "../components/similarBlock.vue";

export default {
  components: {
    HeaderDesc,
    HeaderMob,
    ProductBlock,
    ProductDesctop,
    SimilarBlock,
  },
};
</script>

<style scoped lang="scss">
.product_main-layout {
  display: flex;
  flex-direction: column;

  @media (min-width: 1020px) {
    flex-direction: row;
    justify-content: center;

    .content-desctop {
      padding: unset;
    }
  }

  @media (min-width: 1200px) {
    gap: 60px;

    .product_main-layout {
      display: flex;
      justify-content: center;
      padding: unset;
    }
  }
}
</style>
