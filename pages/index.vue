<script setup lang="ts">
import Navbar from '~/components/Header/Navbar.vue';

const scrollToProfil = () => {
  const profilSection = document.getElementById('profil');
  if (profilSection) {
    profilSection.scrollIntoView({ behavior: 'smooth' });
  }
};

const handleSubmit = (event) => {
  event.preventDefault();
  const email = document.getElementById('email').value;
  const subject = document.getElementById('subject').value;
  const message = document.getElementById('message').value;

  const mailtoLink = `mailto:simon.maigrot.pro@gmail.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(message)}%0AFrom: ${encodeURIComponent(email)}`;
  window.location.href = mailtoLink;
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
                <img src="assets/cloud.png" alt="cloud" class="cloud">
                <img src="assets/pluie.gif" alt="rain" class="rain">
            </div>
        </section>
        <section class="profil" id="profil">
            <h1 class="mb-4 text-4xl font-extrabold leading-none tracking-tight text-gray-900 md:text-5xl lg:text-5xl dark:text-white">Bonjour,<br> je suis Simon Maigrot, développeur passionné par le <span class="text-blue-600 dark:text-blue-500">web</span></h1>
            <p class="text-lg font-normal text-gray-500 lg:text-xl dark:text-gray-400">Actuellement en deuxième année à Epitech Technology à Bruges, je me consacre également au développement web en freelance, alliant théorie et pratique.</p>
            <slider class="sliderr" />
        </section>
        <section class="projets" id="projets">
            <section class="py-20 w-[90%]">
                <div class="flex flex-col flex-1 gap-10 lg:gap-0 lg:flex-row lg:justify-between">
                    <div class="w-full lg:w-1/4 border-b pb-10 lg:border-b-0 lg:pb-0 lg:border-r border-gray-100">
                        <div class="font-manrope font-bold text-5xl text-white mb-5 text-center ">6+</div>
                        <span class="text-xl text-white text-center block ">Projets réalisés</span>
                    </div>
                    <div class="w-full lg:w-1/4 border-b pb-10 lg:border-b-0 lg:pb-0 lg:border-r border-gray-100">
                        <div class="font-manrope font-bold text-5xl text-white mb-5 text-center ">100%</div>
                        <span class="text-xl text-white text-center block ">Clients satisfaits</span>
                    </div>
                    <div class="w-full lg:w-1/4 border-b pb-10 lg:border-b-0 lg:pb-0 lg:border-r border-gray-100">
                        <div class="font-manrope font-bold text-5xl text-white mb-5 text-center ">4 ans</div>
                        <span class="text-xl text-white text-center block ">Aprentissage</span>
                    </div>
                    <div class="w-full lg:w-1/4 ">
                        <div class="font-manrope font-bold text-5xl text-white mb-5 text-center ">2500+</div>
                        <span class="text-xl text-white text-center block ">Heures de travail</span>
                    </div>
                </div>
            </section>
            <cards />                 
        </section>
        <section class="contact" id="contact">
            <section>
            <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md">
                <h2 class="mb-4 text-4xl tracking-tight font-extrabold text-center text-gray-900 dark:text-white">Contactez-moi</h2>
                <p class="mb-8 lg:mb-16 font-light text-center text-gray-500 dark:text-gray-400 sm:text-xl">Avez-vous des questions ou des retours concernant mes services ? Que ce soit un problème technique, des commentaires sur une fonctionnalité bêta, ou des informations sur mon plan d'affaires, je suis là pour vous aider. N'hésitez pas à me contacter !</p>
                <form @submit="handleSubmit" class="space-y-8">
                <div>
                    <label for="email" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Email</label>
                    <input type="email" id="email" class="shadow-sm bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light" placeholder="john.doe@gmail.com" required>
                </div>
                <button type="submit" class="py-3 px-5 text-sm font-medium text-center text-black rounded-lg bg-white hover:bg-gray-200 focus:ring-4 focus:outline-none focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">Envoyer un message</button>
            </form>
            </div>
            </section>
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
    justify-content: space-around;
    background-repeat: no-repeat;
    background-size: cover;
    align-items: center;
}

.landing-left {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    position: relative;
    padding-left: 0px;
    padding-top: 150px;
}

.landing-left h1 {
    font-size: 13vw;
}

.landing-left p {
    font-size: 4vw;
}

.landing-right {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
}

.cloud {
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 50vw;
}

.rain {
    width: 30vw;
    position: absolute;
    top: 37%;
    left: 50%;
    transform: translate(-50%, 0);
    z-index: -1;
}

.projets {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
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

.contact {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-repeat: no-repeat;
    background-size: cover;
}

.profil {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
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

@media screen and (min-width: 1000px) {

    .landing-left {
        width: 50%;
        padding-left: 100px;
        align-items: flex-start;
        padding-top: 0px;
    }

    .landing-left h1 {
        font-size: 80px;
    }

    .landing-left p {
        font-size: 25px;
    }


    .landing-right {
        display: block;
    }

    .landing-right {
        width: 50%;
    }

    .landing {
        flex-direction: row;
    }

    .cloud {
        position: absolute;
        top: 40%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 40vw;
    }

    .rain {
        width: 24vw;
        position: absolute;
        top: 37%;
        left: 50%;
        transform: translate(-50%, 0);
        z-index: -1;
    }
}
</style>
