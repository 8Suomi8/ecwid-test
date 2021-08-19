<template>
  <section class="features">
    <div class="content">
      <ul class="features-list">
        <li
          class="features-list__item"
          v-for="(feature, index) in featuresList"
          :key="`feature-${index}`"
        >
          <div class="features-list__icon-wrapper">
            <img class="features-list__icon" :src="feature.img" />
          </div>
          <p class="features-list__text" v-html="feature.text"></p>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
  import sheepIcon from '@/assets/icons/sheep.png';
  import starIcon from '@/assets/icons/star.png';
  import shipmentIcon from '@/assets/icons/shipment.png';
  import placemarkIcon from '@/assets/icons/placemark.png';
  import operatorIcon from '@/assets/icons/operator.png';

  export default {
    data() {
      return {
        featuresList: [
          {
            img: sheepIcon,
            text: 'Только<br> натуральный состав',
          },
          {
            img: starIcon,
            text: 'Актуальное<br> наличие на сайте',
          },
          {
            img: shipmentIcon,
            text: 'Быстрая<br> отправка',
          },
          {
            img: placemarkIcon,
            text: 'Удобное<br> расположение',
          },
          {
            img: operatorIcon,
            text: 'Помощь<br> в подборе товаров',
          },
        ],
      };
    },
  };
</script>

<style scoped lang="scss">
  @import '@/assets/styles/var.scss';

  .features-list {
    padding: 70px 0;
    display: flex;
    justify-content: space-around;
    &__item {
      text-align: center;
    }
    &__icon-wrapper {
      height: 90px;
      margin-bottom: 17px;
    }
    &__icon {
      max-height: 90px;
    }
    &__text {
      font-size: 14px;
      color: $baseColor;
      line-height: 1.4;
    }
  }
  @media (max-width: 768px) {
    .features-list {
      display: block;
      &__item {
        margin-bottom: 40px;
        &:last-child {
          margin-bottom: 0;
        }
      }
    }
  }
</style>
