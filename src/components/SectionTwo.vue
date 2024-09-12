<template>
  <div class="container">
    <div class="main-title-block">
      <div class="main-title">
        How it works
      </div>
      <div class="main-description">
        Follow these quick steps to claim the items you desire.
      </div>
    </div>
    <div class="cards-block">
      <div class="card">
        <div class="top-area">
          <div class="number">
            1
          </div>
          <div class="text">
            <div class="title">Register your account</div>
            <div class="description">Start your journey by registering an account with us. Simply fill out the required
              forms, and once
              completed, you’ll receive a personal address in the USA. This will be the secure location where your
              packages are held before being sent to you.
            </div>
          </div>
        </div>
        <div class="bot-area">
          <div class="buttons">
            <div class="button button1">Register</div>
            <div class="button button2">Login</div>
          </div>
        </div>
      </div>
      <div class="card">
        <div class="top-area">
          <div class="number">
            2
          </div>
          <div class="text">
            <div class="title">Go Shopping!</div>
            <div class="description">Explore your favorite online stores and pick out the items you’ve been eyeing. Shop
              to your heart's content, knowing your purchases will be safely handled and delivered to your personal
              address in the USA.
            </div>
          </div>
        </div>
        <div class="bot-area">
          <div class="buttons">
            <div class="button button1">Shop List</div>
            <!-- <div class="button button2">Login</div> -->
          </div>
        </div>
      </div>
      <div class="card">
        <div class="top-area">
          <div class="number">
            3
          </div>
          <div class="text">
            <div class="title">Track Your Goods</div>
            <div class="description">Stay informed with real-time updates on your shipments. In your personal account,
              you can track the location of your packages, see the estimated delivery time, and access all the essential
              information you need.
            </div>
          </div>
        </div>
        <div class="bot-area">
          <div class="buttons">
            <div class="button button1">Tracker</div>
            <!-- <div class="button button2">Login</div> -->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { useI18n } from 'vue-i18n';
import CardSection from './Cards/CardSection2.vue';

const { t } = useI18n();
</script>

<style scoped>
/* Container settings for responsiveness */
.container {
  background-color: #81818117;
  min-height: 100dvh;
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 30px;
  justify-content: center;
  padding: 5vh 5vw;
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
  flex-direction: column;
  gap: 10px;
}

.cards-block .card:first-child {
  transform: translateX(-106px);
  /* Shift the card 20px to the left */
}

.cards-block .card:last-child {
  transform: translateX(106px);
  /* Shift the card 20px to the left */
}

.card {
  width: 600px;
  height: 280px;
  border-radius: 50px;
  background-color: #6D6D6D;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  color: white;
}

.top-area {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  gap: 20px;
}

.number {
  font-size: 128px;
  font-weight: bold;
  line-height: 1;
  padding: 5px 0 0 25px;
  max-width: 16.66%;
}

.text {
  flex: 5;
  /* Takes the remaining space (5/6th) */
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  padding-left: 20px;
  gap: 15px;
  /* Add space between number and text */
}

.title {
  font-size: 2rem;
  font-weight: Bold;
  padding-top: 10px;
}

.description {
  font-size: 1rem;
  font-weight: 300;
  line-height: 1.25;
  color: rgb(219, 219, 219);
  text-align: start;
}

.buttons {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 20px;
  font-weight: 400;
}

.button {
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 20px;
  height: 35px;
  width: 140px;

  /* background-color: var(--yellow-color); */
  transition: box-shadow 0.3s ease-in-out, background-color 0.3s ease-in-out;
}

.button:hover {
  cursor: pointer;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.button1 {
  background-color: var(--yellow-color);
}

.button2 {
  border: 2px solid var(--yellow-color);
  transition: background-color 0.2s ease-in-out;
}

.button2:hover {
  background-color: var(--yellow-color);
}

.card:hover {}

@media (max-width: 768px) {
  .card {
    width: 350px;
    height: 440px;
    padding: 20px 20px;
  }

  .cards-block .card:first-child,
  .cards-block .card:last-child {
    transform: none;
  }

  .top-area {
    padding-top: 10px;
    flex-direction: column;
    /* Stack number and text vertically */
    align-items: center;
    /* Center both number and text horizontally */
    gap: 10px;
  }

  .number {
    font-size: 6rem;
    display: flex;
    justify-content: center;
    width: 100%;
    text-align: center;
    /* Center the number horizontally */
    padding: 0;
    margin-bottom: 10px;
    /* Add some spacing between the number and the text */
  }

  .text {
    padding-left: 0;
    text-align: center;
    /* Center the text */
    gap: 20px;
    padding: 0 10px;
  }

  .title {
    font-size: 2rem;
    line-height: 1;
  }

  .description {
    font-size: 0.875rem;
  }

  .buttons {
    padding: 5px 10px;
  }
}
</style>
