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
        <button
          :class="['hamburger', { hamburger_opened: isMenuActive }]"
          @click="openMenu"
        >
          <div class="hamburger__strip"></div>
        </button>
      </div>
      <nav :class="['mobile-menu', { 'mobile-menu_opened': isMenuActive }]">
        <a href="#" class="cart-link">
          <span class="cart-link__text">Перейти в корзину </span>
          <img class="cart-link__icon" :src="cartIcon" />
        </a>
        <ul class="menu">
          <li class="menu__item" v-for="item in menuList" :key="item">
            <a :href="item.link" class="menu__link">{{ item.text }}</a>
          </li>
        </ul>

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
      </nav>
    </div>
    <nav class="menu-wrapper">
      <div class="content">
        <ul class="menu">
          <li class="menu__item" v-for="item in menuList" :key="item">
            <a :href="item.link" class="menu__link">{{ item.text }}</a>
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
        menuList: [
          {
            text: 'Пряжа',
            link: '#',
          },
          {
            text: 'Спицы',
            link: '#',
          },
          {
            text: 'Крючки',
            link: '#',
          },
          {
            text: 'Аксессуары',
            link: '#',
          },
          {
            text: 'Подарочные сертификаты',
            link: '#',
          },
          {
            text: 'МК и описания',
            link: '#',
          },
          {
            text: 'Модели',
            link: '#',
          },
        ],
        logoImg,
        clockIcon,
        locationIcon,
        phoneIcon,
        cartIcon,
        isMenuActive: false,
      };
    },
    methods: {
      openMenu() {
        this.isMenuActive = !this.isMenuActive;
      },
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
    z-index: 4;
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
    color: inherit;
    text-decoration: none;
    display: flex;
    align-items: center;
    &__text {
      font-size: 14px;
    }
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
  .hamburger {
    display: none;
    z-index: 4;
  }
  .mobile-menu {
    display: none;
  }
  @media (max-width: 1140px) {
    .header {
      .content {
        padding: 0 15px;
      }
    }
  }
  @media (max-width: 860px) {
    .info-block {
      display: none;
    }
    .cart-link {
      display: none;
    }
    .menu-wrapper {
      display: none;
    }
    .top-header {
      margin-bottom: 0;
    }
    .hamburger {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      outline: none;
      border: none;
      cursor: pointer;
      width: 40px;
      height: 40px;
      position: relative;
      background: transparent;
      &_opened {
        .hamburger {
          &__strip {
            transform: rotate(45deg);
            top: 20px;
            &::before {
              opacity: 0;
            }
            &::after {
              transform: rotate(-90deg);
              top: 0px;
            }
          }
        }
      }

      &__strip {
        position: absolute;
        width: 40px;
        height: 3px;
        background-color: $baseColor;
        top: 10px;
        left: 0;
        transition: all 0.1s ease-in-out;
        &::before {
          content: '';
          left: 0;
          top: 10px;
          position: absolute;
          width: 40px;
          height: 3px;
          background-color: $baseColor;
          transition: all 0.1s ease-in-out;
        }
        &::after {
          content: '';
          left: 0;
          top: 20px;
          position: absolute;
          width: 40px;
          height: 3px;
          background-color: $baseColor;
          transition: all 0.1s ease-in-out;
        }
      }
    }
    .mobile-menu {
      box-shadow: 0px 3px 3px #53535326;
      display: none;
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      z-index: 3;
      background: #fff;
      padding: 20px;
      &_opened {
        display: block;
      }
      .cart-link {
        display: flex;
        justify-content: center;
        margin-bottom: 20px;
        &__text {
          margin-right: 10px;
        }
      }
      .info-block {
        display: flex;
        max-width: 240px;
        margin: 15px auto;
      }
      .menu {
        padding: 20px 0;
        flex-direction: column;
      }
    }
  }
  @media (max-width: 500px) {
    .cart-link {
      &__text {
        display: none;
      }
    }
  }
</style>
