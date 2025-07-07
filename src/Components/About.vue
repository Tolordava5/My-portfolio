<template>
        <h2>About Me</h2>

    <div class="information">
        <!-- Left Side -->
        <div class="text-content">
            <div>
                <h3 v-show="!showMoreText">Hello, I'm</h3>
                <h1 v-show="!showMoreText">Giorgi Tolordava</h1>
                <h2 id="autoWriter" v-show="!showMoreText">And I am Web Developer...</h2>
            </div>
            <div class="social" v-show="!showMoreText">
                <a href="https://www.facebook.com/giorgi.tolordava.576786" target="_blank">
                    <img src="../assets/Photos/facebook.png" alt="Facebook">
                </a>
                <a href="https://www.instagram.com/georgetolordava5/" target="_blank">
                    <img src="../assets/Photos/instagram.webp" alt="Instagram">
                </a>
                <a href="https://github.com/Tolordava5" target="_blank">
                    <img src="../assets/Photos/github.png" alt="GitHub">
                </a>
                <a href="https://www.linkedin.com/in/george-george-629411258/" target="_blank">
                    <img src="../assets/Photos/linkdin.png" alt="LinkedIn">
                </a>
            </div>
            <div class="btns">
                <a href="#" @click.prevent="toggleMoreText">
                    <button class="primary-btn">
                        {{ showMoreText ? 'Less about me' : 'More about me' }}
                    </button>
                </a>
                <a href="Giorgi-Tolordava.pdf">
                    <button class="secondary-btn">CV</button>
                </a>
            </div>

            <div v-if="showMoreText" class="more-about-me-box">
                <p>
                    I am a Front-end developer focused on creating
                    modern and user-friendly web solutions. I am
                    actively developing in the technological direction
                    and working to deepen my knowledge and
                    practical experience in web application
                    development. My goal is to contribute to the
                    creation of effective, functional and scalable
                    systems that will contribute to the overall
                    productivity of the company and increase user
                    satisfaction.
                </p>
            </div>
        </div>

        <div class="image-section">
            <div class="flip-card-inner">
                <img src="../assets/Photos/George.jpg" alt="Giorgi Tolordava" />
                <div class="back-text">
                    <p>I'm a 20-year-old Front-End Developer with a strong passion for building modern user-focused web
                        experiences.</p>
                </div>
            </div>
        </div>
    </div>
</template>



<style scoped>
h2{
    background: linear-gradient(to left, #161616, #1a1128);
    display: flex;
    justify-content: center;
    font-size: 48px;
    color: white;
}
.information {
    display: flex;
    justify-content: center;
    color: white;
    background: linear-gradient(to left, #161616, #1a1128);
    padding: 50px 30px;
    gap: 100px;
}

.text-content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 20px;
}

h3 {
    font-size: 40px;
}

h1 {
    font-size: 50px;
}

h2#autoWriter {
    font-size: 32px;
    color: white;
    white-space: nowrap;
    overflow: hidden;
    border-right: 2px solid #A259FF;
    width: fit-content;
}

.social {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-top: 10px;
}

.social img {
    width: 40px;
    transition: transform 0.3s;
}

.social img:hover {
    transform: scale(1.2);
}

.btns {
    display: flex;
    gap: 20px;
    margin-top: 30px;
}

.primary-btn {
    background-color: #A259FF;
    color: white;
    border: none;
    border-radius: 12px;
    width: 160px;
    height: 51px;
    cursor: pointer;
    transition: 0.4s;
}

.secondary-btn {
    background: transparent;
    border: 1px solid #A259FF;
    color: white;
    width: 160px;
    height: 51px;
    border-radius: 12px;
    cursor: pointer;
    transition: 0.4s;
}

.primary-btn:hover,
.secondary-btn:hover {
    box-shadow: 0 0 10px #A259FF, 0 0 20px #A259FF;
}

.image-section img {
    width: 500px;
    border-radius: 50%;
    object-fit: cover;
    margin: 0 auto;
    display: block;
}

.image-section {
    perspective: 1000px;
    display: flex;
    justify-content: center;
    margin-top: 50px;
    width: 500px;
    height: 500px;
    border-radius: 50%;
    position: relative;
}

.flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    transition: transform 0.8s ease-in-out;
    transform-style: preserve-3d;
    cursor: pointer;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.4);
}

.image-section:hover .flip-card-inner {
    transform: rotateY(180deg);
}

.image-section img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 50%;
    backface-visibility: hidden;
    position: absolute;
    top: 0;
    left: 0;
}

.back-text {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: linear-gradient(135deg, #A259FF 0%, #5C3E99 100%);
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    backface-visibility: hidden;
    transform: rotateY(180deg);
    padding: 20px;
    text-align: center;
    user-select: none;
}

.back-text h2 {
    font-size: 2.5rem;
    margin-bottom: 0.5rem;
}

.back-text p {
    font-size: 1.5rem;
    font-weight: 300;
}

.more-about-me-box {
    margin-top: 20px;
    padding: 20px;
    background-color: rgba(255, 255, 255, 0.05);
    border: 1px solid #A259FF;
    border-radius: 12px;
    color: white;
    font-size: 23px;
    max-width: 500px;
    height: 350px;
    animation: fadeIn 0.3s ease-in-out;
}
.more-about-me-box p{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 10px;
    font-family: 'Roboto', sans-serif;
}
@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(10px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}


@media screen and (max-width: 600px) {
    .information {
        display: flex;
        flex-direction: column-reverse;
        padding: 30px 15px;
        gap: 40px;
    }

    h1 {
        font-size: 36px;
    }

    h3 {
        font-size: 28px;
    }

    h2#autoWriter {
        font-size: 26px;
    }

    .image-section img {
        width: 320px;
        margin-top: 10px;
    }

    .btns {
        flex-direction: column;
        gap: 15px;
    }

    .primary-btn,
    .secondary-btn {
        width: 100%;
    }
}
</style>
<script setup>
import { ref, onMounted } from 'vue';

// გამხსნელი ტექტის ტოგლი
const showMoreText = ref(false);
function toggleMoreText() {
    showMoreText.value = !showMoreText.value;
}

// ტექსტის "ბეჭდვის" ანიმაცია
onMounted(() => {
    const element = document.getElementById('autoWriter');
    const text = "And I am Web Developer...";
    let index = 1;
    let isDeleting = false;

    function type() {
        if (!element) return;

        if (!isDeleting) {
            element.textContent = text.substring(0, index++);
            if (index > text.length) {
                isDeleting = true;
                setTimeout(type, 1000);
                return;
            }
        } else {
            index--;
            if (index < 2) {
                isDeleting = false;
            }
            element.textContent = text.substring(0, index);
        }

        setTimeout(type, isDeleting ? 70 : 120);
    }

    type();
});
</script>
