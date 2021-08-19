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
        <button
          :class="[
            'slider__pagination-item',
            { 'slider__pagination-item_active': index == sliderActive },
          ]"
          v-for="(slide, index) in sliderList"
          :key="`pagination-${index}`"
          @click="slideTo(index)"
        ></button>
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
    data() {
      return {
        navIcon,
        sliderList: [
          { img: require('@/assets/img/banner.png') },
          { img: require('@/assets/img/banner.png') },
          { img: require('@/assets/img/banner.png') },
          { img: require('@/assets/img/banner.png') },
          { img: require('@/assets/img/banner.png') },
        ],
        sliderActive: 0,
        sliderWidth: 0,
      };
    },
    computed: {
      sliderCount() {
        return this.sliderList.length - 1;
      },
      sliderTranslate() {
        return -this.sliderWidth * this.sliderActive;
      },
    },
    methods: {
      getSliderSize: function() {
        const slider = this.$el.querySelector('.slider');
        this.sliderWidth = slider.offsetWidth;
      },
      nextSlide: function() {
        if (this.sliderActive < this.sliderCount) {
          this.sliderActive += 1;
          return;
        }
        this.sliderActive = 0;
      },
      prevSlide: function() {
        if (this.sliderActive > 0) {
          this.sliderActive -= 1;
          return;
        }
        this.sliderActive = this.sliderCount;
      },
      slideTo: function(index) {
        this.sliderActive = index;
      },
    },
    mounted() {
      this.getSliderSize();
      window.addEventListener('resize', () => {
        this.getSliderSize();
      });
    },
  };
</script>

<style scoped lang="scss">
  @import '@/assets/styles/var.scss';
  .slider {
    width: 100%;
    display: flex;
    align-items: center;
    position: relative;
    overflow: hidden;
    &__wrapper {
      display: flex;
      width: 100%;
      position: relative;
      transition: all 0.3s ease-in-out;
    }
    &__slide {
      width: 100%;
      flex-shrink: 0;
      img {
        width: 100%;
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
    &__pagination {
      position: absolute;
      display: flex;
      align-self: flex-end;
      z-index: 2;
      width: 100%;
      justify-content: center;
      padding-bottom: 25px;
    }
    &__pagination-item {
      display: block;
      outline: none;
      border: none;
      cursor: pointer;
      width: 10px;
      height: 10px;
      background: #fff;
      transition: all 0.3s ease-in-out;
      border-radius: 50%;
      margin: 0 15px;
      padding: 0;
      &_active {
        background: $baseColor;
      }
    }
  }
  @media (max-width: 768px) {
    .slider {
      padding-bottom: 40px;
      &__pagination {
        bottom: 0;
      }
      &__pagination-item {
        border: 1px solid $baseColor;
      }
    }
  }
</style>
