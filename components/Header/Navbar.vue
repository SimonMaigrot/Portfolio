<script setup lang="ts">
import { ref } from 'vue';

const isMenuOpen = ref(false);

const handleScroll = (event: Event) => {
    event.preventDefault();
    const targetId = (event.target as HTMLAnchorElement).getAttribute('href');
    const targetElement = document.querySelector(targetId);

    if (targetElement) {
        targetElement.scrollIntoView({ behavior: 'smooth' });
    }

    if (window.innerWidth <= 768) {
        isMenuOpen.value = false;
    }
};

const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value;
};
</script>

<template>
    <div class="navbar">
        <div class="burger-menu" @click="toggleMenu">
            <div :class="{'line': true, 'active': isMenuOpen}" v-for="n in 3" :key="n"></div>
        </div>
        <ul :class="{'open': isMenuOpen}">
            <div class="link">
                <a href="#landing" @click="handleScroll">Accueil</a>
            </div>
            <div class="link">
                <a href="#profil" @click="handleScroll">Profil</a>
            </div>
            <div class="link">
                <a href="#projets" @click="handleScroll">Projets</a>
            </div>
            <div class="contact">
                <a href="#contact" @click="handleScroll">Contact</a>
            </div>
        </ul>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@100..900&display=swap');

.navbar {
    width: 100%;
    display: flex;
    justify-content: flex-end;
    padding: 15px;
    z-index: 100;
    position: fixed;
    transition: .3s;
    margin-top: 15px;
}

.burger-menu {
    display: none;
    cursor: pointer;
    flex-direction: column;
    justify-content: space-around;
    height: 20px;
    margin-right: 20px;
}

.burger-menu .line {
    width: 25px;
    height: 3px;
    background-color: white;
    transition: all 0.3s ease;
}

.burger-menu .line.active:nth-child(1) {
    transform: rotate(45deg) translate(4px, 4px);
}

.burger-menu .line.active:nth-child(2) {
    opacity: 0;
}

.burger-menu .line.active:nth-child(3) {
    transform: rotate(-45deg) translate(5px, -5px);
}

ul {
    display: flex;
    font-family: 'League Spartan';
    font-weight: 400;
    font-size: 20px;
    list-style: none;
    gap: 20px;
}

ul.open {
    display: block;
}

.navbar a {
    color: white;
    text-decoration: none;
}

.link {
    border-radius: 10px;
    display: flex;
    transition: .3s;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    margin-left: 20px;
    gap: 5px;
    font-size: 18px;
    padding: 0 15px;
}

.link:hover {
    background: rgba(255, 255, 255, 0.233);
}

.contact {
    margin-right: 40px;
    margin-left: 30px;
    background: white;
    padding: 5px 20px;
    border-radius: 10px;
    transition: .3s;
    cursor: pointer;
}

.contact:hover {
    background: rgba(255, 255, 255, 0.627);
}

.contact a {
    color: rgb(36, 36, 36);
    font-size: 16px;
}

/* Media Query for mobile */
@media (max-width: 768px) {
    .burger-menu {
        display: flex;
    }

    ul {
        display: none;
        flex-direction: column;
        position: absolute;
        top: 60px;
        right: 20px;
        background-color: black;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    ul.open {
        display: flex;
    }

    .link {
        margin: 10px 0;
        font-size: 16px;
    }

    .contact {
        margin: 10px 0;
        font-size: 16px;
    }
}
</style>
