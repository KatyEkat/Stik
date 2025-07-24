<template>
  <div class="similar__block">
    <h2 class="similar__block-header">Похожие товары</h2>

    <div class="similar__block-cards">
      <div
        class="similar__block-card"
        v-for="(item, index) in similarProducts"
        :key="index"
      >
        <div class="similar__block-card-img">
          <img :src="item.img" :alt="item.name" />
        </div>

        <div class="similar__block-card-text-content">
          <p class="similar__block-card-text-product-name">
            {{ item.name }}
          </p>

          <div
            class="similar__block-card-text-price-block"
            v-if="item.oldPrice"
          >
            <p class="similar__block-card-text-price">{{ item.price }}</p>
            <p class="similar__block-card-text-price-old">
              {{ item.oldPrice }}
            </p>
          </div>

          <p class="similar__block-card-text-price" v-else>
            {{ item.price }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      similarProducts: [
        {
          name: "платье с v-образным вырезом, белый",
          img: "/img/lady4.png",

          price: "14 900 RUB",
          oldPrice: "8 000 RUB",
        },
        {
          name: "жакет двубортный, серо-голубой",
          img: "/img/lady3.png",

          price: "8 900 RUB",
        },
        {
          name: "платье макси с ярусами, белый",
          img: "/img/lady2.png",

          price: "10 500 RUB",
        },
        {
          name: "комбинезон со стойкой, чёрный",
          img: "/img/lady.png",
          price: "9 500 RUB",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.similar__block {
  display: flex;
  flex-direction: column;
  gap: 23px;
  padding: 4px 15px 0 15px;

  &-header {
    color: rgb(51, 51, 51);
    font-family: "Helvetica";
    font-size: 12px;
    font-weight: 400;
    line-height: 16px;
    text-align: left;
    text-transform: uppercase;
  }

  &-cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 32px 8px;
  }

  &-card {
    display: flex;
    flex-direction: column;
    gap: 15px;

    &-img > img {
      width: 100%;
      height: auto;
      object-fit: cover;
    }

    &-text-price-block {
      display: flex;
      flex-direction: row;
      gap: 10px;
    }

    &-text-price {
      color: rgb(51, 51, 51);
      font-family: "Helvetica";
      font-size: 10px;
      font-weight: 400;
      line-height: 14px;
      text-align: left;
      text-transform: uppercase;

      &-old {
        color: rgb(130, 130, 130);
        font-family: "Helvetica";
        font-size: 10px;
        font-weight: 400;
        line-height: 14px;
        text-align: left;
        text-decoration-line: line-through;
        text-transform: uppercase;
      }
    }

    &-text-product-name {
      color: rgb(51, 51, 51);
      font-family: "Helvetica";
      font-size: 10px;
      font-weight: 400;
      line-height: 14px;
      text-align: left;
    }

    &-text-content {
      display: flex;
      flex-direction: column;
      gap: 5px;
      padding: 0 15px 7px 15px;
    }
  }
}

@media (min-width: 712px) {
  .similar__block {
    padding: 42px 40px;
  }
}
</style>
