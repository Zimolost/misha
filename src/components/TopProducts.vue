<template>
  <section id="products" class="products-section">
    <div class="section__top">
      <h2 class="section-title">Наши лучше товары</h2>
      <div class="controls">
        <nav class="tabs">
          <button class="tab-btn" role="tab">Последние</button>
          <button class="tab-btn" role="tab">Лучшие</button>
        </nav>
      </div>
      <button class="all-btn" @click="toProducts">
        Все товары
        <span class="arrow-img mask-arrow" aria-hidden="true"></span>
      </button>
    </div>
    <div class="line"></div>
    <div class="products">
      <article class="card" v-for="p in 12" :key="p.id">
        <div class="img-wrap">
          <img :src="imgs[p - 1]" alt="img" class="product-img" />
        </div>
        <div class="meta">
          <h3 class="title">{{ productNames[p - 1] }}</h3>
          <div class="meta-top">
            <div class="stars">
              <img src="../img/star-y.png" alt="" class="star-img" v-for="n in 4" :key="n" />
              <img src="../img/star-g.png" alt="" class="star-img" v-for="m in 5 - 4" :key="m" />
            </div>
            <span class="reviews">(12 отзывов)</span>
          </div>
          <div class="price">
            <p class="product-price">₽ {{ prices[p - 1] }}</p>
          </div>
        </div>
      </article>
    </div>

    <button id="about" class="products__link" @click="toProducts">Больше товаров...</button>
  </section>
</template>

<script setup>
import p1 from '../img/p1.png'
import p2 from '../img/p2.png'
import p3 from '../img/p3.png'
import p4 from '../img/p4.png'
import p5 from '../img/p5.png'
import p6 from '../img/p6.png'
import p7 from '../img/p7.png'
import p8 from '../img/p8.png'
import p9 from '../img/p9.png'
import p10 from '../img/p10.png'
import p11 from '../img/p11.png'
import p12 from '../img/p12.png'

const imgs = [p1, p2, p3, p4, p5, p6, p7, p8, p9, p10, p11, p12]

const prices = [25000, 22000, 17000, 26000, 23000, 15000, 3000, 35000, 36000, 20000, 12000, 700]

const productNames = [
  'Шлем',
  'Нагрудник',
  'Налокотники',
  'Краги',
  'Шорты',
  'Наколенники',
  'Гамаши',
  'Коньки',
  'Клюшка',
  'Термобельё',
  'Хоккейный баул',
  'Капа',
]
</script>

<style scoped>
.controls {
  display: flex;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  align-items: center;
  gap: 16px;
}

.section__top {
  display: flex;
  align-items: center;
  position: relative;
}

.tabs {
  display: flex;
  gap: 16px;
  font-size: 0.85rem;
}

.tab-btn {
  background: none;
  border: none;
  padding: 6px 8px;
  cursor: pointer;
  font-weight: 600;
  text-transform: uppercase;
  color: #808080;
}

.tab-btn.active {
  color: var(--primary-color);
  border-bottom: 2px solid #111;
}

.all-btn {
  border: 2px solid var(--primary-color);
  padding: 7px 12px;
  background: transparent;
  cursor: pointer;
  font-weight: 700;
  display: flex;
  margin-left: auto;
  gap: 1rem;
  align-items: center;
  color: var(--primary-color);
  transition: all 0.3s ease;
}
.arrow-img {
  object-fit: contain;
  height: 1rem;
  transition: all 0.3s ease;
}

.arrow-img.mask-arrow {
  width: 16px;
  height: 12px;
  display: inline-block;
  background-color: var(--primary-color);
  -webkit-mask: url('../img/arrow-right.png') no-repeat center / contain;
  mask: url('../img/arrow-right.png') no-repeat center / contain;
  transition: background-color 0.18s ease;
}

.line {
  background: rgb(209, 209, 209);
  height: 1px;
  width: 100%;
}

.all-btn:hover .arrow-img.mask-arrow {
  background-color: #ffffff;
}

.all-btn:hover .arrow-img {
  filter: none;
}

.all-btn:hover {
  background: var(--primary-color);
  color: #ffffff;
}

.products-section {
  display: flex;
  flex-direction: column;
  margin: 10rem 10%;
  gap: 2rem;
}
.products {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1rem;
  margin-top: 12px;
  align-items: stretch;
}

.section-title {
  font-size: 2rem;
  color: var(--primary-color);
}

.card {
  background: linear-gradient(135deg, #ffffff 5%, #ededed 100%);
  border: 1px solid rgb(244, 243, 243);
  padding: 14px;
  position: relative;
  margin-bottom: 2rem;
  position: relative;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  justify-content: space-between; /* выравнивание верх/низ */
  height: 100%;
}

.stars {
  display: flex;
  gap: 0.2rem;
  margin-bottom: 0.5rem;
}

.star-img {
  object-fit: contain;
  height: 1rem;
}

.img-wrap {
  height: 170px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #fafafa;
  margin-bottom: 12px;
  overflow: hidden;
}

.product-img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}

.meta {
  font-size: 0.85rem;
  margin-bottom: 6px;
  display: flex;
  flex-direction: column;
  justify-content: left;
  align-items: start;
  gap: 0.5rem;
}

.title {
  margin: 6px 0;
  font-size: 0.95rem;
  color: #222;
}

.price {
  font-weight: 700;
  color: #111;
  display: flex;
  margin-left: auto;
  align-items: end;
  justify-content: end;
}

.products__link {
  margin-top: 1rem;
  background: #ffffff;
  color: gray;
  border: 2px solid gray;
  margin: 0 auto;
  font-size: 0.8rem;
  font-weight: 700;
  padding: 0.6rem 1.8rem;
  display: flex;
  cursor: pointer;
  transition: all 0.3s ease;
}
.products__link:hover {
  color: var(--primary-color);
  border-color: var(--primary-color);
  background: var(--secondary-color);
}

.product-price {
  margin-left: auto;
}

.discount {
  text-decoration: line-through;
  color: var(--muted);
}

.discount-price {
  color: var(--primary-color);
  margin-left: 0.5rem;
  font-size: 1.2rem;
  text-decoration: none;
}

.percents {
  position: absolute;
  top: 0.5rem;
  left: 0.5rem;
  color: var(--primary-color);
  font-weight: 600;
  background: var(--secondary-color);
  padding: 0.3rem;
}

.big-discount {
  color: var(--secondary-color);
  background: var(--primary-color);
}

.heart {
  position: absolute;
  top: 1rem;
  right: 1rem;
}

.heart-img {
  height: 1.5rem;
  width: 100%;
  object-fit: contain;
}

@media (max-width: 1300px) {
  .products {
    grid-template-columns: repeat(3, 1fr);
  }
  @media (max-width: 1200px) {
    .products {
      grid-template-columns: repeat(3, 1fr);
    }
    .tab-btn {
      opacity: 0;
    }
  }
}
@media (max-width: 750px) {
  .products {
    grid-template-columns: repeat(2, 1fr);
  }
}
@media (max-width: 400px) {
  .products {
    grid-template-columns: repeat(1, 1fr);
  }
}
@media (max-width: 700px) {
  .section-title {
    font-size: 1.5rem;
  }
}

@media (max-width: 500px) {
  .products-section {
    margin: 3rem 10%;
  }
}
</style>
