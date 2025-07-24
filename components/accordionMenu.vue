<template>
  <div class="accordion">
    <div
      class="accordion-item"
      v-for="(item, index) in items"
      :key="index"
      :class="{ 'with-top': index === 0 }"
    >
      <div class="accordion-header" @click="toggle(index)">
        <span class="accordion-title">{{ item.title }}</span>
        <span
          class="accordion-icon"
          :class="{ rotated: openIndexes.includes(index) }"
        >
          <svg
            width="12"
            height="12"
            viewBox="0 0 12 12"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M10.5 6.5V5.5H6.5V1.5H5.5V5.5H1.5V6.5H5.5V10.5H6.5V6.5H10.5Z"
              fill="#828282"
            />
          </svg>
        </span>
      </div>

      <transition name="accordion">
        <div v-show="openIndexes.includes(index)" class="accordion-content">
          <p>{{ item.content }}</p>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          title: "Описание",
          content: "Здесь текст описания товара.",
        },
        {
          title: "Состав и уход",
          content: "Хлопок 100%. Машинная стирка при 30°C.",
        },
      ],
      openIndexes: [],
    };
  },
  methods: {
    toggle(index) {
      if (this.openIndexes.includes(index)) {
        this.openIndexes = this.openIndexes.filter((i) => i !== index);
      } else {
        this.openIndexes.push(index);
      }
    },
  },
};
</script>

<style scoped lang="scss">
.accordion {
  width: 100%;
  padding: 34px 16px 40px 16px;

  &-item {
    padding: 15px 7px 12px 0;
    border-bottom: 1px solid #e0e0e0;

    &.with-top {
      border-top: 1px solid #e0e0e0;
    }
  }

  &-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    width: 100%;

    color: rgb(51, 51, 51);
    font-family: "Helvetica";
    font-size: 10px;
    font-weight: 400;
    line-height: 14px;
    text-transform: uppercase;
  }

  &-title {
    font-weight: 500;
    font-size: 14px;
    color: #333;
  }

  &-icon {
    transition: transform 0.3s ease;
  }

  &-icon.rotated {
    transform: rotate(45deg);
  }

  &-content {
    overflow: hidden;
    padding-top: 10px;
    font-size: 14px;
    color: rgb(51, 51, 51);
    font-family: "Helvetica";
    font-size: 9px;
    font-weight: 400;
    line-height: 14px;
    text-transform: uppercase;
  }
}

.accordion-enter-active,
.accordion-leave-active {
  transition: all 0.3s ease;
  overflow: hidden;
}

.accordion-enter,
.accordion-leave-to {
  max-height: 0;
  opacity: 0;
  padding-top: 0;
  padding-bottom: 0;
}

.accordion-enter-to,
.accordion-leave {
  max-height: 200px;
  opacity: 1;
  padding-top: 10px;
}



@media (min-width: 712px) {
    
}
</style>
