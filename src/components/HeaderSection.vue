<template>
  <header class="header">
    <div class="header__logo">
      <img src="../img/logo2.png" alt="logo" class="logo-img" />
    </div>
    <ul class="nav-bar">
      <li>
        <a href="#categories" class="nav-link" active-class="active-link">Категории</a>
      </li>
      <li>
        <a href="#products" class="nav-link" active-class="active-link">Товары</a>
      </li>
      <li>
        <a href="#about" class="nav-link" active-class="active-link">О нас</a>
      </li>
      <li>
        <a href="#contacts" class="nav-link">Контакты</a>
      </li>
    </ul>

    <div class="header__actions">
      <button class="btn-login">
        <span src="../img/login.png" alt="login" class="btn-img mask-arrow" aria-hidden="true">
        </span>
        Войти
      </button>

      <div class="icons">
        <!-- <img src="../img/profile.png" alt="profile" class="cart-img" />
        <div class="icon-block">
          <img src="../img/favorite.png" alt="favorite" class="cart-img" />
        </div> -->

        <div class="icon-block">
          <img src="../img/cart.png" alt="cart" class="cart-img" />
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
  padding: 1rem;
  margin: 0 10%;
  margin-top: 1rem;
  display: flex;
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  background: white;
  /* border-radius: 1rem; */
  justify-content: space-between;
  align-items: center;
  z-index: 1000;

  background: rgba(255, 255, 255, 0.55);
  -webkit-backdrop-filter: blur(10px) saturate(120%); /* Safari */
  backdrop-filter: blur(10px) saturate(120%);
}

.header__logo {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  cursor: pointer;
}

.header__title {
  font-weight: 600;
  font-size: 2rem;
}

.nav-bar {
  display: flex;
  gap: 1.5rem;
  list-style-type: none;
}

.nav-link {
  text-decoration: none;
  color: black;
  font-size: 1.4rem;
}

.logo-img {
  height: 7rem;
  object-fit: contain;
}

.header__actions {
  display: flex;
  gap: 2rem;
  align-content: center;
}

.btn-login {
  display: flex;
  gap: 0.5rem;
  font-size: 1.4rem;
  font-weight: 600;
  background: transparent;
  border: none;
  cursor: pointer;
  align-items: center;
  color: #111827; /* начальный цвет текста/иконки */
  transition: color 0.18s ease;
}

.mask-arrow {
  width: 1.8rem;
  height: 1.8rem;
  display: inline-block;
  background-color: currentColor;
  -webkit-mask: url('../img/login.png') no-repeat center / contain;
  mask: url('../img/login.png') no-repeat center / contain;
  -webkit-mask-repeat: no-repeat;
  mask-repeat: no-repeat;
  transition: background-color 0.18s ease;
}

.btn-login:hover,
.btn-login:focus {
  color: var(--primary-color);
}

.btn-img {
  height: 1.8rem;
  object-fit: contain;
}

.cart-img {
  height: 3rem;
  object-fit: contain;
  cursor: pointer;
}
.icons {
  display: flex;
  gap: 0.9rem;
}
.active-link {
  color: var(--primary-color);
  font-weight: 600;
}

.icon-block {
  position: relative;
}

.indicator {
  background: red;
  height: 1.3rem;
  width: 1.3rem;
  border-radius: 50%;
  position: absolute;
  top: -0.5rem;
  right: -0.5rem;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  font-weight: 600;
}

@media (max-width: 1000px) {
  .nav-bar {
    display: none;
  }
}

@media (max-width: 800px) {
  .logo-img {
    width: 5rem;
    height: 5rem;
  }
}

@media (max-width: 500px) {
  .btn-login {
    display: none;
  }
}
</style>
