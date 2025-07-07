<template>
  <section class="skills-section">
    <h2>Skills</h2>
    <swiper
      :effect="'coverflow'"
      :grabCursor="true"
      :centeredSlides="true"
      :slidesPerView="'auto'"
      :coverflowEffect="{
        rotate: 30,
        stretch: 0,
        depth: 200,
        modifier: 2.5,
        slideShadows: true
      }"
      :pagination="true"
      :modules="modules"
      class="mySwiper"
    >
      <swiper-slide v-for="(skill, index) in skills" :key="index">
        <div class="card">
          <img :src="getImagePath(skill.img)" :alt="skill.name" />
          <p>{{ skill.name }}</p>
        </div>
      </swiper-slide>
    </swiper>
  </section>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/effect-coverflow';
import 'swiper/css/pagination';
import { EffectCoverflow, Pagination } from 'swiper/modules';

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const skills = [
      { name: "HTML", img: "HTML.png" },
      { name: "CSS", img: "CSS.png" },
      { name: "JavaScript", img: "JavaScript.png" },
      { name: "Python", img: "Python.png" },
      { name: "React", img: "React.png" },
      { name: "Vue", img: "Vue.png" },
      { name: "Tailwind", img: "Tailwind.png" },
      { name: "Typescript", img: "Typescript.png" },
      { name: "Figma", img: "Figma.png" },
    ];

    const getImagePath = (img) => new URL(`../assets/Logos/${img}`, import.meta.url).href;

    return {
      modules: [EffectCoverflow, Pagination],
      skills,
      getImagePath,
    };
  },
};
</script>

<style scoped>
.skills-section {
  background: linear-gradient(to left, #161616, #1a1128);
  padding: 100px 0;
  text-align: center;
}

h2 {
  color: white;
  font-size: 48px;
  margin-bottom: 30px;
}

.swiper {
  width: 100%;
  padding-bottom: 50px;
}

.swiper-slide {
  width: 360px;
  height: 420px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.card {
  background: linear-gradient(to bottom right, #1c1c1c, #22152e);
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.4);
  text-align: center;
  transition: transform 0.3s ease;
  height: 100%;
  width: 100%;
  border: 1px solid rgba(255, 255, 255, 0.05);
}

.card:hover {
  transform: scale(1.05);
}

.card img {
  width: 100%;
  height: 75%;
  object-fit: contain;
  padding: 20px;
}

.card p {
  font-size: 22px;
  font-weight: bold;
  color: #fff;
  padding: 10px 0;
}
</style>
