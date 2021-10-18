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
                            <span class="account__name">Мортиджан</span>
                            <span class="account__text">300 баллов</span>
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
                    <button data-id="all" type="button"
                    class="js-tabs-btn tabs__item tabs__item--active">
                      Все товары</button>
                    <button data-id="clothes" type="button" class="js-tabs-btn tabs__item">
                      Одежда</button>
                    <button data-id="accessories" type="button" class="js-tabs-btn tabs__item">
                      Аксессуары</button>
                </div>
                <div class="js-products">
                </div>
            </section>
        </main>
        <footer class="footer">
            <div class="footer__left">
                <p class="footer__copyright">© Kolesa Group</p>
                <div class="socials">
                    <a href="https://www.instagram.com/" rel="nofollow noopener noreferrer" target="_blank" class="socials__link">
                        <img src="./assets/Instagram.svg" alt="instagram" class="socials__icon">
                    </a>
                    <a href="https://www.youtube.com/" rel="nofollow noopener noreferrer" target="_blank" class="socials__link">
                        <img src="./assets/YouTube.svg" alt="youtube" class="socials__icon">
                    </a>
                    <a href="https://www.vk.com/" rel="nofollow noopener noreferrer" target="_blank" class="socials__link">
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
  </div>
</template>

<script>

export default {
  name: 'App',
};
</script>

<style lang="scss">
@import './styles/vars.scss';
@import './styles/reset.scss';
@import './styles/layout.scss';
@import './styles/header.scss';
@import './styles/header-mobile.scss';
@import './styles/search.scss';
@import './styles/account.scss';
@import './styles/sidebar.scss';
@import './styles/main.scss';
@import './styles/questions.scss';
@import './styles/tabs.scss';
@import './styles/cards.scss';
@import './styles/footer.scss';
@import './styles/socials.scss';
@import './styles/modal-window.scss';
@import './styles/modal-images.scss';
@import './styles/modal-scores.scss';
@import './styles/modal-sizes.scss';
@import './styles/modal-colors.scss';

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
