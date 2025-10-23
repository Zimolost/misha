<template>
  <footer class="site-footer" role="contentinfo" id="contacts">
    <div class="footer-inner">
      <!-- Блок с логотипом и контактами -->
      <div class="footer-col footer-brand">
        <a class="brand" href="/" aria-label="Главная страница Мишень">
          <div class="brand-mark" aria-hidden="true">
            <img src="../img/logo2.png" alt="логотип Мишень" class="logo" />
          </div>
          <p class="muted small">
            «Мишень» — это больше чем магазин, это концепция точного выбора и уверенности.
          </p>
        </a>

        <div class="contact-compact">
          <a class="contact-link" href="tel:+79529588754">+8 952 958 87 54</a>
          <a class="contact-link" href="mailto:mishen21@yandex.ru">mishen21@yandex.ru</a>
        </div>

        <div class="social-row">
          <a href="https://t.me/kmsunl11" class="social-link" aria-label="Телеграм">
            <span class="icon icon-telegram">
              <img src="../img/telegram.png" alt="телеграм" class="icon-img" />
            </span>
          </a>
          <a href="https://m.vk.com/kondratevmisha" class="social-link" aria-label="ВКонтакте">
            <span class="icon icon-twitter">
              <img src="../img/vk.png" alt="вконтакте" class="icon-img" />
            </span>
          </a>
        </div>
      </div>

      <!-- Навигационные ссылки -->
      <nav class="footer-col footer-links" aria-label="Навигация в подвале">
        <div class="links-group">
          <h4 class="links-title">Магазин</h4>
          <ul>
            <li><a href="#">Все товары</a></li>
            <li><a href="#">Новинки</a></li>
            <li><a href="#">Популярное</a></li>
            <li><a href="#">Распродажа</a></li>
          </ul>
        </div>

        <div class="links-group">
          <h4 class="links-title">Компания</h4>
          <ul>
            <li><a href="#">О нас</a></li>
            <li><a href="#">Вакансии</a></li>
            <li><a href="#">Пресса</a></li>
            <li><a href="#">Устойчивое развитие</a></li>
          </ul>
        </div>
      </nav>

      <!-- Контактная информация -->
      <div class="footer-col footer-contact" aria-labelledby="contact-heading">
        <h3 id="contact-heading" class="footer-title">Контакты</h3>
        <address class="contact-info">
          <div>
            Чувашская Республика - Чувашия, г.о. город Чебоксары, г Чебоксары Московский проспект,
            38к4, этаж 1, офис 105
          </div>
          <div><a href="tel:+79529588754">+8 952 958 87 54</a></div>
          <div><a href="mailto:mishen21@yandex.ru">mishen21@yandex.ru</a></div>
        </address>

        <div class="store-hours">
          <strong>Часы работы:</strong>
          <div>Пн — Пт: 9:00 — 18:00</div>
          <div>Сб — Вс: 10:00 — 16:00</div>
        </div>
      </div>
    </div>

    <div class="footer-bottom">
      <p class="copyright">© {{ year }} Мишень. Все права защищены.</p>
      <ul class="bottom-links" aria-label="Юридическая информация">
        <li><a href="#">Условия</a></li>
        <li><a href="#">Конфиденциальность</a></li>
        <li><a href="#">Политика cookies</a></li>
      </ul>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
const year = ref(new Date().getFullYear())
</script>

<style scoped>
/* Базовые стили */
.site-footer {
  background: #071212;
  background: linear-gradient(135deg, #132424 0%, #071212 100%);
  color: #fff;
  padding: 48px 0 24px;
  border-top: 1px solid rgba(255, 255, 255, 0.03);
}

.footer-inner {
  margin: 0 10%;
  display: grid;
  grid-template-columns: 1fr 1.3fr 1fr;
  gap: 2rem;
  align-items: start;
  padding: 0 1rem;
}

.footer-col {
  padding: 0.25rem 0;
}

/* Стили для бренда */
.brand {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 0.75rem;
  text-decoration: none;
  color: inherit;
}

.brand-mark {
  width: 30%;
  height: 30%;
  padding: 0.5rem;
  background: white;
  border-radius: 50%;
  box-shadow: 0 6px 18px rgba(12, 66, 66, 0.08);
}

.logo {
  object-fit: contain;
  width: 100%;
  height: 100%;
}

.muted {
  color: rgba(255, 255, 255, 0.82);
  margin-top: 0.5rem;
  font-size: 0.95rem;
  line-height: 1.5;
}

.contact-compact {
  margin-top: 0.7rem;
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.contact-link {
  color: rgba(255, 255, 255, 0.9);
  text-decoration: none;
  font-weight: 600;
}

.contact-link:hover {
  color: var(--secondary-color);
}

/* Социальные иконки */
.social-row {
  display: flex;
  gap: 0.5rem;
  margin-top: 0.9rem;
  align-items: center;
}

.social-link {
  width: 36px;
  height: 36px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.03);
  color: #fff;
  text-decoration: none;
  transition:
    background 0.15s ease,
    transform 0.12s ease;
}

.social-link:hover {
  background: var(--secondary-color);
  color: var(--primary-color);
  transform: translateY(-3px);
}

.social-link:hover .icon-img {
  filter: invert(0);
}

.icon {
  width: 2rem;
  height: 2rem;
  display: inline-block;
  background: rgba(255, 255, 255, 0.12);
  border-radius: 3px;
}

.icon-img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  filter: invert(100%);
}

/* Навигационные ссылки */
.footer-links {
  display: flex;
  justify-content: center;
  gap: 1.25rem;
}

.links-group {
  min-width: 0;
}

.links-title {
  color: rgba(255, 255, 255, 0.95);
  margin-bottom: 0.5rem;
  font-weight: 700;
  font-size: 0.96rem;
}

.links-group ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: grid;
  gap: 0.45rem;
}

.links-group a {
  color: rgba(255, 255, 255, 0.86);
  text-decoration: none;
  font-size: 0.95rem;
}

.links-group a:hover {
  color: var(--secondary-color);
  text-decoration: underline;
}

/* Контактная информация */
.footer-title {
  font-size: 1.05rem;
  margin: 0 0 0.5rem 0;
  font-weight: 700;
}

.contact-info {
  display: flex;
  flex-direction: column;
  font-style: normal;
  color: rgba(255, 255, 255, 0.9);
  line-height: 1.4;
  margin-bottom: 0.8rem;
}

.contact-info a {
  color: rgba(255, 255, 255, 0.9);
  text-decoration: none;
}

.contact-info a:hover {
  color: var(--secondary-color);
}

.store-hours {
  line-height: 1.5;
}

/* Нижняя часть футера */
.footer-bottom {
  margin-top: 28px;
  border-top: 1px solid rgba(255, 255, 255, 0.03);
  padding: 16px 1.25rem 28px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1200px;
  margin-left: auto;
  margin-right: auto;
}

.bottom-links {
  list-style: none;
  display: flex;
  gap: 1rem;
  margin: 0;
  padding: 0;
}

.bottom-links a {
  color: rgba(255, 255, 255, 0.75);
  font-size: 0.92rem;
  text-decoration: none;
}

.bottom-links a:hover {
  color: var(--secondary-color);
}

/* Адаптивность для планшетов (1024px и меньше) */
@media (max-width: 1024px) {
  .footer-inner {
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto auto;
    gap: 2rem;
  }

  .footer-brand {
    grid-column: 1 / 3;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: flex-start;
    gap: 2rem;
  }

  .brand {
    flex: 1;
  }

  .contact-compact {
    margin-top: 0;
  }

  .social-row {
    margin-top: 0;
  }
}

/* Адаптивность для планшетов среднего размера (768px и меньше) */
@media (max-width: 768px) {
  .footer-inner {
    margin: 0 5%;
    grid-template-columns: 1fr;
    gap: 2.5rem;
  }

  .footer-brand {
    grid-column: 1;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 1.5rem;
  }

  .brand-mark {
    width: 25%;
    height: 25%;
    margin: auto;
  }

  .footer-links {
    flex-direction: column;
    gap: 1.5rem;
    text-align: center;
  }

  .footer-contact {
    text-align: center;
  }

  .footer-bottom {
    flex-direction: column;
    gap: 1rem;
    text-align: center;
    padding: 16px 1rem 28px;
  }

  .bottom-links {
    justify-content: center;
    flex-wrap: wrap;
  }
}

/* Адаптивность для мобильных устройств (480px и меньше) */
@media (max-width: 480px) {
  .site-footer {
    padding: 32px 0 16px;
  }

  .footer-inner {
    margin: 0 1rem;
    padding: 0;
    gap: 2rem;
  }

  /* .brand-mark {
    width: 8rem;
    height: 4rem;
  } */

  .contact-compact {
    align-items: center;
  }

  .footer-links {
    gap: 1.25rem;
  }

  .links-group ul {
    gap: 0.35rem;
  }

  .footer-bottom {
    padding: 16px 0.5rem 20px;
  }

  .bottom-links {
    gap: 0.75rem;
  }

  .bottom-links a {
    font-size: 0.85rem;
  }
}

/* Улучшенная адаптивность для очень маленьких экранов (360px и меньше) */
@media (max-width: 360px) {
  .footer-inner {
    margin: 0 0.5rem;
  }

  .social-link {
    width: 32px;
    height: 32px;
  }

  .icon {
    width: 1.75rem;
    height: 1.75rem;
  }

  .footer-bottom {
    padding: 12px 0.25rem 16px;
  }

  .bottom-links {
    flex-direction: column;
    gap: 0.5rem;
  }
}
</style>
