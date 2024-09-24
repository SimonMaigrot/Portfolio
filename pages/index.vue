<script setup la
  components: { Navbar },ng="ts">
import Navbar from '~/components/Header/Navbar.vue';

const scrollToProfil = () => {
  const profilSection = document.getElementById('profil');
  if (profilSection) {
    profilSection.scrollIntoView({ behavior: 'smooth' });
  }
};
</script>

<template>
    <div>
        <navbar />
        <section class="landing" id="landing">
            <div class="landing-left">
                <h1 class="portfolio">Développeur web</h1>
                <p class="name">Simon Maigrot</p>
                <a href="#profil" class="decouvrir" @click.prevent="scrollToProfil">Découvrir</a>
            </div>
            <div class="landing-right">
                <img src="assets/cloud.png" alt="cloud">
                <img src="assets/pluie.gif" alt="rain" class="rain">
            </div>
        </section>
        <section class="profil" id="profil">
            <h1 class="mb-4 text-4xl font-extrabold leading-none tracking-tight text-gray-900 md:text-5xl lg:text-5xl dark:text-white"> "L'innovation est la clé pour transformer des "<span class="text-blue-600 dark:text-blue-500"> idées en succès</span>"</h1>
            <p class="text-lg font-normal text-gray-500 lg:text-xl dark:text-gray-400">Bonjour, je m'apelle Simon Maigrot, actuellement en deuxième année à Epitech Technology à Bruges, je me consacre également au développement web en freelance, alliant théorie et pratique.</p>
            <slider class="sliderr" />
        </section>
        <section class="projets" id="projets">
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolor illo dolorum eum eius quod nihil obcaecati vel natus, esse, consectetur ipsam dolore, unde incidunt quaerat voluptatibus voluptates magni. Illo, necessitatibus.</p>
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Eveniet tenetur culpa saepe fugit! Amet perspiciatis, autem ut ipsa corrupti in suscipit eum, repellat facere laborum, distinctio dicta nostrum iste culpa.</p>
        </section>
        <section class="contact" id="contact">
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolor illo dolorum eum eius quod nihil obcaecati vel natus, esse, consectetur ipsam dolore, unde incidunt quaerat voluptatibus voluptates magni. Illo, necessitatibus.</p>
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Eveniet tenetur culpa saepe fugit! Amet perspiciatis, autem ut ipsa corrupti in suscipit eum, repellat facere laborum, distinctio dicta nostrum iste culpa.</p>
        </section>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@100..900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@300..700&display=swap');

.landing {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    background-repeat: no-repeat;
    background-size: cover;
    align-items: center;
}

.landing-left {
    width: 50%;
    height: 100vh;
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: flex-start;
    position: relative;
    padding-left: 100px;
}

.landing-right {
    width: 50%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

.projets {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-repeat: no-repeat;
    background-size: cover;
}

.profil h1 {
    padding-left: 50px;
    padding-right: 50px;
}

.profil p {
    padding-left: 50px;
    padding-right: 50px;
    text-align: center;
}

.decouvrir {
    display: flex;
    justify-content: center;
    border: 2px white solid;
    padding: 10px;
    border-radius: 100px;
    color: white;
    width: 130px;
    transition: .3s;
    font-weight: bold;
    margin-top: 50px;
}

.decouvrir:hover {
    background: white;
    color: black;
}

.profil, .contact {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-repeat: no-repeat;
    background-size: cover;
}

.portfolio {
    color: white;
    font-size: 6vw;
    font-family: 'League Spartan';
    font-weight: 700;
    letter-spacing: -0.09em;
    animation: slideInLeft 1s forwards;
}

.name {
    font-family: 'Quicksand';
    font-weight: 600;
    letter-spacing: +0.5em;
    color: white;
    font-size: 1.5vw;
    animation: slideInRight 1s forwards;
}

.rain {
    z-index: -1;
    position: absolute;
    width: 20%;
    top: 440px;
}

@keyframes slideInLeft {
    from {
        transform: translateX(-100%);
        opacity: 0;
    }
    to {
        transform: translateX(0);
        opacity: 1;
    }
}

@keyframes slideInRight {
    from {
        transform: translateX(100%);
        opacity: 0;
    }
    to {
        transform: translateX(0);
        opacity: 1;
    }
}
</style>
