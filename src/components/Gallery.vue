<template>
  <div class="content">
    <div class="slider">
      <button class="slider__nav slider__nav_prev" @click="prevSlide">
        <img :src="navIcon" class="slider__icon" />
      </button>
      <div
        class="slider__wrapper"
        v-bind:style="{ left: sliderTranslate + 'px' }"
      >
        <div
          class="slider__slide"
          v-for="(slide, index) in sliderList"
          :key="`slider-${index}`"
        >
          <img :src="slide.img" />
        </div>
      </div>
      <button class="slider__nav slider__nav_next" @click="nextSlide">
        <img :src="navIcon" class="slider__icon" />
      </button>
      <div class="slider__pagination">
        <div
          :class="[
            'slider__pagination-item',
            { slider__pagination_active: index == sliderActive },
          ]"
          v-for="(slide, index) in sliderList"
          :key="`pagination-${index}`"
        ></div>
      </div>
    </div>
  </div>
</template>

<script>
  import navIcon from '/public/icons/left.svg';
  export default {
    name: 'Gallery',
    components: {},
    props: {},
    setup() {
      return {};
    },
    data() {
      return {
        navIcon,
        sliderList: [
          { img: require('@/assets/img/banner.png') },
          { img: require('@/assets/img/banner.png') },
          { img: require('@/assets/img/banner.png') },
        ],
        sliderActive: 1,
        sliderTranslate: 0,
      };
    },
    computed: {
      sliderCount() {
        return this.sliderList.length;
      },
      sliderWidth() {
        const slider = this.$el.querySelector('.slider');
        return slider.offsetWidth;
      },
    },
    watch: {
      sliderActive: function() {},
    },
    methods: {
      initSlider: function() {},
      nextSlide: function() {
        if (this.sliderActive < this.sliderCount) {
          this.sliderActive += 1;
          this.sliderTranslate -= this.sliderWidth;
        } else {
          this.sliderActive = 1;
          this.sliderTranslate = 0;
        }
      },
      prevSlide: function() {
        if (this.sliderActive > 1) {
          this.sliderActive -= 1;
          this.sliderTranslate += this.sliderWidth;
        } else {
          this.sliderActive = this.sliderCount;
          this.sliderTranslate = -(this.sliderCount - 1) * this.sliderWidth;
        }
      },
    },
    mounted() {
      this.initSlider();
    },
  };
</script>

<style scoped lang="scss">
  @import '@/assets/styles/var.scss';
  .slider {
    width: 100%;
    height: 400px;
    display: flex;
    align-items: center;
    position: relative;
    overflow: hidden;
    &__wrapper {
      display: flex;
      height: 100%;
      position: relative;
      transition: all 0.3s ease-in-out;
    }
    &__slide {
      height: 100%;
      flex-shrink: 0;
      img {
        width: 100%;
        height: 100%;
      }
    }
    &__nav {
      position: absolute;
      content: '';
      width: 30px;
      height: 30px;
      border: 1px solid $baseColor;
      background: #fff;
      border-radius: 50%;
      outline: none;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      z-index: 2;
      &_prev {
        left: 22px;
      }
      &_next {
        right: 22px;
        transform: rotate(180deg);
      }
    }
    &__icon {
      width: 7px;
      height: 12px;
    }
  }
</style>
