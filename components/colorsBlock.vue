<template>
  <div class="color_picker">
    <p class="color_picker-label">Цвет: {{ selectedColor.name }}</p>

    <div class="color_picker-options">
      <div
        v-for="(color, index) in colors"
        :key="index"
        class="color_picker-square"
        :class="{
          active: selectedColor.value === color.value,
          white: color.value === '#ffffff',
        }"
        :style="{ backgroundColor: color.value }"
        @click="selectColor(color)"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      colors: [
        { name: "белый", value: "#ffffff" },
        { name: "черный", value: "#000000" },
        { name: "бежевый", value: "#F9F1DC" },
      ],
      selectedColor: { name: "белый", value: "#ffffff" },
    };
  },
  methods: {
    selectColor(color) {
      this.selectedColor = color;
    },
  },
};
</script>

<style scoped lang="scss">
.color_picker {
  display: flex;
  flex-direction: column;
  gap: 16px;

  padding: 34px 16px 0 16px;


  &-label {
    color: rgb(79, 79, 79);
    font-family: "Helvetica";
    font-size: 10px;
    font-weight: 400;
    line-height: 14px;
    text-align: left;
  }

  &-options {
    display: flex;
    gap: 16px;
    align-items: flex-end;
  }

  &-square {
    width: 28px;
    height: 28px;
    cursor: pointer;
    position: relative;
    transition: border 0.2s ease;

    &.white {
      border: 1px solid #bdbdbd;
    }

    &:not(.white) {
      border: none;
    }

    &.active {
      border: 2px solid #bdbdbd;

      &::after {
        content: "";
        position: absolute;
        bottom: -6px;
        left: 0;
        width: 100%;
        height: 1px;
        background-color: #4f4f4f;
      }
    }
  }
}
</style>
