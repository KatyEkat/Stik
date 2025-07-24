<template>
  <div class="product_details-right">
    <div class="product_info-block-desc">
      <div class="product_info">
        <p class="product_info-title">ЖАКЕТ УДЛИНЁННЫЙ, БЕЛЫЙ</p>
        <p class="product_info-price">8900 RUB</p>
      </div>
    </div>

    <SizeBlock />
    <ColorsBlock />

    <div class="buttons_block-desc">
      <button class="product_button">добавить в корзину</button>
      <button class="save_button">
        <svg
          width="44.000000"
          height="44.000000"
          viewBox="0 0 44 44"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
        >
          <defs />
          <rect
            id="Favorite / Big / Stroke"
            rx="0.000000"
            width="23.000000"
            height="23.000000"
            transform="translate(10.500000 10.500000)"
            fill="#FFFFFF"
            fill-opacity="0"
          />
          <path
            id="Vector"
            d="M15.5 14L28.5 14L28.5 31.48L22.01 27.11L15.5 31.48L15.5 14ZM16.5 15L16.5 29.51L22.01 25.88L27.5 29.51L27.5 15L16.5 15Z"
            fill="#000000"
            fill-opacity="1.000000"
            fill-rule="evenodd"
          />
          <rect
            id="Secondary / Icon / Active"
            rx="0.000000"
            width="43.000000"
            height="43.000000"
            transform="translate(0.500000 0.500000)"
            stroke="#000000"
            stroke-opacity="1.000000"
            stroke-width="1.000000"
          />
        </svg>
      </button>
    </div>

    <AccordionMenu />
  </div>
</template>

<script>
import SizeBlock from "./sizeBlock.vue";
import ColorsBlock from "./colorsBlock.vue";
import AccordionMenu from "./accordionMenu.vue";

export default {
  components: {
    SizeBlock,
    ColorsBlock,
    AccordionMenu,
  },
};
</script>

<style scoped lang="scss">
.product_details-right {
  display: flex;
  flex-direction: column;
  max-width: 400px;
  padding-top: 32px;
  padding: 0;

  .product_info-block-desc {
    display: none;
  }

  .buttons_block-desc {
    display: none;
  }
}

@media (min-width: 712px) {
  /* .buttons_block-desc{
    display: flex;
} */



  .product_details-right {
    padding: 0 40px;
  }

  .size_block {
    padding: unset;
    margin-top: 31px;
  }

  .color_picker {
    padding: unset;
    margin-top: 34px;
  }

  .product_desctop-right {
    padding: 32px 0 0 40px;
  }
}

@media (min-width: 1020px) {
    .product_details-right .buttons_block-desc {
    display: flex;
    gap: 10px;
    margin-top: 36px;
  }

  .product_button {
    color: rgb(255, 255, 255);
    font-family: "Helvetica";
    font-size: 11px;
    font-weight: 400;
    line-height: 15px;
    letter-spacing: 0%;
    text-align: center;
    text-transform: uppercase;
    padding: 15px 25px 15px 25px;
    height: 44px;
    background: rgb(0, 0, 0);
    cursor: pointer;
  }

  .product_button:hover {
    background: rgb(65, 65, 65);
    transition: 0.2s;
  }

  .product_button:active {
    background: rgb(97, 97, 97);
  }

  .save_button {
    background: unset;
    border: unset;
    cursor: pointer;
  }

  .product_info-block-desc {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding: unset;
    max-width: 360px;
  }
  .product_info {
    color: rgb(51, 51, 51);
    font-family: Helvetica;

    font-weight: 400;
    line-height: 16px;
    letter-spacing: 0%;
    text-align: left;
    text-transform: uppercase;

    &-title {
      text-transform: uppercase;
      color: #333;
      font-size: 12px;
    }

    &-price {
      font-size: 12px;
      margin-top: 5px;
    }
  }

  .color_picker {
    width: fit-content;
    padding: unset;
    margin-top: 36px;
  }
}

@media (min-width: 1200px) {
  .product_button {
    width: 306px;
  }
}
</style>
