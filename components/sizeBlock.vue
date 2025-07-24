<template>
  <div class="size_block">
    <p class="label">Размеры</p>

    <div class="size_block-list">
      <div
        v-for="(size, index) in sizes"
        :key="index"
        class="size_block-column"
      >
        <div
          class="size_block-box"
          :class="{
            disabled: size.disabled,
            active: selectedSize === size.label && !size.disabled,
          }"
          @click="selectSize(size)"
        >
          <span class="size_block-label">{{ size.label }}</span>
        </div>

        <span
          class="size_block-note"
          v-if="size.note"
          :class="{ disabled: size.disabled }"
        >
          {{ size.note }}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedSize: "XS",
      sizes: [
        { label: "XS", note: "мало", disabled: false },
        { label: "S", note: null, disabled: false },
        { label: "M", note: "подписка", disabled: true },
      ],
    };
  },
  methods: {
    selectSize(size) {
      if (!size.disabled) {
        this.selectedSize = size.label;
      }
    },
  },
};
</script>

<style scoped lang="scss">
.size_block {
  display: flex;
  flex-direction: column;
  gap: 9px;
  padding: 31px 16px 0 16px;

  &-label {
    color: rgb(79, 79, 79);
    font-family: "Helvetica";
    font-size: 10px;
    font-weight: 400;
    line-height: 14px;
    text-align: left;
  }

  &-list {
    display: flex;
    gap: 14px;
  }

  &-column {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
  }

  &-box {
    border: 1px solid rgb(51, 51, 51);
    transition: border-color 0.2s;
    padding: 9px 29px;
    width: 65px;
    height: 31px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;

    &-label {
      color: rgb(51, 51, 51);
      font-family: "Helvetica";
      font-size: 10px;
      font-weight: 400;
      line-height: 14px;
      text-transform: uppercase;
    }

    &.active {
      border: 2px solid #000;
    }

    &.disabled {
      cursor: default;
      opacity: 0.4;
      border: 2px solid #ccc;
    }
  }

  &-note {
    font-size: 10px;
    font-family: "Helvetica";
    color: #828282;

    &.disabled {
      color: #bdbdbd;
    }
  }

  @media (min-width: 712px) {
    /* .size_block {
      padding: unset;
      margin-top: 31px;
    } */
    .product_details-right {
      /* padding: 32px 0 0 40px; */
      padding: 31px 0 0 40px;
    }
  }

  @media (min-width: 1020px) {
    .size_block {
      padding: 0;
    }
  }
}
</style>
