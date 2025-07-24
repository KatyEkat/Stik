<template>
  <div class="content-desctop">
    <div class="product_slider slider-mob">
      <div class="slider_slider-wrapper">
        <div class="image-container">
          <button class="arrow left" @click="prevSlide">
            <svg
              width="32"
              height="32"
              viewBox="0 0 32 32"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <rect
                width="32"
                height="32"
                rx="16"
                transform="matrix(4.37114e-08 1 1 -4.37114e-08 0 0)"
                fill="white"
                fill-opacity="0.4"
              />
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M8 16L13.2754 21L14.2434 20.0825L10.6205 16.6488L23 16.6488L23 15.3512L10.6205 15.3512L14.2434 11.9175L13.2754 11L8 16Z"
                fill="black"
              />
            </svg>
          </button>

          <img
            :src="images[currentSlide]"
            alt="Product-image"
            class="main-image"
          />

          <button class="arrow right" @click="nextSlide">
            <svg
              width="32.000000"
              height="32.000000"
              viewBox="0 0 32 32"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
            >
              <defs>
                <clipPath id="clip739_170">
                  <rect
                    id="arrow-right-outline"
                    rx="15.500000"
                    width="31.000000"
                    height="31.000000"
                    transform="translate(32.500000 0.500000) rotate(90.000000)"
                    fill="white"
                    fill-opacity="0"
                  />
                </clipPath>
              </defs>
              <rect
                id="arrow-right-outline"
                rx="15.500000"
                width="31.000000"
                height="31.000000"
                transform="translate(32.500000 0.500000) rotate(90.000000)"
                fill="#FFFFFF"
                fill-opacity="0.400000"
              />
              <g clip-path="url(#clip739_170)">
                <path
                  id="Vector (Stroke)"
                  d="M24 16L18.72 21L17.75 20.08L21.37 16.64L9 16.64L9 15.35L21.37 15.35L17.75 11.91L18.72 11L24 16Z"
                  fill="#000000"
                  fill-opacity="1.000000"
                  fill-rule="evenodd"
                />
              </g>
            </svg>
          </button>
        </div>
      </div>

      <div class="dots">
        <span
          v-for="(img, i) in images"
          :key="i"
          class="dot"
          :class="{ active: i === currentSlide }"
          @click="goToSlide(i)"
        ></span>
      </div>
    </div>

    <div class="slider-desc">
      <div class="slider_layout">
        <div class="slider_thumbnails">
          <img
            v-for="(img, index) in images"
            :key="index"
            :src="img"
            :alt="'thumb-' + index"
            class="thumbnail"
            :class="{ active: currentSlide === index }"
            @click="goToSlide(index)"
          />
        </div>

        <div class="image-container">
          <button class="arrow left" @click="prevSlide">
            <svg
              width="32.000000"
              height="32.000000"
              viewBox="0 0 32 32"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
            >
              <defs>
                <clipPath id="clip739_164">
                  <rect
                    id="arrow-left-outline"
                    rx="15.500000"
                    width="31.000000"
                    height="31.000000"
                    transform="matrix(4.37114e-08 1 1 -4.37114e-08 0.5 0.5)"
                    fill="white"
                    fill-opacity="0"
                  />
                </clipPath>
              </defs>
              <rect
                id="arrow-left-outline"
                rx="15.500000"
                width="31.000000"
                height="31.000000"
                transform="matrix(4.37114e-08 1 1 -4.37114e-08 0.5 0.5)"
                fill="#FFFFFF"
                fill-opacity="0.400000"
              />
              <g clip-path="url(#clip739_164)">
                <path
                  id="Vector (Stroke)"
                  d="M8 16L13.27 21L14.24 20.08L10.62 16.64L23 16.64L23 15.35L10.62 15.35L14.24 11.91L13.27 11L8 16Z"
                  fill="#BDBDBD"
                  fill-opacity="1.000000"
                  fill-rule="evenodd"
                />
              </g>
            </svg>
          </button>

          <img
            :src="images[currentSlide]"
            alt="Product-image"
            class="main-image"
          />

          <button class="arrow right" @click="nextSlide">
            <svg
              width="32"
              height="32"
              viewBox="0 0 32 32"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <rect
                x="32"
                width="32"
                height="32"
                rx="16"
                transform="rotate(90 32 0)"
                fill="white"
                fill-opacity="0.4"
              />
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M24 16L18.7246 21L17.7566 20.0825L21.3795 16.6488L9 16.6488L9 15.3512L21.3795 15.3512L17.7566 11.9175L18.7246 11L24 16Z"
                fill="black"
              />
            </svg>
          </button>
        </div>
      </div>

      <div class="dots">
        <span
          v-for="(img, i) in images"
          :key="i"
          class="dot"
          :class="{ active: i === currentSlide }"
          @click="goToSlide(i)"
        ></span>
      </div>
    </div>

    <div class="product_info-block">
      <div class="product_info">
        <p class="product_info-title">ЖАКЕТ УДЛИНЁННЫЙ, БЕЛЫЙ</p>
        <p class="product_info-price">8900 RUB</p>
      </div>
      <div class="product_info-save-mob-img">
        <svg
          width="14"
          height="18"
          viewBox="0 0 14 18"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M0.5 0H13.5V17.4819L7.01338 13.1182L0.5 17.4819V0ZM1.5 1V15.5181L7.01338 11.8818L12.5 15.5181V1H1.5Z"
            fill="#333333"
          />
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentSlide: 0,
      images: [
        "../img/mainLady.png",
        "/img/mainLady2.png",
        "/img/mainLady3.png",
        "/img/mainLady4.png",
      ],
    };
  },
  methods: {
    nextSlide() {
      this.currentSlide = (this.currentSlide + 1) % this.images.length;
    },
    prevSlide() {
      this.currentSlide =
        (this.currentSlide - 1 + this.images.length) % this.images.length;
    },
    goToSlide(index) {
      this.currentSlide = index;
    },
  },
};
</script>

<style scoped lang="scss">
.slider-desc {
  display: none;
}

.slider-mob {
  display: block;
}

.product_slider {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;

  &-wrapper {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}

.arrow {
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  z-index: 2;

  &.left {
    left: 10px;
  }

  &.right {
    right: 10px;
  }

  img {
    width: 32px;
    height: 32px;
  }
}

.image-container {
  position: relative;
  width: 375px;
  height: 617px;

  .main-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }

  .arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 32px;
    height: 32px;
    background: rgba(255, 255, 255, 0.4);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    padding: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 3;

    svg {
      width: 100%;
      height: 100%;
    }

    &.left {
      left: 16px;
    }

    &.right {
      right: 16px;
    }
  }
}

.dots {
  display: flex;
  gap: 6px;
  position: relative;
  top: -25px;

  .dot {
    width: 7px;
    height: 7px;
    border-radius: 50%;
    background-color: rgba(255, 255, 255, 0.4);
    transition: background-color 0.3s ease;
    cursor: pointer;

    &.active {
      background-color: #ffffff;
    }
  }
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

  &-save-mob-img {
    display: flex;
  }
}

.product_info-block {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 31px 25px 0 17px;
  max-width: 400px;
}

@media (min-width: 712px) {

  .product_info-block{
    padding: 31px 0 0 40px;
  }


  .slider-mob {
    display: none;
  }

  .slider-desc {
    display: block;
  }

  .product_slider {
    flex-direction: row;
    justify-content: center;
    align-items: flex-start;
    gap: 24px;
  }

  .slider_slider-wrapper {
    display: flex;
    flex-direction: row;
    gap: 20px;
  }

  .image-container {
    width: 500px;
    height: auto;
  }

  .main-image {
    width: 100%;
    height: auto;
  }

  .dots {
    position: static;
    margin-top: 10px;
  }

  .arrow.left {
    left: 10px;
  }

  .arrow.right {
    right: 10px;
  }
  .slider_layout {
    display: flex;
    flex-direction: row;
    gap: 20px;
    justify-content: center;
  }

  .slider_thumbnails {
    display: flex;
    flex-direction: column;
    gap: 10px;

    .thumbnail {
      width: 60px;
      height: 100px;
      object-fit: cover;
      cursor: pointer;
      opacity: 0.6;
      border: 1px solid transparent;

      &.active {
        opacity: 1;
        border-color: #000;
      }
    }
  }

  .image-container {
    width: 470px;
    height: 700px;
  }

  .dots {
    display: none;
  }
}

@media (min-width: 1024px) {
  .content-desctop {
    display: flex;
    /* width: 100%; */
    gap: 61px;
    padding: 0 72px;
  }

  .product_info-save-mob-img {
    display: none;
  }

  .product_info-block {
    display: none;
  }
}

@media (min-width: 1200px) {
  .content-desctop {
    width: fit-content;
  }
}
</style>
