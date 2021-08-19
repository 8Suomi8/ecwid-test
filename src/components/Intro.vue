<template>
  <section class="intro">
    <div class="intro__info">
      <h1 class="intro__title">ДОБРО ПОЖАЛОВАТЬ В НАШ НОВЫЙ МАГАЗИН!</h1>
      <p class="intro__text">
        Мы садимся вязать, и вселенная вокруг начинает жить по-другому. Точнее,
        мы создаем собственную вселенную, в которой мы отдыхаем, вдохновляемся и
        создаем шедевры. Наш магазин за то, чтобы вы занимались своим любимым
        делом с удовольствием. Наш магазин – это место, где вам предложат пряжу
        и инструмент исключительного качества для создания лучших творений,
        которые вы только задумали. Наш магазин – это место, куда вы просто
        можете прийти поболтать и выпить чашечку кофе за вязанием
      </p>
      <a href="#" class="intro__link">Узнать о нас больше</a>
    </div>
    <div class="video">
      <button class="video__btn">
        <img :src="playIcon" class="video__icon" />
      </button>
    </div>
  </section>
</template>

<script>
  import playIcon from '/public/icons/play.svg';

  export default {
    data() {
      return {
        playIcon,
      };
    },
  };
</script>

<style scoped lang="scss">
  @import '@/assets/styles/var.scss';
  .intro {
    display: flex;
    width: 100%;
    max-width: 976px;
    margin: 0 auto;
    &__info {
      flex-grow: 1;
      display: flex;
      flex-direction: column;
    }
    &__title {
      font-size: 16px;
      line-height: 1.5;
      font-weight: 700;
      text-transform: uppercase;
      margin-bottom: 10px;
    }
    &__text {
      font-size: 12px;
      line-height: 2.2;
    }

    &__link {
      display: inline-block;
      margin-left: auto;
      margin-top: 20px;
      color: $baseColor;
      text-decoration: underline;
    }
  }
  .video {
    width: 350px;
    margin-left: 90px;
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 1px solid $baseColor;
    background: #f9edf0;
    &__btn {
      outline: none;
      border: none;
      cursor: pointer;
      background: transparent;
    }
    &__icon {
      width: 60px;
      height: 60px;
    }
  }
  @media (max-width: 1006px) {
    .intro {
      padding: 0 15px;
      display: block;
    }
    .video {
      width: 100%;
      height: 400px;
      margin-left: 0;
      margin-top: 50px;
    }
  }
  @media (max-width: 600px) {
    .video {
      height: 200px;
    }
  }
</style>
