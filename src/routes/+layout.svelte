<script>
	import Header from '$lib/header/Header.svelte';
  import { webVitals } from '$lib/vitals';
  import { browser } from '$app/env';
  import { page } from '$app/stores';
  import '../app.css';

  let analyticsId = import.meta.env.VERCEL_ANALYTICS_ID;

  $: if (browser && analyticsId) {
    webVitals({
      path: $page.url.pathname,
      params: $page.params,
      analyticsId
    })
  }
</script>

<Header />

<main>
  <!-- POPUP -->
  <div class="auth">
    <div class="auth__close-wrapper" onclick="authToggle()">
      <div class="auth__close"></div>
    </div>
    <div class="auth__title">Войти</div>
    <form action="" class="auth__form">
      <div class="auth__form-title">Логин</div>
      <input type="email" placeholder="Введите">
      <div class="auth__form-title">Пароль</div>
      <input type="password" placeholder="Введите">
      <div class="auth__form-btns">
        <button type="submit">Войти</button>
        <a href="/" onclick="signupToggle()">Зарегистрироваться</a>
      </div>
    </form>
  </div>

  <div class="signup">
    <div class="signup__close-wrapper" onclick="signupToggle()">
      <div class="signup__close"></div>
    </div>
    <div class="signup__title">Регистрация</div>
    <form action="" class="signup__form">
      <div class="signup__form-title">Придумайте логин</div>
      <input type="email" placeholder="Введите">
      <div class="signup__form-title">Придумайте пароль</div>
      <input type="password" placeholder="Введите">
      <div class="signup__form-title">Повторите пароль</div>
      <input type="password" placeholder="Введите">
      <div class="signup__form-btns">
        <button type="submit">Зарегистрироваться</button>
      </div>
    </form>
  </div>

  <!-- WRAPPER -->
  <div class="wrapper">
    <div class="inside-wrapper">

      <!-- HEADER -->
      <header class="header">
        <div class="header__container">
          <div class="header__body">
            <div class="header__block">
              <div class="header__logo"></div>
              <div class="header__menu"></div>
            </div>
            <div class="header__block">
              <ul class="header__navigation">
                <li><a href="#main">Главная</a></li>
                <li><a href="#service">О сервисе</a></li>
                <li><a href="#directory">Справочник</a></li>
                <li><a href="#map">Карта</a></li>
                <li><a href="#rating">Рейтинг</a></li>
                <li><a href="#contact">Контакты</a></li>
              </ul>
            </div>
            <div class="header__block">
              <div class="header__switch" onclick="darkMode()">
                <div class="header__switch-el"></div>
              </div>
              <div class="header__profile-box" onclick="authToggle()">
                <div class="header__profile-icon"></div>
                <p>Кабинет</p>
              </div>
            </div>
          </div>
        </div>
      </header>

      <!-- MAIN -->
      <section class="main" id="main">
        <div class="main__container _container">
          <div class="main__body">
            <div class="main__block">
              <div class="main__title-wrap">
                <div class="main__title title">Вместе сделаем якутию - Надежной</div>
              </div>
              <div class="main__text-wrap">
                <div class="main__text text-2level">Открытая площадка с комментированием работы ИП</div>
              </div>
              <a href="/" class="main__btn">Узнать Больше <div class="main__btn-icon"></div></a>
              <div class="main__el-wrapper">
                <div class="main__el"></div>
                <div class="main__el"></div>
              </div>
            </div>
            <div class="main__block">
              <div class="main__slider swiper">
                <div class="main__slider-wrapper swiper-wrapper">

                  <div class="main__slide swiper-slide">
                    <div class="main__slide-title">Роман</div>
                    <div class="main__slide-text">Этот проект помогает улучшить многие сферы общего жития и всё такое
                    </div>
                  </div>

                  <div class="main__slide swiper-slide">
                    <div class="main__slide-title">Роман</div>
                    <div class="main__slide-text">Этот проект помогает улучшить многие сферы общего жития и всё такое
                    </div>
                  </div>

                  <div class="main__slide swiper-slide">
                    <div class="main__slide-title">Роман</div>
                    <div class="main__slide-text">Этот проект помогает улучшить многие сферы общего жития и всё такое
                    </div>
                  </div>

                </div>
                <div class="main__slider-pagination swiper-pagination"></div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- SERVICE -->
      <section class="service" id="service">
        <div class="service__container _container">
          <div class="service__body">
            <div class="service__block">
              <div class="service__subtitle sub-title">About us</div>
              <div class="service__title title">О сервисе</div>
              <div class="service__text text-1level">
                В настоящее время безналичные платежи нераздельно связаны с нашей жизнью, позволяет проводить оплату
                быстро и безопасно.
              </div>
              <div class="service__text text-1level">
                Однако некоторые предприниматели принимают оплату с помощью «мобильного банка», без фискализации
                операции, что может повлечь последствия.
              </div>
              <div class="service__box-wrapper">
                <div class="service__box">
                  <div class="service__num num">01</div>
                  <div class="service__text text-3level">
                    Для клиента – угроза вовлечения в мошеннические схемы,
                    Отсутствие чека - нет защиты прав потребителя, не участие в программах лояльности банков.
                  </div>
                </div>
                <div class="service__box">
                  <div class="service__num num">02</div>
                  <div class="service__text text-3level">
                    Для региона – отсутствие налоговых поступлений в бюджет. сокращение гос.бюджета
                  </div>
                </div>
              </div>
            </div>
            <div class="service__block">
              <div class="service__mask-bg">
                <div class="service__element"></div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="directory" id="directory">
        <div class="directory__container _container">
          <div class="directory__body">
            <div class="directory__head">
              <div class="directory__subtitle sub-title">Guide</div>
              <div class="directory__title title">Справочник</div>
            </div>
            <div class="directory__content">
              <div class="directory__wrapper">
                <div class="directory__block">
                  <div class="directory__heading">Бонусная система</div>
                  <div class="directory__text">У нас имеется бонусная система со скидками у партнеров до 20%. Как ими
                    воспользвоваться и накопить? Все просто отправляйте комментарии на ИП и копите бонусы, а уже в
                    личном кабинете потратитье их!</div>
                  <div class="directory__img"></div>
                </div>
                <div class="directory__block">
                  <div class="directory__heading">Рейтинговая система</div>
                  <div class="directory__text">В рейтинге вы можете увидеть свою позиции среди остальных пользователей и
                    посмотреть кто самый активный! Самый активный пользователь получает повышение до “модератора”!</div>
                  <div class="directory__img"></div>
                </div>
              </div>
              <div class="directory__wrapper">
                <div class="directory__block">
                  <div class="directory__img"></div>
                  <div class="directory__heading">Интерактивная карта</div>
                  <div class="directory__text">Вы можете увидеть на карте какие ИП принимают оплаты моб.банком или не
                    имеют кассы и все это происходит в реальном времени.</div>
                  <div class="directory__item-wrapper">
                    <div class="directory__item">
                      <div class="directory__item-icon"></div>
                      <div class="directory__item-text">- Отказано</div>
                    </div>
                    <div class="directory__item">
                      <div class="directory__item-icon"></div>
                      <div class="directory__item-text">- Ожидание</div>
                    </div>
                    <div class="directory__item">
                      <div class="directory__item-icon"></div>
                      <div class="directory__item-text">- Подтверждено</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
      </section>

      <div class="directory__footer">
        <div class="directory__footer-el"></div>
        <div class="directory__footer-el"></div>
      </div>

      <section class="map" id="mapsection">
        <div class="map__container _container">
          <div class="map__body">
            <div class="map__block">
              <div class="map__subtitle sub-title">Interactive map</div>
              <div class="map__title title">Интерактивная карта</div>
            </div>
            <div class="map__wrapper">
              <div id="map"></div>
            </div>
          </div>
        </div>
      </section>

      <section class="rating" id="rating">
        <div class="rating__container _container">
          <div class="rating__body">
            <div class="rating__block">
              <div class="rating__subtitle sub-title">Rating of participants</div>
              <div class="rating__title title">Рейтинг участников</div>
            </div>
            <div class="rating__block">
              <div class="rating__box">

                <div class="rating__item">
                  <div class="rating__item-block">
                    <div class="rating__item-logo"></div>
                    <div class="rating__item-user">
                      <div class="rating__item-user-title">Anonimus_12</div>
                      <div class="rating__item-user-subtitle">1 место</div>
                    </div>
                  </div>
                  <div class="rating__item-submit">42 одобренных заявок</div>
                  <div class="rating__item-score">390 баллов</div>
                  <div class="rating__item-rate">Рейтинг №1</div>
                </div>
                <div class="rating__item">
                  <div class="rating__item-block">
                    <div class="rating__item-logo"></div>
                    <div class="rating__item-user">
                      <div class="rating__item-user-title">Destroyer</div>
                      <div class="rating__item-user-subtitle">2 место</div>
                    </div>
                  </div>
                  <div class="rating__item-submit">42 одобренных заявок</div>
                  <div class="rating__item-score">390 баллов</div>
                  <div class="rating__item-rate">Рейтинг №2</div>
                </div>
                <div class="rating__item">
                  <div class="rating__item-block">
                    <div class="rating__item-logo"></div>
                    <div class="rating__item-user">
                      <div class="rating__item-user-title">Eva1</div>
                      <div class="rating__item-user-subtitle">3 место</div>
                    </div>
                  </div>
                  <div class="rating__item-submit">42 одобренных заявок</div>
                  <div class="rating__item-score">390 баллов</div>
                  <div class="rating__item-rate">Рейтинг №3</div>
                </div>
                <div class="rating__item">
                  <div class="rating__item-block">
                    <div class="rating__item-logo"></div>
                    <div class="rating__item-user">
                      <div class="rating__item-user-title">Anonimus_103</div>
                      <div class="rating__item-user-subtitle">4 место</div>
                    </div>
                  </div>
                  <div class="rating__item-submit">42 одобренных заявок</div>
                  <div class="rating__item-score">390 баллов</div>
                  <div class="rating__item-rate">Рейтинг №4</div>
                </div>
                <div class="rating__item">
                  <div class="rating__item-block">
                    <div class="rating__item-logo"></div>
                    <div class="rating__item-user">
                      <div class="rating__item-user-title">Becon99</div>
                      <div class="rating__item-user-subtitle">5 место</div>
                    </div>
                  </div>
                  <div class="rating__item-submit">42 одобренных заявок</div>
                  <div class="rating__item-score">390 баллов</div>
                  <div class="rating__item-rate">Рейтинг №5</div>
                </div>
                <div class="rating__item">
                  <div class="rating__item-block">
                    <div class="rating__item-logo"></div>
                    <div class="rating__item-user">
                      <div class="rating__item-user-title">Anonimus_9</div>
                      <div class="rating__item-user-subtitle">6 место</div>
                    </div>
                  </div>
                  <div class="rating__item-submit">42 одобренных заявок</div>
                  <div class="rating__item-score">390 баллов</div>
                  <div class="rating__item-rate">Рейтинг №6</div>
                </div>

                <div class="rating__item-btn" onclick="authToggle()">Посмотреть весь рейтинг <div
                    class="rating__item-btn-icon"></div>
                </div>

              </div>
            </div>
          </div>
        </div>
      </section>

      <div class="rating__footer">
        <div class="rating__footer-el"></div>
        <div class="rating__footer-el"></div>
      </div>

      <section class="contact" id="contact">
        <div class="contact__container _container">
          <div class="contact__body">
            <div class="contact__block">
              <div class="contact__subtitle sub-title">Contacts</div>
              <div class="contact__title title">Контакты</div>
              <div class="contact__head">Номер</div>
              <div class="contact__text">+79841084114</div>
              <div class="contact__head">Адрес</div>
              <div class="contact__text">Проспект Ленина 1</div>
              <div class="contact__head">Почта</div>
              <div class="contact__text">qwertuipp15@gmail.com</div>
            </div>
            <div class="contact__block">
            </div>
          </div>
        </div>
      </section>

    </div>
  </div>
  <div class="footer__back"></div>
  <footer class="footer" id="footer">

    <div class="footer__container _container">
      <div class="footer__body">
        <div class="footer__block">
          <ul class="footer__navigaion">
            <li><a href="#main">Главная</a></li>
            <li><a href="#service">О сервисе</a></li>
            <li><a href="#directory">Справочник</a></li>
            <li><a href="#map">Карта</a></li>
            <li><a href="#rating">Рейтинг</a></li>
            <li><a href="#contact">Контакты</a></li>
          </ul>
        </div>
        <div class="footer__block">
          <div class="footer__text">© 2022 yanadzor</div>
          <div class="footer__text">Политика конфиденциальности</div>
          <div class="footer__text">Разработка - RPS</div>
        </div>
      </div>
    </div>
  </footer>
</main>
