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
            <div class="title">
                <h1 class="portfolio">portfolio</h1>
            </div>
            <p class="name">Simon Maigrot</p>
            <a href="#profil" class="decouvrir" @click.prevent="scrollToProfil">Découvrir</a>
        </section>
        <section class="profil" id="profil">
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolor illo dolorum eum eius quod nihil obcaecati vel natus, esse, consectetur ipsam dolore, unde incidunt quaerat voluptatibus voluptates magni. Illo, necessitatibus.</p>
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Eveniet tenetur culpa saepe fugit! Amet perspiciatis, autem ut ipsa corrupti in suscipit eum, repellat facere laborum, distinctio dicta nostrum iste culpa.</p>
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
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: url("assets/background.png");
    background-repeat: no-repeat;
    background-size: cover;
}

.projets {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: url("assets/backgroundGreen.jpg");
    background-repeat: no-repeat;
    background-size: cover;
}

.decouvrir {
    display: flex;
    justify-content: center;
    border: 2px white solid;
    padding: 10px;
    border-radius: 5px;
    color: white;
    width: 130px;
    transition: .3s;
    font-weight: bold;
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
    background: white;
    background-repeat: no-repeat;
    background-size: cover;
}

.background {
    width: 100%;
    height: 100vh;
    position: absolute;
    z-index: -1;
}

.title {
    width: 60%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.portfolio {
    color: white;
    font-size: 19vw;
    font-family: 'League Spartan';
    font-weight: 700;
    letter-spacing: -0.09em;
    animation: slideInLeft 1s forwards;
}

.name {
    position: absolute;
    top: 59%;
    font-family: 'Quicksand';
    font-weight: 400;
    letter-spacing: +0.5em;
    color: white;
    font-size: 3.2vw;
    animation: slideInRight 1s forwards;
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
