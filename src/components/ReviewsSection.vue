<template>
  <div class="preview-wrap">
    <header class="preview-header">
      <div class="preview-top">
        <h2 class="section-title">Счастливые клиента</h2>
        <p>Ваши впечатления — наша гордость</p>
      </div>
    </header>

    <div class="preview-shell">
      <div class="carousel-viewport">
        <div class="cards">
          <!-- === REAL CARDS === -->
          <div
            class="card"
            v-for="(idx, i) in reviews"
            :key="i"
            :class="{ 'current--card': i === activeIndex }"
            @click="onCardClick(i)"
            :ref="(el) => (cardEls[i] = el)"
          >
            <div class="card__meta">
              <div class="card__top">
                <div class="stars">
                  <img src="@/img/star-y.png" alt="star" v-for="n in 5" :key="n" class="star" />
                </div>
                <p class="date">20.10.2025</p>
              </div>

              <div class="card__image">
                <img src="@/img/woman.png" alt="" class="author-img" />
                <h3 class="title">Александрова Анастасия</h3>
              </div>
              <p class="description">{{ desc[i] }}</p>
            </div>
          </div>
          <!-- end cards -->
        </div>
      </div>
    </div>

    <div class="controls">
      <button @click="rotateLeft" aria-label="Prev">
        <img src="@/img/arrow-left.png" alt="" class="btn-image" />
      </button>

      <div class="indicators">
        <div class="indicator" v-for="(pos, i) in reviews" :key="i" @click="activeIndex = i">
          <img
            :src="activeIndex === i ? activeDot : dot"
            alt=""
            class="indicator-img"
            :class="{ active: activeIndex === i }"
          />
        </div>
      </div>

      <button @click="rotateRight" aria-label="Next">
        <img src="@/img/arrow-right.png" alt="" class="btn-image" />
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import activeDot from '@/img/activeDot.png'
import dot from '@/img/dot.png'

const desc = [
  'Ребенок растет как на дрожжах, экипировка за сезон становится мала, а форма изнашивается до дыр. "Мишень" для нас стал настоящей находкой. Но главное даже не сам магазин (ассортимент отличный, цены адекватные), а их сервис! Их заточка коньков — это отдельная магия! Сын после их работы буквально "летает" по льду и не нарадуется на цепкость поворотов. Спасибо команде "Мишени" за то, что делают наш хоккей доступнее и качественнее!',
  'Пользуюсь одними и теми же крагами лет 10, родные уже, как брат. Недавно порвался шов, да и пластиковая манжета треснула. Всюду говорили: "Выброси, купи новые". Зашел в "Мишень" от безысходности. Каково же было мое удивление, когда мастер не только не отговорил меня от ремонта, а с энтузиазмом взялся за работу! Он не просто зашил дырку, а заменил манжету на новую, подобрал максимально схожую по жесткости, и теперь мои ветераны стали даже лучше, чем были.  Однозначно рекомендую!',
  'Ребята, кто еще сомневается — не надо. Я перепробовал кучу мест, пока не нашел "Мишень". Их заточка — это не просто наточить лезвия, это именно что тонкая настройка под тебя. Мастер задал пару вопросов про мой стиль катания, посмотрел на конек и предложил вариант. Разница ощущается с первых же секунд на льду: невероятная устойчивость и мощное толчковое ребро. Теперь только к ним. И атмосфера в магазине крутая, все свои, пахнет хоккеем и победой!',
  'Много лет в хоккее, и я привык доверять не вывеске, а людям. В "Мишени" я нашел именно таких специалистов. Подход к делу у них фундаментальный. Принес клюшку на замену крюка — не просто поменяли, а проконсультировали по углам и геометрии, подобрали оптимальный для моего хвата и роли. А уж про ремонт экипировки и говорить нечего: штопают так, что порой место ремонта становится крепче оригинала. Для тех, кто ценит качество, а не показуху — это ваше место.',
  'С двумя сыновьями-хоккеистами мой мир — это бесконечные тренировки, сборы и починка снаряжения. "Мишень" стал для нас палочкой-выручалочкой. Мы приезжаем сюда, и пока один ребенок выбирает себе новые щитки, второй сдает коньки на заточку. Параллельно я отдаю на ремонт наколенник, на котором оторвался ремешок. И все это — в одном месте, за один визит! Никакой беготни по городу. Персонал очень внимательный, помогает подобрать размер, всегда подскажут. Огромная экономия времени и нервов для хоккейной семьи',
]

const reviews = ref(desc.map((_, i) => i))

const activeIndex = ref(2) // можно поставить 0
const cardEls = ref([])

function rotateRight() {
  if (!reviews.value.length) return
  activeIndex.value = (activeIndex.value + 1) % reviews.value.length
}
function rotateLeft() {
  if (!reviews.value.length) return
  activeIndex.value = (activeIndex.value - 1 + reviews.value.length) % reviews.value.length
}
function onCardClick(i) {
  activeIndex.value = i
}
</script>

<style scoped>
.preview-wrap {
  display: flex;
  flex-direction: column;
  width: 100%;
  overflow: hidden;
  margin-bottom: 3rem;
  margin-top: 4rem;
}
.section-title {
  font-size: 9rem;
  color: var(--primary-color);
}
.preview-shell {
  background: #f7f8fa;
  /* padding: 18px; */
}
.preview-header {
  display: flex;
  margin: auto;
  /* margin-left: 8rem; */
  margin-bottom: 12px;
}
.preview-top {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  /* margin-right: 100%; */
}
.preview-header h2 {
  font-size: 2.2rem;
  /* margin: auto; */
  margin-bottom: 0.4rem;
}
.controls {
  display: flex;
  gap: 1rem;
  margin: auto;
  align-items: center;
}
.controls button {
  background: var(--primary-color);
  border: none;
  padding: 0.8rem 0.8rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.3s ease;
  border: 2px solid var(--primary-color);
}
.btn-image {
  object-fit: cover;
  height: 1.2rem;
  filter: invert(100%);
  transition: all 0.3s ease;
}

.controls button:hover {
  background: white;
  border: 2px solid var(--primary-color);
}

.controls button:hover .btn-image {
  filter: invert(0);
}

.carousel-viewport {
  overflow: hidden;
  padding: 12px 0;
}
.cards {
  display: flex;
  align-items: center;
  justify-content: center;
}

/* CARD */
.card {
  height: 100%;
  width: 310px;
  min-height: 510px;
  background: linear-gradient(135deg, #ffffff 5%, #ededed 100%);
  overflow: hidden;
  cursor: pointer;
  padding: 1.5rem;
  transition:
    transform 0.28s ease,
    opacity 0.28s ease;
  display: flex;
  flex-direction: column;
  opacity: 0.87;
  filter: brightness(90%);
  transform: scale(0.8);
}

.current--card {
  transform: translateY(-6px) scale(1.01);
  opacity: 1;
  border: 1px solid rgb(223, 223, 223);
  filter: brightness(100%);
}

.card__image {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-top: auto;
}
.author-img {
  height: 4.8rem;
  width: 4.8rem;
  object-fit: cover;
}
.card__top {
  display: flex;
  gap: 2rem;
  justify-content: space-between;
}
.stars {
  margin-bottom: 8px;
}
.star {
  object-fit: contain;
  height: 1rem;
  margin-right: 6px;
}
.card__meta {
  display: flex;
  flex-direction: column;
  height: 100%;
  flex: 1 1 auto;
  justify-content: space-between;
  /* gap: 3rem; */
}

.card.skeleton {
  background: #ffffff;
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  gap: 12px;
  align-items: stretch;
  justify-content: flex-start;
  opacity: 1;
  transform: scale(1);
}

.sk-img {
  width: 100%;
  height: 350px;
  background: linear-gradient(90deg, #eee 0%, #f5f5f5 50%, #eee 100%);
  background-size: 200% 100%;
  animation: shimmer 1.2s linear infinite;
  margin-bottom: 1rem;
}

.sk-line {
  height: 12px;
  margin-bottom: 0.5rem;
  border-radius: 6px;
  background: #eee;
}
.sk-round {
  height: 4rem;
  width: 4rem;
  border-radius: 50%;
  background: #eee;
}
.sk-line.short {
  width: 60%;
  height: 1.5rem;
}

/* shimmer animation */
@keyframes shimmer {
  0% {
    background-position: -200% 0;
  }
  100% {
    background-position: 200% 0;
  }
}

.indicators {
  display: flex;
  gap: 1rem;
  align-items: center;
}
.indicator-img {
  object-fit: contain;
  height: 0.8rem;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
.indicator-img.active {
  height: 1.2rem;
}

.description {
  margin-top: 1rem;
}

@media (max-width: 1300px) {
  .description {
    font-size: 0.8rem;
  }
}

@media (max-width: 1200px) {
  .description {
    font-size: 0.7rem;
  }
  .title {
    font-size: 0.8rem;
  }
  .card {
    min-height: 200px;
    max-height: 500px;
  }
  .author-img {
    width: 4rem;
    height: 4rem;
  }
  .star {
    height: 0.7rem;
  }
  .date {
    font-size: 0.8rem;
  }
}

/* Мобильные устройства (портрет) */
@media (max-width: 900px) {
  .card:nth-child(1),
  .card:nth-child(5) {
    display: none !important;
  }

  .indicators:nth-child(1),
  .indicators:nth-child(5) {
    display: none !important;
  }
  /* ... другие стили ... */
} /* Мобильные устройства (портрет) */
@media (max-width: 580px) {
  .card:nth-child(2),
  .card:nth-child(4) {
    display: none !important;
  }

  /* Остальные стили для мобильной версии */
  /* ... другие стили ... */
}

@media (max-width: 700px) {
  .section-title {
    font-size: 1.5rem;
  }

  .preview-header h2 {
    font-size: 1.5rem;
  }
}
</style>
