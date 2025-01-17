<template>
    <div>
        <Navbar />
        <div class="all">
            <div class="name">
                <h1>I'm Simon</h1>
            </div>
            <div class="detailsContainer">
                <div class="details">
                    <img src="assets/defaultProfile.jpg" alt="profileImage" class="profileImage">
                    <div>
                        <h2>I'm a Product Designer working remotely from 8°C Dublin, Ireland.</h2>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque, recusandae nisi corporis perspiciatis, dolore porro expedita, quasi voluptatum natus voluptas exercitationem temporibus commodi ducimus dignissimos ipsum consequuntur inventore cum blanditiis!</p>
                    </div>
                </div>
            </div>
            <div class="collaboration">
                <div class="collaborationText">
                    <h2>Let's collaborate if you're committed to sustainability, education, equality, or carbon neutrality.</h2>
                    <p>I believe we should leave this Earth as good as or better than we found it for future generations; my goal is to contribute to those ideals in whatever way I can. If you feel the same, I'd love to talk.</p>
                </div>
                <div class="collaborationDiv">
                    <div class="collaborationDivTop">
                        <div>
                            <h2>Make it</h2>
                            <p>I sketch wireframes and make prototypes. Talking through tactile designs existing in the browser is worth its weight. Design tools only carry you so far; the rest should be realized with a link my team can rally around.</p>
                        </div>
                        <div>
                            <h2>Collaborate</h2>
                            <p>Good design is not created in a vacuum but rather in a shared space. It must be facilitated and iterated upon as a team. I aim to include stakeholders in my design process and create a collaborative environment that welcomes and encourages feedback.</p>
                        </div>
                    </div>
                    <div class="collaborationDivTop">
                        <div>
                            <h2>Accessible FTW</h2>
                            <p>I aim to make everything I design accessible to all for one main reason - it's the right thing to do. Accessible products benefit the many, not the few.</p>
                        </div>
                        <div>
                            <h2>Keep experimenting</h2>
                            <p>Everything I create is subject to change and experimentation. Not everything will work, but it's worth trying - and learning from what doesn't.</p>
                        </div>
                    </div>
                </div>
                <div class="flex justify-center">
                    <div class="w-[70%]">
                        <p>Before I stepped into the world of product design, I was a web developer. One of my earliest jobs involved writing HTML emails, in a time before email linters. Lots of wishing, hoping, and finger crossing that your email arrived in a recipient's inbox in one piece.
    
    Coding emails forced me to understand how HTML and CSS play together, a skill set I've carried and kept fresh in the years since. My side project work is just an excuse to satisfy my curiosity about new technologies and understand how the web is moving forward.
    
    Outside work, I enjoy good coffee near my home by the sea, listening to and playing music, exploring the world with my partner, and playing with my Labrottie pup, Louie.</p>
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