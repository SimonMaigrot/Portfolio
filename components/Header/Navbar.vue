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

</script>

<template>
    <div class="navbar">
        <ul>
            <div class="link">
                <a href="#landing" @click="handleScroll">Accueil</a>
                <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 15 15">
                    <path fill="white" d="m8.146 9.146l-.353.354l.707.707l.354-.353zM10.5 7.5l.354.354l.353-.354l-.353-.354zM8.854 5.146L8.5 4.793l-.707.707l.353.354zm0 4.708l2-2l-.708-.708l-2 2zm2-2.708l-2-2l-.708.708l2 2zM10.5 7H4v1h6.5z" />
                </svg>
            </div>
            <div class="link">
                <a href="#profil" @click="handleScroll">Profil</a>
                <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 15 15">
                    <path fill="white" d="m8.146 9.146l-.353.354l.707.707l.354-.353zM10.5 7.5l.354.354l.353-.354l-.353-.354zM8.854 5.146L8.5 4.793l-.707.707l.353.354zm0 4.708l2-2l-.708-.708l-2 2zm2-2.708l-2-2l-.708.708l2 2zM10.5 7H4v1h6.5z" />
                </svg>
            </div>
            <div class="link">
                <a href="#projets" @click="handleScroll">Projets</a>
                <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 15 15">
                    <path fill="white" d="m8.146 9.146l-.353.354l.707.707l.354-.353zM10.5 7.5l.354.354l.353-.354l-.353-.354zM8.854 5.146L8.5 4.793l-.707.707l.353.354zm0 4.708l2-2l-.708-.708l-2 2zm2-2.708l-2-2l-.708.708l2 2zM10.5 7H4v1h6.5z" />
                </svg>
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

.navbar ul {
    display: flex;
    font-family: 'League Spartan';
    font-weight: 400;
    font-size: 20px;
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

</style>
