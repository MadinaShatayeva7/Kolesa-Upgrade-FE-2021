<template>
  <div id="app" class="app">
    <header class="header">
            <div class="mobile">
                <div class="mobile__burger">
                    <a href="#" class="mobile__burger-item">
                        <img src="./assets/burger.svg" alt="Кнопка меню">
                    </a>
                </div>
                <div class="mobile__logo">
                    <a href="#" class="mobile__logo-item">
                        <img src="./assets/Kolesa-group-mob.svg" alt="Kolesagroup логотип мини">
                    </a>
                </div>
            </div>
            <div class="header__logo">
                <a href="#" class="header__logo-item">
                    <img src="./assets/Kolesagroup.svg" alt="Kolesagroup логотип">
                </a>
            </div>
            <div class="header__right">
                <form action="" class="search">
                    <input type="text" class="search__input" name="search" placeholder="Поиск">
                    <button type="button" title="Поиск" id="btn" class="search__btn"></button>
                </form>
                <div class="account-wrap">
                    <a href="#" class="account">
                        <img src="./assets/rick.png" alt="Картинка Рика" class="account__image">
                        <span class="account__desc">
                            <p class="account__name">Мортиджан</p>
                            <p class="account__text">300 баллов</p>
                        </span>
                    </a>
                </div>
            </div>
        </header>
        <main class="main">
            <aside class="sidebar">
                <nav class="menu">
                    <ul class="menu__list">
                        <li class="menu__item">
                            <a href="#" class="menu__link">Оргсхема</a>
                        </li>
                        <li class="menu__item">
                            <a href="#" class="menu__link">Kolesa <strong>Team</strong></a>
                        </li>
                        <li class="menu__item">
                            <a href="#" class="menu__link active">Kolesa <strong>Shop</strong></a>
                        </li>
                        <li class="menu__item">
                            <a href="#" class="menu__link">Картина компании</a>
                        </li>
                        <li class="menu__item">
                            <a href="#" class="menu__link">Новости</a>
                        </li>
                        <li class="menu__item">
                            <a href="#" class="menu__link">Education</a>
                        </li>
                        <li class="menu__item">
                            <a href="#" class="menu__link">Guidelines</a>
                        </li>
                        <li class="menu__item">
                            <a href="#" class="menu__link">Библиотека</a>
                        </li>
                        <li class="menu__item">
                            <a href="#" class="menu__link">FAQ</a>
                        </li>
                    </ul>
                </nav>
            </aside>
            <section class="content">
                <div class="content__image image">
                    <picture>
                        <source media="(max-width: 767px)" srcset="./assets/banner-mob2.jpg">
                        <source media="(min-width: 768px)" srcset="./assets/banner.jpg">
                        <img src="./assets/banner.jpg" class="image__item"
                        alt="Горячее предложение">
                    </picture>
                </div>
                <div class="content__questions questions">
                    <button type="button" class="questions__item questions__item--take">
                      Получить баллы</button>
                    <button type="button" class="questions__item questions__item--how">
                      Как получить баллы</button>
                    <button type="button" class="questions__item questions__item--present">
                      Подарить баллы</button>
                </div>
                <div class="content__tabs tabs">
                    <button
                    v-for="tab in tabs" :key="tab.value"
                    :class="{ 'tabs__item--active': tab.value === activeTab }"
                    @click="sortTabs(tab)"
                    data-id="all" type="button"
                    class="js-tabs-btn tabs__item">
                    {{tab.name}}</button>
                </div>
                <div class="content">
                  <div class="content__products">
                    <div
                    v-for="item in filterProducts" :key="item.id"
                    class="content__product">
                      <div class="card">
                        <div class="card__image">
                          <img :src="item.img" :alt="item.alt">
                          <span class="card__label" v-if="item.badge">New</span>
                        </div>
                        <div class="card__desc">
                          <h3 class="card__ball">{{item.price}} баллов</h3>
                          <p class="card__name">{{item.title}}</p>
                          <p class="card__sizes">Размеры {{item.size}}</p>
                          <button type="button" data-type="modal"
                          class="card__btn" @click="openModal">
                            Заказать
                          </button>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
            </section>
        </main>
        <footer class="footer">
            <div class="footer__left">
                <p class="footer__copyright">© Kolesa Group</p>
                <div class="socials">
                    <a href="https://www.instagram.com/" rel="nofollow noopener noreferrer"
                    target="_blank" class="socials__link">
                        <img src="./assets/Instagram.svg" alt="instagram" class="socials__icon">
                    </a>
                    <a href="https://www.youtube.com/" rel="nofollow noopener noreferrer"
                    target="_blank" class="socials__link">
                        <img src="./assets/YouTube.svg" alt="youtube" class="socials__icon">
                    </a>
                    <a href="https://www.vk.com/" rel="nofollow noopener noreferrer"
                    target="_blank" class="socials__link">
                        <img src="./assets/VK.svg" alt="vkontakte" class="socials__icon">
                    </a>
                </div>
            </div>
            <div class="footer__right">
                <div class="footer__desc">
                    <p class="footer__desc-item">Есть идеи что улучшить? </p>
                    <p class="footer__desc-item">Не знаешь, с кем решить проблему?</p>
                </div>
                <div class="footer__btn">
                    <button type="button" class="footer__button">Написать</button>
                </div>
            </div>
        </footer>
        <div class="modal-main-wrap" v-if="isShowModal">
          <div class="modal-overlay" @click="closeModal"></div>
          <div class="modal-window-wrap">
            <div class="modal-wrapper">
              <button type="button" @click="closeModal"
              class="modal-wrapper__btn"></button>
              <div class="images">
                  <img src="./assets/image.png" alt="Футболка Эволюционируй или сдохни">
                  <div class="images__items">
                      <img src="./assets/image-1.png"
                      alt="Футболка Эволюционируй или сдохни 01" class="images__item">
                      <img src="./assets/image-2.png"
                      alt="Футболка Эволюционируй или сдохни 02" class="images__item active">
                      <img src="./assets/image-3.png"
                      alt="Футболка Эволюционируй или сдохни 03" class="images__item">
                  </div>
              </div>
              <div class="modal-wrapper__desc">
                  <h3 class="modal-wrapper__title">Футболка "Эволюционируй или сдохни"</h3>
                  <div class="modal-wrapper__blocks scores">
                      <div class="scores__left">
                          <h4 class="scores__left-title">100 баллов</h4>
                          <button type="button" class="scores__btn">Попросить 50 баллов</button>
                      </div>
                      <div class="scores__right">
                          <p class="scores__title">Твой баланс:</p>
                          <p class="scores__text">50 баллов</p>
                      </div>
                  </div>
                  <div class="modal-wrapper__blocks colors">
                      <h5 class="colors__title">Цвета:</h5>
                      <div class="colors__items">
                          <input type="radio" class="colors__item" id="radio-1" name="colors">
                          <label for="radio-1" class="colors__label colors__blue">Синий</label>

                          <input type="radio" class="colors__item" id="radio-2" name="colors">
                          <label for="radio-2" class="colors__label colors__beige">Бежевый</label>

                          <input type="radio" class="colors__item" id="radio-3" name="colors">
                          <label for="radio-3" class="colors__label colors__grey">Серый</label>
                      </div>
                  </div>
                  <div class="modal-wrapper__blocks size">
                      <h5 class="size__title">Размер:</h5>
                      <div class="size__items">
                          <input type="radio" class="size__input" id="size-1" name="size">
                          <label for="size-1" class="size__label">S</label>

                          <input type="radio" class="size__input" id="size-2" name="size">
                          <label for="size-2" class="size__label">M</label>

                          <input type="radio" class="size__input" id="size-3" name="size">
                          <label for="size-3" class="size__label">L</label>
                      </div>
                  </div>
                  <div class="modal-wrapper__blocks">
                      <h5 class="modal-wrapper__details">Детали:</h5>
                      <p>Брендированная толстовка от Qazaq Republic.
                        Материал: Хлопок 80%, Вискоза 20%</p>
                  </div>
                  <div class="modal-wrapper__blocks">
                      <h5 class="modal-wrapper__question">Как выбрать размер:</h5>
                      <p>Написать дяде Рику для уточнения.</p>
                  </div>
                </div>
              </div>
          </div>
        </div>
  </div>
</template>

<script>
import { clothes, accessories } from './mock';

const allStuff = clothes.concat(accessories).sort((good) => (good.badge ? -1 : 1));
const newClothes = clothes.sort((good) => (good.badge ? -1 : 1));
const newAccessories = accessories.sort((good) => (good.badge ? -1 : 1));

export default {
  name: 'App',
  data() {
    return {
      isShowModal: false,
      allStuff,
      tabs: [
        { name: 'Все товары', id: 1, value: 'allStuff' },
        { name: 'Одежда', id: 2, value: 'clothes' },
        { name: 'Аксессуары', id: 3, value: 'accessories' },
      ],
      activeTab: 'allStuff',
      sortedProducts: [],
    };
  },
  computed: {
    filterProducts() {
      if (this.sortedProducts.length) {
        return this.sortedProducts;
      }
      return this.allStuff;
    },
  },
  methods: {
    openModal() {
      this.isShowModal = true;
    },
    closeModal() {
      this.isShowModal = false;
    },
    sortTabs(tab) {
      this.activeTab = tab.value;
      if (tab.value === 'clothes') {
        this.sortedProducts = newClothes;
        return;
      }
      if (tab.value === 'accessories') {
        this.sortedProducts = newAccessories;
        return;
      }
      this.sortedProducts = allStuff;
    },
  },
};
</script>

<style lang="scss">
@import './styles/style.scss';

#app {
  font-family: "Open Sans", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  min-height: 100vh;
  display: grid;
  grid-template: minmax(104px, auto) 1fr minmax(100px, auto) / 1fr;
  grid-template-areas: 'header' 'main' 'footer';
}
</style>
