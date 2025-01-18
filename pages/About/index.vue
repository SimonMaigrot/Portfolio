<template>
    <div>
        <Navbar />
        <div class="all">
            <div class="name">
                <h1>I'm Simon</h1>
            </div>
            <div class="detailsContainer">
                <div class="details">
                    <img src="assets/moi.jpg" alt="profileImage" class="profileImage">
                    <div>
                        <h2>I'm a web developper working remotely from Bordeaux, France.</h2>
                        <p>I am currently a second-year student at Epitech Technology in Bruges, where I am honing my skills in software engineering and web development. Alongside my studies, I work as a freelance web developer, helping clients bring their ideas to life through modern and responsive websites. Balancing academic learning with real-world projects allows me to constantly grow as a developer while delivering high-quality results to my clients.</p>
                    </div>
                </div>
            </div>
            <div class="collaboration">
                <div class="collaborationText">
                    <h2>Let’s boost your business together.</h2>
                    <p>
                        I specialize in creating tailored strategies to increase your company’s conversion rates and build a strong online presence. Whether it’s enhancing your brand visibility or engaging your audience effectively, I’m here to help turn your vision into reality.
                    </p>
                </div>
                <div class="collaborationDiv">
                    <div class="collaborationDivTop">
                        <div>
                            <h2>Bring Ideas to Life</h2>
                            <p>I design intuitive wireframes and prototypes, turning concepts into reality. Static design tools are just the starting point; the real value comes from creating interactive designs that feel tangible and impactful.</p>
                        </div>
                        <div>
                            <h2>Collaborate with you</h2>
                            <p>Great design happens through open communication and collaboration. I work closely with my clients, ensuring their feedback is integrated at every step to create solutions that truly reflect their vision.</p>
                        </div>
                    </div>
                    <div class="collaborationDivTop">
                        <div>
                            <h2>Design for Everyone</h2>
                            <p>Accessibility is central to everything I create. Inclusive designs don’t just serve a few—they create meaningful experiences for everyone.</p>
                        </div>
                        <div>
                            <h2>Evolve Through Experimentation</h2>
                            <p>Every project is an opportunity to explore, experiment, and refine. Each iteration brings us closer to designs that inspire and deliver real results.</p>
                        </div>
                    </div>
                </div>
                <div class="flex justify-center">
                    <div class="w-[70%]">
                        <p>From Internship to Freelance
My six-month internship in web development at Wakatepe played a pivotal role in shaping my freelance journey. During this time, I focused on continuously improving the websiteand gained hands-on experience with tools, frameworks, and project workflows. Collaborating with experienced developer allowed me to understand best practices and refine my approach to solving real-world challenges.

The diversity of projects I worked on at Wakatepe (FrontEnd and Backend) gave me the confidence to handle complex tasks independently. It also inspired me to take the leap into freelancing, where I could apply these skills to help clients bring their ideas to life.

This experience taught me the importance of adaptability, effective communication, and delivering results that align with a client’s vision—values that now define my freelance work.</p>
                    </div>
                </div>
            </div>
            <Footer />
        </div>
    </div>
</template>

<style>

.all {
    width: 100%;
    display: flex;
    justify-content: center;
    padding-top: 140px;
    flex-direction: column;
}

.name {
    width: 100%;
    display: flex;
    justify-content: center;
}

.detailsContainer {
    width: 100%;
    display: flex;
    justify-content: center;
}

.details {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 90%;
    gap: 100px;
    flex-direction: column;
    margin-top: 100px;
}

.profileImage {
    width: 300px;
    height: 400px;
    object-fit: cover;
    border-top-left-radius: 200px;
    border-top-right-radius: 200px;
}

.collaboration {
    width: 100%;
    display: flex;
    margin-top: 150px;
    flex-direction: column;
    align-items: center;
}

.collaborationText {
    width: 90%;
}

.collaborationDiv {
    width: 90%;
    background-color: #28443c;
    border-radius: 64px;
    margin-top: 100px;
    padding: 50px 50px;
    display: flex;
    flex-direction: column;
    gap: 50px;
}

.collaborationDiv div {
    width: 100%;
}

.collaborationDivTop {
    width: 90%;
    display: flex;
    gap: 50px;
    flex-direction: column;
}

@media screen and (min-width: 767px) {
    .details {
        flex-direction: row;
    }

    .collaborationDivTop {
        flex-direction: row;
        gap: 150px;
    }

    .collaborationDiv {
        padding: 100px 100px;
        gap: 100px;
    }
    
    .all {
        padding-left: 30px;
        padding-right: 30px;
    }

    .collaborationText {
        width: 70%;
    }
}
</style>