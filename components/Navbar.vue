<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';

const isScrolled = ref(false);

const activeLink = ref<string>('');

const checkScroll = () => {
    if (window.scrollY >= 50) {
        isScrolled.value = true;
    } else {
        isScrolled.value = false;
    }
};

const isHomePage = ref(false);

onMounted(() => {
    const currentPath = window.location.pathname;
    if (currentPath === "/") {
        localStorage.setItem('isHomePage', 'true');
        isHomePage.value = true;
    } else {
        localStorage.setItem('isHomePage', 'false');
        isHomePage.value = false;
    }
    window.addEventListener('scroll', checkScroll);
    activeLink.value = localStorage.getItem('activeLink') || 'Work';
});

const setActiveLink = (link: string) => {
    activeLink.value = link;
    localStorage.setItem('activeLink', link);
};

onBeforeUnmount(() => {
    window.removeEventListener('scroll', checkScroll);
});
</script>

<template>
    <div class="navbarContainer">
        <div :class="['navbar', { 'scrolled': isScrolled }]">
            <li class="navbarLi">
                <a 
                    href="#" 
                    :class="{ 'highlight': activeLink === 'Work' }"
                    @click="setActiveLink('Work')"
                >Work</a>
                <a 
                    href="#"
                    :class="{ 'highlight': activeLink === 'About' }"
                    @click="setActiveLink('About')"
                >About</a>
                <a 
                    href="#"
                    :class="{ 'highlight': activeLink === 'Play' }"
                    @click="setActiveLink('Play')"
                >Play</a>
                <a 
                    href="#"
                    :class="{ 'highlight': activeLink === 'Notes' }"
                    @click="setActiveLink('Notes')"
                >Notes</a>
                <a 
                    href="#"
                    :class="{ 'highlight': activeLink === 'Contact' }"
                    @click="setActiveLink('Contact')"
                >Contact</a>
            </li>
        </div>
    </div>
</template>

<style scoped>
.navbarContainer {
    width: 100%;
    display: flex;
    justify-content: center;
    position: absolute;
}

.navbar {
    padding-left: 15px;
    padding-right: 15px;
    z-index: 1000;
    height: 50px;
    margin-top: 20px;
    position: fixed;
    transition: background 0.3s, backdrop-filter 0.3s;
    border-radius: 50px;
    display: flex;
    justify-content: space-around;
    align-items: center;
}

.navbar.scrolled {
    background: hsla(158, 23%, 18%, .7);
    backdrop-filter: blur(20px);
}

.navbarLi {
    text-decoration: none;
    display: flex;
}

.navbarLi a {
    color: #d4ede4;
    padding: 5px 20px;
    border-radius: 20px;
    transition: .5s;
    font-size: 10px;
}

.navbarLi a.highlight {
    background: #6faf883d;
    padding: 5px 12px;
    border-radius: 20px;
}

@media screen and (min-width: 350px) {
    .navbarLi a {
        font-size: 13px;
    }
}

@media screen and (min-width: 500px) {
    .navbarLi a {
        font-size: 15px;
    }
}
</style>
