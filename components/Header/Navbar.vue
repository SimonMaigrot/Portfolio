<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';

const isTextBlack = ref(false);

const handleScroll = (event: Event) => {
    event.preventDefault();
    const targetId = (event.target as HTMLAnchorElement).getAttribute('href');
    const targetElement = document.querySelector(targetId);

    if (targetElement) {
        targetElement.scrollIntoView({ behavior: 'smooth' });
    }
};

const updateTextColor = () => {
    const sections = document.querySelectorAll('section');
    const scrollPosition = window.scrollY + window.innerHeight / 2;

    sections.forEach(section => {
        const sectionTop = section.offsetTop;
        const sectionHeight = section.clientHeight;

        // Vérifie si l'utilisateur est sur les sections #profil ou #contact
        if (scrollPosition >= sectionTop && scrollPosition < sectionTop + sectionHeight) {
            isTextBlack.value = section.id === 'profil' || section.id === 'contact';
        }
    });
};

onMounted(() => {
    window.addEventListener('scroll', updateTextColor);
});

onUnmounted(() => {
    window.removeEventListener('scroll', updateTextColor);
});

</script>

<template>
    <div class="navbar">
        <ul>
            <li><a href="#landing" @click="handleScroll" :class="{ black: isTextBlack }">Accueil</a></li>
            <li><a href="#profil" @click="handleScroll" :class="{ black: isTextBlack }">Profil</a></li>
            <li><a href="#projets" @click="handleScroll" :class="{ black: isTextBlack }">Projets</a></li>
            <li><a href="#contact" @click="handleScroll" :class="{ black: isTextBlack }">Contact</a></li>
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
}

.navbar ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    font-family: 'League Spartan';
    font-weight: 7600;
    font-size: 20px;
}

.navbar li {
    margin-right: 25px;
    position: relative;
}

.navbar a {
    color: white;
    text-decoration: none;
    transition: color 0.3s;
}

.navbar a.black {
    color: black;
}

.navbar a::after {
    content: '';
    display: block;
    width: 100%;
    height: 2px;
    background: white;
    position: absolute;
    left: 0;
    bottom: -5px;
    transform: scaleX(0);
    transition: transform 0.3s ease;
}

.navbar a:hover::after {
    transform: scaleX(1);
}

</style>
