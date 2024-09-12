<template>
  <div class="container">
    <div class="main-title-block">
      <div class="main-title">
        List of Shops
      </div>
      <div class="main-description">
        Pick a shop of your choice and start shopping
      </div>
    </div>

    <!-- Cards Block -->
    <div class="cards-block">
      <!-- Left Block with 3 Cards -->
      <div class="left-block">
        <div class="card one">
          <div class="card-button">
            <a href="https://www.carters.com" target="_blank">?</a>
          </div>
        </div>
        <div class="card two">
          <div class="card-button">
            <a href="https://www.6pm.com" target="_blank">?</a>
          </div>
        </div>
        <div class="card three">
          <div class="card-button">
            <a href="https://www.apple.com" target="_blank">?</a>
          </div>
        </div>
      </div>

      <!-- Right Block with 1 Big Card -->
      <div class="right-block">
        <div class="card four">
          <div class="card-button">
            <a href="https://www.amazon.com" target="_blank">?</a>
          </div>
        </div>
      </div>
    </div>

    <!-- Button -->
    <div class="button">
      List of Shops
    </div>
  </div>
</template>

<script setup>
import { useI18n } from 'vue-i18n';

const { t } = useI18n();
</script>

<style scoped>
/* Container settings for responsiveness */
.container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  padding: 5vh 5vw;
  gap: 30px;
  border-bottom: dashed 2px var(--silver-color);
}

.main-title-block {
  color: var(--grey-color);
  display: flex;
  flex-direction: column;
  align-items: center;
}

.main-title {
  font-size: 2rem;
  font-weight: bold;
}

.main-description {
  font-size: 1rem;
  /* font-weight: bold; */
  text-align: center;
}

.cards-block {
  display: flex;
  justify-content: center;
  gap: 20px;
  width: 100%;
  flex-wrap: wrap;
}

.left-block {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  width: 600px;
  min-height: 600px;
}

.right-block {
  display: flex;
  width: 600px;
  min-height: 600px;
  border-radius: 50px;
}

.card {
  min-width: 300px;
  border-radius: 50px;
  box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.2);
  transition: box-shadow 0.2s ease-in-out;
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  position: relative;
}

.card:hover {
  box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.4);
  /* cursor: pointer; */
}

.one {
  flex: 1;
  min-width: 200px;
  background-image:
    url('@/assets/images/carters.svg'),
    url('@/assets/images/carter-s-shop--baby-apparel.png');

  background-size: 200px, cover;
  background-position: center, center;
  background-repeat: no-repeat, no-repeat;
}


.two {
  flex: 1;
  min-width: 200px;
  background-image:
    url('@/assets/images/6pm2.svg'),
    url('@/assets/images/6pm-goods--handbags-and-accessories.png');
  background-size: 200px, cover;
  background-position: center, center;
  background-repeat: no-repeat, no-repeat;
}

.three {
  flex: 1;
  min-width: 200px;
  background-image:
    url('@/assets/images/apple.png'),
    url('@/assets/images/121660709784.png');
  background-size: 180px, cover;
  background-position: center, center;
  background-repeat: no-repeat, no-repeat;
}

.four {
  flex: 1;
  min-width: 200px;
  background-image:
    url('@/assets/images/amazon3.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.button {
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 1000px;
  height: 45px;
  width: 180px;
  font-size: 16px;
  font-weight: 400;
  background-color: var(--grey-color);
  color: white;
  transition: box-shadow 0.3s ease-in-out, background-color 0.3s ease-in-out, opacity 0.3s ease-in-out;
  opacity: 0.8;
}

.button:hover {
  cursor: pointer;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  opacity: 1;
}

.card-button {
  height: 40px;
  width: 40px;
  position: absolute;
  bottom: 20px;
  right: 20px;
  display: flex;
  font-size: 1.5rem;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  border-radius: 50%;
  background-color: var(--yellow-color);
  opacity: 0.5;

  transition: background-color 0.3s ease-in-out, opacity 0.3s ease-in-out;
}

.card-button a {
  text-decoration: none;
  color: white;
}

.card-button:hover {
  opacity: 1;
}


@media (max-width: 768px) {
  .card {
    min-width: 300px;
    height: 300px;
  }

  .right-block {
    min-width: 300px;
    min-height: 300px;
  }
}
</style>
