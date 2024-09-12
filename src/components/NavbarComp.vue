<template>
    <div class="navbar">
        <div class="left-block">
            <div class="logo">
                <img src="@/assets/images/logo.svg" alt="Logo" />
            </div>
        </div>
        <div class="right-block">
            <div class="nav-links">
                <router-link to="/">{{ t('home') }}</router-link>
                <a href="#">{{ t('about') }}</a>
                <a href="#">{{ t('services') }}</a>
                <a href="#">{{ t('contact') }}</a>
            </div>
            <div class="buttons">
                <div v-if="isLoggedIn" class="user-info">
                    <span class="username-comp">{{ t('user') }}: <span class="username">{{ username }}</span></span>
                    <button @click="logout" class="cta-button">{{ t('logout') }}</button>
                </div>
                <router-link v-else to="/login" class="cta-button">
                    {{ t('getStarted') }}
                </router-link>
                <div class="language-selector">
                    <button @click="toggleDropdown" :class="{ active: isDropdownVisible }">
                        {{ currentLanguage.label }}
                        <svg-icon type="mdi" :path="mdiChevronDown"></svg-icon>
                    </button>
                    <ul v-if="isDropdownVisible" class="language-dropdown">
                        <li v-for="language in languages" :key="language.code" @click="changeLanguage(language.code)">
                            {{ language.label }}
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, computed, onMounted } from 'vue';
import { useI18n } from 'vue-i18n';
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiChevronDown } from '@mdi/js';

const { locale, t } = useI18n();
const languages = ref([
    { code: 'en', label: 'EN' },
    { code: 'ru', label: 'RU' },
    { code: 'uz', label: 'UZ' },
]);

const currentLocale = computed(() => locale.value);
const currentLanguage = computed(() => languages.value.find(lang => lang.code === currentLocale.value));

const isDropdownVisible = ref(false);

function toggleDropdown() {
    isDropdownVisible.value = !isDropdownVisible.value;
}

function changeLanguage(language) {
    locale.value = language;
    isDropdownVisible.value = false;  // Close the dropdown after selection
}

const isLoggedIn = ref(false);
const username = ref('');

onMounted(() => {
    const storedUsername = localStorage.getItem('username');
    if (storedUsername) {
        isLoggedIn.value = true;
        username.value = storedUsername;
    }
});

function logout() {
    localStorage.removeItem('username');
    isLoggedIn.value = false;
    username.value = '';
}
</script>

<style scoped>
.navbar {
    position: fixed;
    color: var(--grey-color);
    top: 0;
    left: 0;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    transition: background-color 0.3s ease-in-out;
    font-size: 0.875rem;
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
    height: 70px;
    background-color: #bdc3c736;
    box-shadow: 0 2px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
}

.right-block {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 35px;
    padding-right: 20px;
    height: 40px;
}

.logo img {
    padding-left: 15px;
    height: 60px;
    padding: 5px 0 0 15px;
}

.nav-links {
    display: flex;
    gap: 35px;
    align-items: center;


}

.nav-links a {
    text-decoration: none;
    color: var(--grey-color);
    transition: color 0.3s ease, transform 0.3s ease;
}

.nav-links a:hover {
    color: var(--yellow-color);
    transform: scale(1.05);
}

.cta-button {
    display: inline-flex;
    justify-content: center;
    align-items: center;
    padding: 6px 18px;
    font-size: 0.875rem;
    color: var(--grey-color);
    border-radius: 20px;
    border: 2px solid var(--grey-color);
    cursor: pointer;
    font-weight: 500;
    transition: background-color 0.1s ease-in-out;
    font-family: Montserrat;
    height: 35px;
    text-decoration: none;
    white-space: nowrap;
    flex-shrink: 0;
}


.cta-button:hover {
    background-color: var(--grey-color);
    color: #fff;
}

.buttons {
    display: flex;
    flex-direction: row;
    gap: 20px;
}

.language-selector {
    position: relative;
    display: flex;
    align-items: center;
    background-color: #6464643f;
    border-radius: 20px;
    box-shadow: inset 2px 1px 3px #226f9381;
    padding: 3px;
    height: 35px;
    /* width: 100%; */
}

.language-selector button {
    display: flex;
    align-items: center;
    gap: 5px;
    padding: 5px 10px;
    height: 30px;
    border: none;
    background: transparent;
    cursor: pointer;
    font-weight: 500;
    font-size: 0.9rem;
    color: var(--vt-c-white-mute);
    transition: background-color 0.2s ease, color 0.2s ease-in-out;
    border-radius: 20px;
    font-family: Montserrat;
}

.language-selector button:hover {
    background-color: #226f934b;
}

.language-selector button.active {
    background-color: var(--grey-color);
    color: white;
    box-shadow: 2px 0px 3px #226f93a4;
}

.language-selector svg-icon {
    margin-left: 8px;
}

.language-dropdown {
    position: absolute;
    top: 100%;
    right: -2px;
    z-index: 100;
    background-color: #ffffff;
    border-radius: 10px;
    box-shadow: 0 4px 8px var(--grey-color);
    margin-top: 8px;
    list-style: none;
    padding: 10px;
    width: 80px;
}

.language-dropdown li {
    padding: 5px;
    cursor: pointer;
    font-family: Montserrat;
    font-size: 0.9rem;
    color: var(--grey-color);
    text-align: center;
    transition: background-color 0.2s ease;
}

.language-dropdown li:hover {
    background-color: var(--grey-color);
    color: white;
}

.user-info {
    display: flex;
    align-items: center;
    gap: 10px;
    font-weight: 500;
    font-size: 0.9rem;
    color: var(--main-color);
    padding-left: 10px;
}

.username {
    font-weight: 800;
    padding-left: 5px;
}

.username-comp {
    background-color: #226f931f;
    padding: 5px 15px;
    white-space: nowrap;
}

@media (max-width: 768px) {

    .nav-links,
    .cta-button {
        display: none;
    }
}
</style>