<!-- <template>
  <div>
    <HeaderDesc/>
    <HeaderMob />
    <ProductBlock />
    <SizeBlock />
    <ColorsBlock />
    <AccordionMenu />
    <SimilarBlock />
  </div>
</template>

<script>
import HeaderDesc from "../components/headerDesc.vue";
import HeaderMob from "../components/headerMob.vue";
import ColorsBlock from "../components/colorsBlock.vue";
import AccordionMenu from "../components/accordionMenu.vue";
import SimilarBlock from "../components/similarBlock.vue";
import SizeBlock from "../components/sizeBlock.vue";
import ProductBlock from "../components/productBlock.vue";

export default {};
</script>

<style>



</style> -->
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
  padding: 42px 40px;

  @media (min-width: 1020px) {
    flex-direction: row;
    justify-content: space-between;
    padding: 0 72px;
  }

  @media (min-width: 1200px) {
    gap: 60px;
  }
}
</style>
