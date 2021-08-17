<template>
  <header class="header">
    <div class="content">
      <div class="top-header">
        <img class="logo" :src="logoImg" />
        <div class="info-block">
          <img alt="" class="info-block__icon" :src="locationIcon" />
          <div class="info-block__content">
            <span class="info-block__text">м. Кропоткинская</span>
            <span class="info-block__text">Соймоновский проезд, д.7 с.1</span>
          </div>
        </div>
        <div class="info-block">
          <img alt="" class="info-block__icon" :src="clockIcon" />
          <div class="info-block__content">
            <span class="info-block__text">Пн - Пт&nbsp; 11 - 20</span>
            <span class="info-block__text">Сб - Вск 11 - 18</span>
          </div>
        </div>
        <div class="info-block">
          <img alt="" class="info-block__icon" :src="phoneIcon" />
          <div class="info-block__content">
            <a
              class="info-block__text info-block__text_link"
              href="tel:+78000000000"
              >+7 800 000 00 00</a
            >
            <a
              class="info-block__text info-block__text_link"
              href="tel:+78000000000"
              >+7 800 000 00 00</a
            >
          </div>
        </div>
        <a href="#" class="cart-link">
          <img class="cart-link__icon" :src="cartIcon" />
        </a>
      </div>
    </div>
    <nav class="menu-wrapper">
      <div class="content">
        <ul class="menu">
          <li class="menu__item">
            <a href="#" class="menu__link">Пряжа</a>
          </li>
          <li class="menu__item">
            <a href="#" class="menu__link">Спицы</a>
          </li>
          <li class="menu__item">
            <a href="#" class="menu__link">Крючки</a>
          </li>
          <li class="menu__item">
            <a href="#" class="menu__link">Аксессуары</a>
          </li>
          <li class="menu__item">
            <a href="#" class="menu__link">Подарочные сертификаты</a>
          </li>
          <li class="menu__item">
            <a href="#" class="menu__link">МК и описания</a>
          </li>
          <li class="menu__item">
            <a href="#" class="menu__link">Модели</a>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
  import logoImg from '@/assets/img/logo.png';
  import clockIcon from '@/assets/icons/clock.png';
  import locationIcon from '@/assets/icons/location.png';
  import phoneIcon from '@/assets/icons/phone.png';
  import cartIcon from '@/assets/icons/cart.png';
  export default {
    name: 'Header',
    components: {},
    props: {},
    data() {
      return {
        logoImg,
        clockIcon,
        locationIcon,
        phoneIcon,
        cartIcon,
      };
    },
  };
</script>

<style scoped lang="scss">
  @import '@/assets/styles/var.scss';
  .header {
    padding: 30px 0 34px 0;
  }
  .top-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 20px;
  }
  .logo {
    max-width: 91px;
  }
  .info-block {
    display: flex;
    align-items: center;
    &__icon {
      margin-right: 17px;
      height: 30px;
    }
    &__content {
    }
    &__text {
      font-size: 13px;
      line-height: 17px;
      display: block;
      &_link {
        color: inherit;
        text-decoration: none;
      }
    }
  }
  .cart-link {
    &__icon {
    }
  }
  .menu-wrapper {
    background: $baseColor;
    // background: #497952;
    color: #fff;
  }
  .menu {
    display: flex;
    align-items: center;
    justify-content: center;
    &__item {
    }
    &__link {
      color: inherit;
      text-decoration: none;
      font-weight: 700;
      font-size: 14px;
      padding: 11px 15px;
      display: block;
    }
  }
</style>
