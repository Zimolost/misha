<template>
  <section class="subscribe">
    <div class="subscribe-text">
      <p class="subscribe-title">Подпишитесь на нашу</p>
      <p class="subscribe-title">рассылку</p>
      <p class="subscribe-info">
        Первыми узнавайте о новых поступлениях хоккейной экипировки, специальных акциях и
        эксклюзивных скидках. Получайте советы по выбору снаряжения, новости о хоккейных событиях и
        уведомления о старте распродаж коллекций ведущих брендов.
      </p>
    </div>
    <div class="subscribe-form">
      <p class="form-title">Будьте в курсе событий</p>
      <div class="form-group">
        <input class="input" type="email" placeholder="Введите вашу почту" />
        <button class="btn">Подписаться</button>
      </div>
      <p class="confirm-text">
        Подписываясь, вы соглашаетесь с нашей
        <span class="policy">Политикой конфиденциальности</span>
      </p>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.subscribe {
  margin: 6rem 10%;
  display: flex;
  padding: 4rem 3rem;
  border-radius: 2rem;
  gap: 6rem;
  background: linear-gradient(135deg, #1b5696 0%, var(--primary-color) 100%);
  color: white;
}

.subscribe-title {
  font-size: 2.5rem;
  font-weight: 600;
}

.subscribe-text {
  display: flex;
  flex-direction: column;
  width: 50%;
}

.subscribe-form {
  display: flex;
  flex-direction: column;
  width: 50%;
  justify-content: center;
  /* align-items: center; */
  gap: 1rem;
}

.input {
  border-radius: 3rem;
  height: 3.5rem;
  min-width: 20rem;
  border: 1px solid #c3e9a01a;
  padding-left: 1.5rem;
  background: #c3e9a01a;
  font-size: 1.1rem;
}

.input::placeholder {
  color: #ffffff;
}

.subscribe-info {
  margin-top: 2rem;
}

.form-group {
  display: flex;
  gap: 1rem;
}

.btn {
  border-radius: 3rem;
  border: 1px solid rgb(196, 196, 196);
  padding: 0.5rem 1.5rem;
  font-size: 1.1rem;
  background: var(--secondary-color);
  color: var(--primary-color);
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn:hover {
  color: rgb(255, 255, 255);
  background: var(--primary-color);
}

.confirm-text {
  font-size: 0.8rem;
  margin-right: auto;
  color: rgb(255, 255, 255, 0.9);
}

.policy {
  text-decoration: underline;
}

@media (max-width: 1200px) {
  .subscribe {
    flex-direction: column;
    gap: 1rem;
  }
  .subscribe-text {
    width: 100%;
    flex: 1;
  }
  .subscribe-form {
    width: 100%;
    flex: 1;
  }

  .form-group {
    width: 100%;
    flex: 1;
  }

  input {
    width: 100%;
  }
}

@media (max-width: 800px) {
  .form-group {
    flex-direction: column;
  }
}

@media (max-width: 600px) {
  .subscribe-title {
    font-size: 2rem;
  }
  .subscribe-text {
    font-size: 0.8rem;
  }

  .input {
    min-width: 0;
  }
}

@media (max-width: 500px) {
  .subscribe-title {
    font-size: 1.5rem;
  }
  .input {
    font-size: 1rem;
  }
}
</style>
