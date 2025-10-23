<template>
  <div class="container">
    <div class="header-section">
      <h1 class="title">О нас</h1>
      <div class="divider"></div>
    </div>

    <div class="about-content">
      <div class="about-main">
        <p class="about-intro">
          Магазин <span class="color">«Мишень»</span> был создан для тех, кто ценит в экипировке не
          только имя, но и <span class="color">идеальное соответствие своим задачам</span>.
        </p>

        <div class="mission-section">
          <h2 class="subtitle">Наша философия</h2>
          <p class="about-text">
            Мы понимаем, что от правильного выбора зависит ваша безопасность, комфорт и, в конечном
            счете, <span class="color">результат на льду</span>. Поэтому наш ассортимент — это
            кропотливо подобранная коллекция лучших брендов и моделей для всех уровней подготовки.
          </p>
        </div>

        <div class="team-section">
          <h2 class="subtitle">Экспертный подход</h2>
          <p class="about-text">
            Наши консультанты прошли строгий отбор: они не только продавцы, но и
            <span class="color">бывшие игроки, тренеры, настоящие эксперты инвентаря</span>. Они
            помогут подобрать снаряжение, которое сядет по фигуре как влитое, и дадут
            профессиональный совет по уходу за ним.
          </p>
        </div>

        <div class="solutions-section">
          <h2 class="subtitle">Решение для каждого хоккеиста</h2>
          <p class="about-text">
            Мы гордимся тем, что можем предложить
            <span class="color">решение для каждой хоккейной задачи</span>: от экипировки юниора до
            формы для ветерана любительской лиги, от любительского снаряжения до профессиональной
            экипировки.
          </p>
        </div>

        <div class="advantages-grid">
          <div class="advantage-card">
            <h3 class="advantage-title">Быстрая доставка</h3>
            <p>Наша логистика отлажена так, чтобы вы получали свой заказ максимально быстро</p>
          </div>
          <div class="advantage-card">
            <h3 class="advantage-title">Программа лояльности</h3>
            <p>Система скидок и бонусов делает покупки выгодными для постоянных клиентов</p>
          </div>
          <div class="advantage-card">
            <h3 class="advantage-title">Поддержка 24/7</h3>
            <p>Мы всегда на связи, чтобы обеспечить вам полную поддержку по всем вопросам</p>
          </div>
        </div>

        <div class="final-section">
          <p class="about-text final-text">
            Мы не просто продаем экипировку — мы помогаем хоккеистам достигать своих целей.
            <span class="color">Ваш успех — это наша «Мишень».</span>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
.container {
  margin: 5rem 10%;
  text-align: center;
}

.header-section {
  margin-bottom: 3rem;
}

.title {
  font-size: 3.5rem;
  margin-bottom: 1rem;
  color: var(--primary-color);
}

.divider {
  width: 100px;
  height: 4px;
  background: var(--primary-color);
  margin: 0 auto;
  border-radius: 2px;
}

.about-content {
  /* max-width: 1200px; */
  margin: 0 auto;
}

.about-main {
  text-align: left;
}

.about-intro {
  font-size: 1.5rem;
  line-height: 1.6;
  margin-bottom: 2.5rem;
  text-align: center;
  font-weight: 500;
}

.subtitle {
  font-size: 2rem;
  color: var(--primary-color);
  margin: 2.5rem 0 1.5rem 0;
  text-align: center;
}

.about-text {
  font-size: 1.2rem;
  line-height: 1.8;
  margin-bottom: 1.5rem;
  text-align: justify;
}

.mission-section,
.team-section,
.solutions-section {
  margin-bottom: 2rem;
  padding: 2rem;
  background: rgba(0, 0, 0, 0.02);
  border-radius: 12px;
  border-left: 4px solid var(--primary-color);
}

.advantages-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin: 3rem 0;
}

.advantage-card {
  padding: 2rem;
  background: white;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.advantage-card:hover {
  transform: translateY(-5px);
}

.advantage-title {
  font-size: 1.4rem;
  color: var(--primary-color);
  margin-bottom: 1rem;
  font-weight: 600;
}

.final-section {
  margin-top: 3rem;
  padding: 2rem;
  background: linear-gradient(135deg, var(--primary-color) 0%, #2c5282 100%);
  border-radius: 12px;
  text-align: center;
}

.final-text {
  color: white;
  font-size: 1.3rem;
  font-weight: 500;
  margin: 0;
  text-align: center;
}

.final-text .color {
  color: #ffd700;
  font-weight: 600;
}

.color {
  color: var(--primary-color);
  font-weight: 600;
}

@media (max-width: 768px) {
  .container {
    margin: 3rem 5%;
  }

  .title {
    font-size: 2.5rem;
  }

  .about-intro {
    font-size: 1.3rem;
  }

  .advantages-grid {
    grid-template-columns: 1fr;
  }

  .mission-section,
  .team-section,
  .solutions-section {
    padding: 1.5rem;
  }
}

@media (max-width: 700px) {
  .title {
    font-size: 1.5rem;
  }
  .about-intro {
    font-size: 1rem;
  }
  .subtitle {
    font-size: 1.2rem;
  }
  .about-text {
    font-size: 1rem;
  }
}
</style>
