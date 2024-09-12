<template>
    <div class="container">
        <div class="main-title-block">
            <div class="main-title">
                Support
            </div>
            <div class="main-description">
                Need help? Our support is available 24/7 to answer all your questions
            </div>
        </div>
        <div class="cards-block">
            <div class="left-block">
                <div class="card">
                    <div class="img-block">
                        <img src="@/assets/images/support-call.png" alt="Image Description">
                    </div>

                </div>
            </div>

            <div class="right-block">
                <div class="card-right">
                    <div class="title-block">
                        Need help with your purchase?
                    </div>
                    <div class="text-block">
                        Struggling to buy from an online store? Is your payment card being declined? We're here to help!
                        Simply place an order for our Purchase Assistance service, providing the links to the items you
                        need. For just a 10% fee, we'll make the purchase for you and ensure you receive exactly what
                        you ordered!
                    </div>
                    <div class="button-block">
                        <div class="button-calculate">
                            Contact Us
                        </div>
                    </div>
                </div>
            </div>
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
    min-height: 540px;
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
    justify-content: space-between;
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



.card-right {
    padding: 50px;
    display: flex;
    gap: 30px;
    width: 100%;
    flex-wrap: wrap;
}

.title-block {
    font-size: 1.5rem;
    font-weight: 600;
    width: 100%;
    text-align: center;
}

.text-block {
    padding-top: 10px;
    border-top: dashed 2px var(--silver-color);
    font-size: 1rem;
}

.button-block {
    display: flex;
    align-items: flex-end;
    width: 100%;
    margin-bottom: 10px;
    /* height: 100px; */
    /* border-top: dashed 2px var(--silver-color); */
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


@media (max-width: 768px) {

    .card,
    .card-right {
        padding: 10px;
    }
}
</style>