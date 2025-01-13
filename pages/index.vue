<script setup lang="ts">
const scrollToSection = (id: string) => {
  const section = document.querySelector(id);
  if (section) {
    section.scrollIntoView({ behavior: "smooth" });
  }
};
</script>

<template>
    <div>
        <Navbar />
        <div class="all">
            <div class="gradient">
            </div>
            <div class="home">
                <img src="assets/background.png" alt="backgroundImage" class="backgroundHome">
                <div>
                    <h1>Hi. I'm Simon.</h1>
                    <h1>A Developer</h1>
                </div>
                <p>I'm passionate about crafting experiences that are engaging, accessible, and user-centric.</p>
            </div>
            <div class="profile">
                <div class="profileContainer">
                    <div class="profileBox profilePink">
                        <div class="profileBoxTop">
                            <h2 style="color: #233831;">HELP SCOUT</h2>
                            <h2 style="font-size: 45px; font-weight: 700; color: #233831;">Design</h2>
                        </div>
                        <div class="w-[100%] h-[100%] flex justify-end">
                            <div class="w-[80%] h-[100%] pt-28">
                                <img src="assets/design.svg" alt="design">
                            </div>
                        </div>
                    </div>
                    <div class="profileBox profileGreen">
                        <div class="profileBoxTop">
                            <h2 style="color: #233831;">HELP SCOUT</h2>
                            <h2 style="font-size: 45px; font-weight: 700; color: #233831;">SEO</h2>
                        </div>
                        <div class="w-[100%] h-[100%] flex justify-center pl-10 pr-10">
                            <div class="w-[500px] lg:w-[500px] h-[100%] pt-28">
                                <img src="assets/seo.svg" alt="seo">
                            </div>
                        </div>
                    </div>
                </div>
                <div class="profileContainer">
                    <div class="profileBox profileOrange">
                        <div class="profileBoxTop">
                            <h2 style="color: #233831;">HELP SCOUT</h2>
                            <h2 style="font-size: 45px; font-weight: 700; color: #233831;">Dev</h2>
                        </div>
                        <div class="w-[100%] h-[100%] flex justify-end">
                            <div class="w-[80%] lg:w-[800px] h-[100%] pt-28">
                                <img src="assets/dev.svg" alt="dev">
                            </div>
                        </div>
                    </div>
                    <div class="profileBox profileBlue">
                        <div class="profileBoxTop">
                            <h2 style="color: #233831;">HELP SCOUT</h2>
                            <h2 style="font-size: 45px; font-weight: 700; color: #233831;">Mobile</h2>
                        </div>
                        <div class="w-[100%] h-[100%] flex justify-center">
                            <div class="w-[50%] h-[100%] pt-28">
                                <img src="assets/mobile.svg" alt="mobile">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="projects">
                <h1>In Progress.</h1>
                <p>Work in various states of design and development, from side projects, to in-flight product design and development.</p>
                <div class="profileContainer" style="margin-top: 100px">
                    <a href="https://formagold.fr" class="profileBox profileOrange" style="background-color: white;">
                        <div class="profileBoxTop cursor-pointer">
                            <h2 style="color: #233831;">SAAS</h2>
                            <h2 style="font-size: 45px; font-weight: 700; color: #233831;">Formagold</h2>
                        </div>
                        <div class="w-[100%] h-[100%] flex justify-end">
                            <div class="w-[80%] lg:w-[800px] h-[100%] pt-28">
                                <img src="assets/formagold.png" alt="dev">
                            </div>
                        </div>
                    </a>
                    <div class="profileBox profileBlue" style="background-color: #2c2c2c;">
                    </div>
                </div>
            </div>
            <Footer />
        </div>
    </div>
</template>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Abril+Fatface&family=Lobster+Two:ital,wght@0,400;0,700;1,400;1,700&family=Quicksand:wght@300..700&display=swap');

.all {
    width: 100%;
    display: flex;
    justify-content: center;
    padding-left: 30px;
    padding-right: 30px;
    padding-top: 140px;
    flex-direction: column;
}

.backgroundHome {
    z-index: -1;
    position: absolute;
    top: 0;
    left: 0;
    height: 90%;
    width: 100%;
    display: none;
}

.gradient {
    background: var(--color-gradient);
    width: 100%;
    height: 60vh;
    position: absolute;
    left: 0;
    top: 35vh;
}

.home {
    display: flex;
    flex-direction: column;
    text-align: center;
}

h1 {
    color: #8fdcc2;
    font-weight: lighter;
    font-size: 10vw;
    font-family: Abril Fatface;
    font-weight: lighter;
    line-height: 1.1;
    z-index: 10;
}

p {
    margin-top: 50px;
    color: #d4ede4;
    z-index: 10;
    font-size: clamp(1rem, .8852rem + .4898vw, 1.375rem);
}

.profile {
    display: flex;
    flex-direction: column;
    width: 100%;
    margin-top: 100px;
    width: 100%;
    gap: 50px;
    z-index: 15;
    align-items: center;
}

.profileContainer {
    width: 100%;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    max-width: 1900px;
    gap: 50px;
}

.profileBox {
    border-radius: 40px;
    transition: .3s;
    overflow: hidden;
}

.profileBox:hover {
    transform: translateY(-6px);
}

.profilePink {
    width: 100%;
    height: 300px;
    background: #d894e4;
}

.profileGreen {
    width: 100%;
    height: 300px;
    background: #A3DCD4;
}

.profileOrange {
    width: 100%;
    height: 300px;
    background: #f0bc9c;
}

.profileBlue {
    width: 100%;
    height: 300px;
    background: #c0dcf4;
}

.projects {
    width: 100%;
    display: flex;
    margin-top: 100px;
    flex-direction: column;
    align-items: center;
}

.profileBoxTop {
    padding: 35px;
    width: 100%;
    height: 20%;
    display: flex;
    flex-direction: column;
    align-items: end;
}

@media screen and (min-width: 1024px) {
    .backgroundHome {
        display: block;
    }

    .profile {
        gap: 120px;
    }

    .profileContainer {
        flex-direction: row;
        height: 550px;
    }

    .profilePink {
        width: 33%;
        height: 100%;
    }

    .profileGreen {
        width: 63%;
        height: 100%;
    }

    .profileOrange {
        width: 63%;
        height: 100%;
    }

    .profileBlue {
        width: 33%;
        height: 100%;
    }
}

@media screen and (max-width: 766px) {
    .home h1 {
        font-size: 50px;
    }

    .home p {
        margin-top: 45px;
    }

    .profile {
        margin-top: 45px;
    }
}

</style>