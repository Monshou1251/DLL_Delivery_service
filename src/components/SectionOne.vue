<template>
  <div class="container">
    <section class="section">
      <!-- Block 1: Big block with text and buttons -->
      <div class="text-container">
        <h1 class="big-text">From USA Shops to Your Home in Uzbekistan</h1>
        <p class="small-text">We Deliver What You Need</p>
        <div class="buttons">
          <div class="action-button button-1">Quick Guide</div>
          <div class="action-button button-2">Shops</div>
        </div>
      </div>

      <!-- Block 2, 3, 4: Smaller blocks arranged in a row -->
      <div class="small-blocks">
        <CardSection v-for="(card, index) in cardData" :key="index" class="small-block" :title="card.title"
          :percentage="card.percentage" :description="card.description" />
      </div>
    </section>
  </div>
</template>

<script setup>
import { useI18n } from 'vue-i18n';
import CardSection from './Cards/CardSection1.vue';

const { t } = useI18n();

const cardData = [
  {
    title: 'Trusted by Thousands',
    percentage: '98%',
    description:
      'With a 98% satisfaction rate, our customers consistently praise us for our reliable service and exceptional care.',
  },
  {
    title: 'Unmatched Speed',
    percentage: '1200+',
    description:
      'Our dedicated team ensures that over 1200 packages reach their destination every month, on time and in perfect condition.',
  },
  {
    title: 'New Customers Each Month',
    percentage: '500+',
    description:
      'Join the 500+ new customers who trust us each month to handle their deliveries with professionalism and efficiency.',
  },
];

</script>

<style scoped>
/* Container settings for responsiveness */
.container {
  padding-top: 53px;
  min-height: 100vh;
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 5vh 5vw;
  border-bottom: dashed 2px var(--silver-color);
}

/* Section with a fixed max width for responsiveness */
.section {
  max-width: 1170px;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 150px;
  /* padding: 8% 8%; */
}

/* Block 1: Big block styles */
.text-container {
  text-align: center;
  padding-top: 10%;
}

.big-text {
  font-size: 48px;
  font-weight: 800;
  max-width: 742px;
  line-height: 50px;
  color: var(--grey-color);
}

.small-text {
  font-size: 24px;
  margin-top: 10px;
  color: #818181;
}

.buttons {
  margin-top: 20px;
  display: flex;
  gap: 15px;
  justify-content: center;
  font-size: 16px;
  height: 30px;
  opacity: 0.8;

}


.button-1 {
  background-color: var(--grey-color);
  color: #fff;
}

.button-1:hover {
  transform: scale(1.01);
  opacity: 1;

}

.button-2:hover {
  transform: scale(1.01);
  background-color: var(--grey-color);
  opacity: 1;
  color: #fff;

}

.action-button {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 16px;
  cursor: pointer;
  font-family: 'Montserrat', sans-serif;
  border: 2px solid var(--grey-color);
  border-radius: 1000px;
  width: 140px;
}

/* Block 2, 3, 4: Smaller blocks styles */
.small-blocks {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  gap: 35px;
}

.small-block {
  width: 300px;
  height: 260px;
  /* background-color: #f0f0f0; */
  border: 4px solid #49494918;
  display: flex;
  align-items: center;
  /* justify-content: center; */
  border-radius: 50px;
  text-align: center;
  font-size: 20px;
}

/* Responsive settings for tablet */
@media (max-width: 1170px) {
  .section {
    max-width: 828px;
    gap: 25px;
  }

  .small-blocks {
    flex-direction: column;
    gap: 25px;
  }
}
</style>
