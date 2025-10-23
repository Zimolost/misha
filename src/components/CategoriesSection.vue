<template>
  <div class="gallery-grid">
    <p class="section-title">Категории</p>
    <!-- First row: 2 large blocks -->
    <div class="row row--large">
      <div class="block block--large" tabindex="0">
        <img src="../img/c1.png" alt="img" />
        <div class="block-info">
          <p class="block-title">Клюшки</p>
          <img src="../img/a-r.png" alt="" class="arrow-img" />
        </div>
      </div>
      <div class="block block--large" tabindex="0">
        <img src="../img/c2.png" alt="img" />
        <div class="block-info">
          <p class="block-title">Коньки</p>
          <img src="../img/a-r.png" alt="" class="arrow-img" />
        </div>
      </div>
    </div>

    <!-- Second row: 4 smaller blocks -->
    <div class="row row--small">
      <div class="block block--small">
        <img src="../img/c3.png" alt="img" />
        <div class="block-info block-info-small">
          <p class="block-title-small">Краги</p>
          <img src="../img/a-r.png" alt="" class="arrow-img" />
        </div>
      </div>
      <div class="block block--small">
        <img src="../img/c4.png" alt="img" loading="lazy" />
        <div class="block-info block-info-small">
          <p class="block-title-small">Нагрудники</p>
          <img src="../img/a-r.png" alt="" class="arrow-img" />
        </div>
      </div>
      <div class="block block--small" tabindex="0">
        <img src="../img/c5.png" alt="img" loading="lazy" />
        <div class="block-info block-info-small">
          <p class="block-title-small">Шлемы</p>
          <img src="../img/a-r.png" alt="" class="arrow-img" />
        </div>
      </div>
      <div class="block block--small" tabindex="0">
        <img src="../img/c6.png" alt="img" loading="lazy" />
        <div class="block-info block-info-small">
          <p class="block-title-small">Наколенники</p>
          <img src="../img/a-r.png" alt="" class="arrow-img" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
.gallery-grid {
  display: flex;
  flex-direction: column;
  gap: 16px;
  margin: 6rem 10%;
}

.row {
  display: grid;
  gap: 12px;
}

.row--large {
  grid-template-columns: repeat(2, 1fr);
}
.block--large {
  height: 420px; /* можно изменить */
}

.row--small {
  grid-template-columns: repeat(4, 1fr);
}
.block--small {
  height: 250px; /* поменьше */
}

.block {
  overflow: hidden;
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.08);
  cursor: pointer;
  display: block;
  filter: brightness(90%);
}

.block img {
  margin-left: 7%;
  width: 100%;
  height: 100%;
  object-fit: contain;
  display: block;
  transition: transform 0.35s ease;
}

.block:focus,
.block:hover {
  outline: none;
}

.block:focus img,
.block:hover img {
  transform: scale(1.02);
}

.block-info {
  position: absolute;
  bottom: 7%;
  left: 5%;
  height: 2rem;
  align-items: center;
  justify-content: center;
  display: flex;
  gap: 0.2rem;
}

.block-title {
  font-size: 2rem;
  font-weight: bold;
}

.block-title-small {
  font-weight: bold;
  font-size: 1rem;
}

.block-info-small {
  height: 1.5rem;
  bottom: 2%;
}

.arrow-img {
  height: 1rem;
  width: 1rem;
  margin-top: 2%;
  object-fit: contain;
}

.section-title {
  font-size: 2rem;
  font-weight: bold;
  margin: 2rem 0;
  color: var(--primary-color);
}

@media (max-width: 1100px) {
  .row--large {
    grid-template-columns: 1fr;
  }
  .row--small {
    grid-template-columns: repeat(2, 1fr);
  }
  .block--large {
    height: 420px;
  }
  .block--small {
    height: 210px;
  }
}

@media (max-width: 700px) {
  .section-title {
    font-size: 1.5rem;
  }

  .block-title {
    font-size: 1.5rem;
  }

  .block-title-small {
    font-size: 0.8rem;
  }

  .block-info {
    height: 1.8rem;
  }

  .block-info-small {
    height: 1.2rem;
  }
}

@media (max-width: 500px) {
  .block--large {
    height: 300px;
  }
  .block--small {
    height: 170px;
  }
}

@media (max-width: 420px) {
  .row--small {
    grid-template-columns: 1fr 1fr;
  }
  .gallery-grid {
    margin: 2rem 10%;
  }
}
</style>
