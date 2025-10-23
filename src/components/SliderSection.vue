<template>
  <section class="slider">
    <div class="slider__info">
      <h1 class="slider__title">Мишень</h1>
      <p class="slider__description">
        ООО «Мишень» – это специализированный хоккейный магазин формата «монобрендового ритейла и
        сервиса», созданный для комплексного обслуживания потребностей хоккеистов всех уровней – от
        любителей до профессионалов. Наша миссия – стать главным хоккейным брендом города,
        предоставляя не только качественный товар, но и экспертные услуги, и поддержку местного
        хоккея.
      </p>
      <!-- <p class="price-row">
        <span class="price">$ 123124</span>
      </p> -->
      <div class="actions">
        <a class="btn" href="#products">К товарам</a>
      </div>
    </div>
    <div class="slider__img__block">
      <img src="../img/slider.png" alt="product" class="slider-img" />
    </div>
  </section>
</template>

<style scoped>
.slider {
  height: 100vh;
  display: flex;
  gap: 4rem;
  position: relative;
  padding: 0 10%;
  overflow: hidden;
}
.slider__info {
  display: flex;
  flex-direction: column;
  flex: 0.4;
  justify-content: center;
  gap: 1.2rem;
}
.slider__title {
  font-size: 3.8rem;
  margin-bottom: 2rem;
  font-weight: 700;
  color: var(--primary-color);
}

.price {
  font-size: 1.8rem;
}

.slider__img__block {
  flex: 0.6;
  /* width: 100%; */
}
.slider__img__block {
  position: relative;
  width: 100%;
}

.btn {
  /* height: 3rem; */
  margin-right: auto;
  margin-top: 1rem;
  padding: 1.2rem 3rem;
  font-size: 1.2rem;
  font-weight: 600;
  border: 1px solid var(--primary-color);
  background: var(--primary-color);
  color: var(--secondary-color);
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn:hover {
  background: var(--secondary-color);
  color: var(--primary-color);
}

.slider-img {
  height: 100%;
  width: 100%;
  z-index: 10;
  object-fit: contain;
  position: absolute;
  pointer-events: none;
}

.img-1 {
  height: 100%;
  width: 100%;
  max-height: 40rem;
  max-width: 25rem;
  right: 10%;
  top: 50%;
  transform: translate(-10%, -45%);
  /* right: 20rem; */
}

.img-2 {
  height: 45%;
  width: 45%;
  bottom: 0;
  /* transform: scaleX(-1); */
  right: 0;
}

.indicators {
  position: absolute;
  left: 50%;
  bottom: 24px;
  transform: translateX(-50%);
  display: flex;
  gap: 1rem;
  z-index: 50;
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

.actions {
  display: flex;
  justify-content: space-between;
}

.slider-btns {
  display: flex;
  gap: 1rem;
}

.arrow-btn {
  background: var(--primary-color);
  border: none;
  border-radius: 1rem;
  padding: 0.8rem 1.1rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.3s ease;
}

.arrow-btn:hover {
  background: #91e29f;
}

.arrow-btn:hover .btn-img {
  filter: invert(0);
}

.btn-img {
  object-fit: cover;
  height: 1.8rem;
  filter: invert(100%);
  transition: all 0.3s ease;
}

.image-frame {
  width: 30rem;
  height: 37rem;
  max-width: 40vw;
  max-height: 70vh;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  position: relative;
  margin: 0 auto;
  background: transparent;
  border-radius: 8px;
  margin-top: 17%;
}

.image-frame img {
  width: auto;
  height: 100%;
  max-width: 100%;
  object-fit: contain;
  display: block;
}

.slider__description {
  min-height: 100px;
  font-size: 1.3rem;
}

/* .slider .slider-img,
.slider .slider__title,
.slider .actions,
.slider .price,
.slider .discount-price,
.slider .slider__description,
.slider .indicators,
.slider .round,
.slider .round-1,
.slider .round-2 {
  opacity: 0;
  transform: translateY(20px);
} */

/* .slider .discount-price {
  opacity: 1;
  transform: none;
} */

.slider .round,
.slider .round-1,
.slider .round-2 {
  transform: scale(0);
}

.discount {
  text-decoration: line-through;
  color: rgb(106, 106, 106);
}

.discount-price {
  color: var(--primary-color);
  font-weight: 600;
  font-size: 2rem;
}

.price-row {
  display: flex;
  gap: 0.5rem;
  align-items: end;
}

@media (max-width: 1500px) {
  .slider__title {
    font-size: 3rem;
    margin-bottom: 0;
  }
}

@media (max-width: 1100px) {
  .slider__title {
    font-size: 2rem;
  }

  .slider__description {
    font-size: 1rem;
  }
}

@media (max-width: 700px) {
  .slider__title {
    font-size: 1.5rem;
  }
  .slider__description {
    font-size: 0.8rem;
  }

  .slider__img__block {
    opacity: 0;
    display: none;
  }

  .slider {
    height: auto;
    margin-top: 25%;
  }

  .slider__info {
    flex: 1;
  }
}

@media (max-width: 600px) {
  .slider {
    margin-top: 33%;
  }
}
</style>
