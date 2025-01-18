<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';

const isScrolled = ref(false);
const activeLink = ref<string>('');
const isMenuOpen = ref(false);  // Nouvel état pour contrôler le menu burger

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
            <!-- Menu Burger -->
            <div class="burger-menu" @click="isMenuOpen = !isMenuOpen">
                <div :class="['burger-line', { 'open': isMenuOpen }]"></div>
                <div :class="['burger-line', { 'open': isMenuOpen }]"></div>
                <div :class="['burger-line', { 'open': isMenuOpen }]"></div>
            </div>
            
            <!-- Liens de navigation -->
            <ul :class="['navbarLi', { 'open': isMenuOpen }]">
                <li class="w-[60%]">
                    <a 
                        href="/" 
                        :class="{ 'highlight': activeLink === 'Work' }"
                        @click="setActiveLink('Work')"
                    >Work</a>
                </li>
                <li class="w-[60%]">
                    <a 
                        href="/about"
                        :class="{ 'highlight': activeLink === 'About' }"
                        @click="setActiveLink('About')"
                    >About</a>
                </li>
                <li class="w-[60%]">
                    <a 
                        href="/tools"
                        :class="{ 'highlight': activeLink === 'Tools' }"
                        @click="setActiveLink('Tools')"
                    >Tools</a>
                </li>
                <li class="w-[60%]">
                    <a 
                        href="/notes"
                        :class="{ 'highlight': activeLink === 'Notes' }"
                        @click="setActiveLink('Notes')"
                    >Notes</a>
                </li>
                <li class="w-[60%]">
                    <a 
                        href="/contact"
                        :class="{ 'highlight': activeLink === 'Contact' }"
                        @click="setActiveLink('Contact')"
                    >Contact</a>
                </li>
            </ul>
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
    justify-content: space-between;
    align-items: center;
}

.navbarLi {
    text-decoration: none;
    display: flex;
    list-style-type: none;
    padding: 0;
}

.navbarLi.open {
    display: flex;
    flex-direction: column;
    align-items: center;
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
}

.burger-menu {
    display: none;
    cursor: pointer;
    flex-direction: column;
    gap: 5px;
}

.burger-line {
    width: 30px;
    height: 3px;
    background-color: #d4ede4;
    transition: transform 0.3s ease, opacity 0.3s ease;
}

.burger-line.open:nth-child(1) {
    transform: rotate(45deg) translate(5px, 5px);
}

.burger-line.open:nth-child(2) {
    opacity: 0;
}

.burger-line.open:nth-child(3) {
    transform: rotate(-45deg) translate(5px, -5px);
}

@media screen and (max-width: 400px) {
    .navbarLi {
        display: none;
        width: 70%;
        text-align: center;
        background-color: hsla(158, 23%, 18%, .9);
        position: absolute;
        top: 60px;
        right: 10px;
        padding: 30px;
        border: 1px solid #3f7c6b68;
        border-radius: 10px;
    }

    .burger-menu {
        display: flex;
    }
    
    .navbarLi a {
        font-size: 18px;
        padding: 10px;
        display: block;
    }

    .navbar {
        width: 100%;
        justify-content: flex-end;
    }
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
