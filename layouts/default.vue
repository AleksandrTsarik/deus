<template>
  <div class="page-wrap">
    <header class="header">
      <div class="container">
        <div class="header__inner">
          <div class="header__logo">
            <TheNetwork :type="'logo'" />
          </div>
          <div class="burger" @click="menuOpen" :class="{'is-open': isOpenMenu}">
            <span></span>
            <span></span>
          </div>
          <div class="overlay" :class="{'is-open': isOpenMenu}"></div>
          <div class="header-mobile" :class="{'is-open': isOpenMenu}">
            
            <div class="header-mobile__menu">
              <div class="header-logo"><TheNetwork :type="'logo'"  /></div>
              <div class="header__info">
                <div class="header__info-block">
                  <p @click="openSubmenu" :class="{'is-open' : isOpen}">Продукты</p>
                  <ul class="header-nav__sublist"  :class="{'is-open' : isOpen}"> 
                    <li v-for="(item, i) in navSublist" :key="i">
                      <NuxtLink :to="item.url">
                        <p>{{ item.title }}</p>
                        <p>{{ item.text }}</p>
                      </NuxtLink>
                    </li>
                  </ul>
                </div>
                <nav class="header-nav">
                  <ul class="header-nav__list">
                    <li class="header-nav__item" v-for="(item, i) in navList" :key="i">
                      <NuxtLink v-if="item.url" :to="item.url">{{ item.name }}</NuxtLink>
                    </li>
                  </ul>
                </nav>
                <UITheButton :label="'Свяжитесь с нами'" class="btn btn-dark"/>
              </div>
            </div>
          </div>
          
          <div class="header__info header-desktop">
            <nav class="header-nav">
              <ul class="header-nav__list">
                <li>
                  <p class="header-nav__item-p">
                    Продукты
                    <ul class="header-nav__sublist"> 
                      <li v-for="(item, i) in navSublist" :key="i">
                        <NuxtLink :to="item.url">
                          <p>{{ item.title }}</p>
                          <p>{{ item.text }}</p>
                        </NuxtLink>
                      </li>
                    </ul>
                  </p>
                </li>
                <li class="header-nav__item" v-for="(item, i) in navList" :key="i">
                  <NuxtLink v-if="item.url" :to="item.url">{{ item.name }}</NuxtLink>
                  
                </li>
              </ul>
            </nav>
            <UITheButton :label="'Свяжитесь с нами'" class="btn btn-dark"/>
          </div>
        </div>
      </div>
    </header>

    <slot />

    <footer class="footer">
      <div class="container">
        <div class="footer__top">
          <div class="footer__logo">
            <TheNetwork :type="'logo-light'" />
          </div>
          <div class="footer-info">
            <div class="footer-info-product">
              <div class="footer-info__title">Продукты</div>
              <div class="footer-info-product__list">
                <NuxtLink
                  v-for="(item, i) in product"
                  :key="i" 
                  :to="item.url"
                >
                  {{ item.name }}
                </NuxtLink>
              </div>
            </div>
            <div class="footer-info__choice">
              <NuxtLink
                v-for="(item, i) in menu"
                :key="i" 
                :to="item.url"
                class="footer-info__title"
              >
                {{ item.name }}
              </NuxtLink>
            </div>
            <div class="footer-info__contact">
              <NuxtLink to="tel:+76667772211">+7 666 777 22 11</NuxtLink>
              <NuxtLink to="mailto:test@mail.ru">test@mail.ru</NuxtLink>
            </div>
          </div>
        </div>
        <div class="footer__bottom">
          <div class="footer__strip">
            <p>Политика конфиденциальности</p>
            <p>Разработка<TheSvg :type="'logo-light'" /></p>
          </div>

        </div>
      </div>
    </footer>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        isOpenMenu: false,
        isOpen: false,
        navList: [
          {
            name: 'Платформа',
            url: '#'
          },
          {
            name: 'Кейсы',
            url: '#'
          },
          {
            name: 'Партнерам',
            url: '#'
          },
          {
            name: 'Блог',
            url: '#'
          },
          {
            name: 'О компании',
            url: '#'
          },
          {
            name: 'Контакты',
            url: '#'
          }
        ],
        navSublist: [
          {
            title: 'Продажи на маркетплейсах',
            text: 'Автоматизация продаж на универсальных маркетплейсах',
            url: '#'
          },
          {
            title: 'Интернет-магазин',
            text: 'Автоматизация онлайн-продаж для вашего интернет-магазина',
            url: '#'
          },
          {
            title: 'Нишевые маркетплейсы',
            text: 'Управление собственным маркетплейсом',
            url: '#'
          },
          {
            title: 'Шина данных (ESB)',
            text: 'Управление обменом данных и интеграции',
            url: '#'
          },
        ],
        product: [
          {
            name: 'Продажи на маркетплейсах',
            url: '#'
          },
          {
            name: 'Интернет-магазин',
            url: '#'
          },
          {
            name: 'Нишевые маркетплейсы',
            url: '#'
          },
          {
            name: 'Шина данных',
            url: '#'
          },
          
        ],
        menu: [
          {
            name: 'Платформа',
            url: '#'
          },
          {
            name: 'Блог',
            url: '#'
          },
          {
            name: 'Кейсы',
            url: '#'
          },
          {
            name: 'О компании',
            url: '#'
          },
          {
            name: 'Партнерам',
            url: '#'
          },
          {
            name: 'Контакты',
            url: '#'
          },
          
        ]
      }
    },
    methods: {
		menuOpen() {
			if (!this.isOpenMenu) document.body.classList.add('menu-open')
			else document.body.classList.remove('menu-open')
			this.isOpenMenu = !this.isOpenMenu
		},
    openSubmenu() {
      this.isOpen = !this.isOpen
    }
	}
  }
</script>

<style lang="scss">
.header {
  height: 90px;
  line-height: 90px;
  background-color: var(--white);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 500;
  .overlay {
    display: none;
    &.is-open {
      display: block;
    }
  }
  &__inner {
    display: grid;
    grid-template-columns: 120px auto;
    align-items: center;
    justify-content: space-between;
  }
  &__info {
    display: flex;
    align-items: center;
  }
  &__info-block {
    p {
      font-weight: 700;
      line-height: 120%;
      margin-bottom: 20px;
      cursor: pointer;
      &.is-open {
        background: linear-gradient(137.70deg, rgb(57, 199, 236),rgb(57, 199, 236),rgb(0, 80, 236));
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        color: #0B2349;
        display: table;
      }
    }
    
  }
  &__logo {
    a {
      display: block;
    }
  }
}
.header-nav {
  &__list {
    display: flex;
    align-items: center;
  }
  &__sublist {
    display: block;
    border: solid 1px var(--border);
    background-color: var(--border);
    border-radius: 40px;
    padding: 40px;
    display: grid;
    align-items: flex-start;
    grid-template-columns: repeat(4, 1fr);
    position: absolute;
    width: 70vw;
    top: 100%;
    left: -10vw;
    gap: 20px;
    display: none;
    p {
      line-height: 120%;
      &:first-child {
        font-size: 16px;
        font-weight: 700;
        margin-bottom: 10px;
      }
      &:last-child {
        font-size: 16px;
        font-weight: 400;
        line-height: 140%;
      }
    }
    li {
      background-color: var(--white);
      height: 100%;
      border-radius: 20px;
      transition: 0.3s;
      a {
        display: block;
        height: 100%;
        padding: 20px;
      }
      &:hover {
        @media(min-width: 1023px) {
          color: var(--text);
          background-color: var(--blockHover);
          a {
            color: var(--text);
            p:first-child {
              background: linear-gradient(137.70deg, rgb(57, 199, 236),rgb(57, 199, 236),rgb(0, 80, 236));
              -webkit-background-clip: text;
              -webkit-text-fill-color: transparent;
              color: #0B2349;
              display: table;
            }
          }
        }
      }
    }
  }
  &__item {
    font-size: 16px;
    line-height: 120%;
    font-weight: 700;
    margin-right: 40px;
    color: var(--text);
    a {
      color: var(--text);
      transition: 0.3s;
      &:hover {
        @media(min-width: 1023px) {
          color: var(--darkBlue);
        }
      }
    }
  }
  &__item-p {
    position: relative;
    display: flex;
    align-items: center;
    font-size: 16px;
    line-height: 120%;
    font-weight: 700;
    margin-right: 40px;
    &:hover {
      @media(min-width: 1023px) {
        color: var(--darkBlue);
        .header-nav__sublist {
          display: grid;
        }
        &::after {
          transform: rotate(-135deg);
          margin-bottom: -0.3em;
        }
      }
    }
    &::after {
      content: '';
      display: block;
      width: 8px;
      height: 8px;
      border-right: solid 2px;
      border-bottom: solid 2px;transform: rotate(45deg);
      margin-left: 0.4em;
      transition: 0.3s;
    }
   
  }
  
}
.burger {
  display: none;
  width: 20px;
  height: 20px;
  position: relative;
  overflow: hidden;
  position: relative;
  cursor: pointer;
  @media(max-width: 1240px) {
    display: block;
    z-index: 10000;
  }
  span {
    &::after, &::before {
      content: '';
      display: block;
      background: linear-gradient(to right, #39C7EC, #0050EC);
      transition: 0.3s;
      width: 100%;
      height: 4px;
      position: absolute;
      top: 50%;
    }
    &:first-child {
        &::after, &::before {
          content: '';
          transform:  rotate(0);
        }
        &::after {
          width: 7px;
          height: 7px;
          top: 0;
          left: 0;
        }
        &::before {
          width: 7px;
          height: 7px;
          top: 0;
          right: 0;
        }
      }
      &:last-child {
        &::after, &::before {
          content: '';
          transform:  rotate(0);
        }
        &::after {
          width: 7px;
          height: 7px;
          bottom: 0;
          right: 0;
        }
        &::before {
          width: 7px;
          height: 7px;
          bottom: 0;
          left: 0;
        }
      }
  }
  &.is-open {
    width: 25px;
    height: 25px;
    span {
      &::after, &::before {
      content: '';
      display: block;
      transition: 0.3s;
      width: 100%;
      height: 4px;
      position: absolute;
      top: 50%;
    }
    &::after {
      left: 0;
      transform:  rotate(45deg);
    }
    &::before {
      right: 0;
      transform:  rotate(-45deg);
    }
    }
  }
}
.header-mobile {
  display: none;
  position: fixed;
  top: 0;
  bottom: 0;
  right: -400px;
  width: 100%;
  max-width: 400px;
  background-color: var(--white);
  transition: 0.3s;
  z-index: 999;
  @media(max-width: 1240px) {
    display: block;
  }
  &.is-open {
    right: 0;
  }
  .header-logo {
    padding: 10px 20px 0;
    a {
      display: block;
    }
  }
  &__menu {
    height: 100%;
    position: relative;
    z-index: 150;
  }
  .header__info {
    flex-direction: column;
    align-items: flex-start;
    padding: 0 20px 0;
  }
  .header-nav {
    margin-top: 20px;
    &__list {
      flex-wrap: wrap;
      align-items: flex-start;
      width: 100%;
    }
    &__item {
      margin-bottom: 1em;
      margin-right: 0;
      flex: 0 0 50%;
      max-width: 50%;
    }
  }
  .header-nav__sublist {
    width: 100%;
    top: auto;
    left: auto;
    position: relative;
    padding: 0;
    display: none;
    background-color: var(--white);
    border-radius: 0;
    border: none;
    &.is-open {
      display: block;
    }
    li a p:last-child {
      display: none;
    }
    li a {
      padding: 0;
      color: var(--text);
    }
    li {
      border-radius: 0;
      margin-bottom: 15px;
    }
  }
}
.header-desktop {
  @media(max-width: 1240px) {
    display: none;
  }
}

.footer {
  background-color: var(--darkBlue);
  padding-top: 110px;
  &__top {
    display: grid;
    grid-template-columns: 160px 1fr;
    gap: 100px;
    margin-bottom: 250px;
    @media(max-width: 1240px) {
      grid-template-columns: 1fr;
      gap: 40px;
      margin-bottom: 130px;
    }
  }
  &__bottom {
    border-top: solid 1px rgba(#fff, 0.5);
  }
  &__strip {
    display: flex;
    max-width: 50%;
    align-items: center;
    color: rgba(#fff, 0.5);
    justify-content: space-between;
    margin-left: auto;
    padding: 30px;
    font-size: 14px;
    @media(max-width: 1240px) {
      margin-left: 0;
      max-width: 100%;
      padding: 30px 0;
    }
    @media(max-width: 767px) {
      flex-wrap: wrap;
      padding: 50px 0;
      p {
        padding-bottom: 15px;
        &:last-child {
          padding-bottom: 0;
        }
      }
    } 
    svg {
      margin-bottom: -0.2em;
      margin-left: 0.3em;
    }
  }
}
.footer-info {
  display: grid;
  grid-template-columns: 0.8fr 1fr 1fr;
  gap: 10px;
  @media(max-width: 1240px) {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  &__title {
    color: var(--white);
    font-size: 26px;
    font-weight: 700;
  }
  &__choice {
    display: flex;
    flex-wrap: wrap;
    a {
      display: inline-block;
      margin-bottom: 30px;
      white-space: nowrap;
      flex: 0 0 50%;
      max-width: 50%;
      transition: 0.3s;
      &:hover {
        @media(min-width: 1023px) {
          color: var(--lightBlue);
        }
      }
      &:last-child{
        margin-bottom: 0;
      }
    }
  }
  &__contact {
    display: flex;
    flex-direction: column;
    a {
      display: inline-block;
      color: var(--white);
      transition: 0.3s;
      &:hover {
        @media(min-width: 1023px) {
          color: var(--lightBlue);
        }
      }
      &:first-child {
        font-weight: 700;
        font-size: 30px;
        margin-bottom: 40px;
      }
      &:last-child {
        font-size: 20px;
        font-weight: 400;
      }
    }
  }
}
.footer-info-product {
  &__list {
    display: flex;
    flex-direction: column;
    margin-top: 25px;
    a {
      color: var(--white);
      font-size: 18px;
      font-weight: 400;
      display: inline-block;
      margin-bottom: 25px;
      transition: 0.3s;
      &:hover {
        @media(min-width: 1023px) {
          color: var(--lightBlue);
        }
      }
      &:last-child {
        margin-bottom: 0;
      }
    }
  }
}

</style>