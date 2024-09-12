<template>
  <div class="container">
    <div class="main-title-block">
      <div class="main-title">
        Shipping Cost Calculator
      </div>
      <div class="main-description">
        Provide some information about your package and calculate the price
      </div>
    </div>
    <div class="cards-block">
      <div class="left-block">
        <div class="card">
          <div class="img-block">
            <img src="@/assets/images/calculation.png" alt="Image Description">
          </div>
          <div class="left-block-description">
            <div>
              Pickup from warehouse in Tashkent: free
            </div>
            <div>
              Delivery in Tashkent: $3.00
            </div>
            <div>
              Delivery throughout Uzbekistan: $3.00 (promotion)
            </div>
          </div>

        </div>
      </div>

      <div class="right-block">
        <div class="card-right">
          <div class="input-block">
            <div class="input-1">
              Weight*
              <input type="text" class="card-input" placeholder="10.2">
            </div>
            <div class="input-2">
              Value
              <input type="text" class="card-input" placeholder="$232">
            </div>
            <div class="input-1">
              Height (cm)*
              <input type="text" class="card-input" placeholder="25.0">
            </div>
            <div class="input-2">
              Width (cm)*
              <input type="text" class="card-input" placeholder="25.0">
            </div>
            <div class="input-2">
              Length (cm)*
              <input type="text" class="card-input" placeholder="125.0">
            </div>
          </div>
          <div class="button-block">
            <div class="required">
              required field*
            </div>
            <div class="button-calculate">
              Calculate
            </div>
          </div>
          <div class="result">
            <div class="result-text">
              <div class="result-text">
                Estimated price
              </div>
              <div class="resulting-price">
                $12
              </div>
            </div>
            <div class="result-text">
              <div class="result-text">
                Estimated delivery time:
              </div>
              <div class="resulting-time">
                7-9 days
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Button -->
    <div class="button">
      Detailed Calculation
    </div>
  </div>
</template>

<script setup>
import { useI18n } from 'vue-i18n';

const { t } = useI18n();
</script>

<style scoped>
.container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  padding: 5vh 5vw;
  gap: 30px;
  border-bottom: dashed 2px var(--silver-color);
  color: var(--grey-color);
}


.main-title-block {
  color: var(--grey-color);
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 5px;
}

.main-title {
  font-size: 2rem;
  font-weight: bold;
  line-height: 1.1;
}

.main-description {
  font-size: 1rem;
  /* font-weight: bold; */
}

.cards-block {
  display: flex;
  justify-content: center;
  max-width: 1169px;
  /* max-height: 568px; */
  flex-wrap: wrap;
  flex-direction: row-reverse;
  background-color: #F0F0F0;
  padding: 10px;
  border-radius: 20px;
}

.card {
  padding: 50px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.left-block {
  /* background-color: rgba(127, 255, 212, 0.308); */
  display: flex;
  flex-wrap: wrap;
  /* min-width: 500px; */
  flex: 1;
  /* min-height: 500px; */

}

.right-block {
  display: flex;
  flex-wrap: wrap;
  /* min-width: 500px; */
  flex: 1;
  /* min-height: 500px; */

}



.img-block {
  max-width: 100%;
  height: 120%;
  display: block;

}

.img-block img {
  height: 100%;
  width: 100%;
  min-width: 200px;
  object-fit: cover;
}

.left-block-description {
  color: #818181;
  text-align: left;
  line-height: 1.2;
  font-size: 16px;
  line-height: 1.2;
  padding: 10px 0;
  font-size: 0.875rem;
  border-top: dashed 2px var(--silver-color);
}

.left-block-description div {
  margin: 0;
  padding: 1px;

}

.result {
  line-height: 1.2;
  width: 100%;
}

.result-text {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  font-size: 1rem;
  font-weight: 500;
}

.resulting-price {
  font-size: 1.5rem;
  font-weight: 800;
}

.resulting-time {
  font-size: 1.5rem;
}

.card-right {
  padding: 50px;
  display: flex;
  gap: 30px;
  width: 100%;
  flex-wrap: wrap;
}

.input-block {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: flex-start;
  align-items: flex-start;
  /* height: 200px; */
}

.input-1 {
  flex: 1;
  min-width: 200px;
}

.input-2 {
  flex: 1;
  min-width: 200px;
}


.card-input {
  width: 100%;
  padding: 5px;
  height: 40px;
  border: 2px solid var(--silver-color);
  font-size: 14px;
}

.card-input:focus {
  outline: none;
  border-color: var(--grey-color);
  font-family: Montserrat;
}

.card-input::placeholder {
  font-size: 14px;
  font-weight: 300;
  color: var(--silver-color);
  font-family: Montserrat;
}

.button-block {
  width: 100%;
  border-top: dashed 2px var(--silver-color);
  /* padding: 40px 0; */
}

.required {
  font-size: 0.875rem;
  color: var(--silver-color);
}

.button-calculate {
  margin-top: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 1000px;
  height: 45px;
  width: 100%;
  font-size: 1rem;
  font-weight: 600;
  border: solid 2px var(--grey-color);
  color: var(--grey-color);
  transition: box-shadow 0.3s ease-in-out, background-color 0.3s ease-in-out;
}

.button-calculate:hover {
  cursor: pointer;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.button-calculate:active {
  box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.2);
  background-color: var(--light-grey-color);
}

.button {
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 1000px;
  height: 45px;
  width: 220px;
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

.button:active {
  box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.2);
  background-color: var(--grey-color);
}

@media (max-width: 768px) {

  .card,
  .card-right {
    padding: 10px;
  }
}
</style>
