<template>
  <header>
    <h2>Portfolio</h2>
    <nav>
      <ul>
        <div class="highlight" :style="{ left: highlightLeft + 'px' }"></div>

        <li v-for="item in navItems" :key="item.id" :class="{ active: activeSection === item.id }" ref="navRefs">
          <a href="#" @click.prevent="handleClick(item.id, $event)">
            {{ item.label }}
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>



<style scoped>
header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100px;
  background: linear-gradient(to left, #161616, #1a1128);
  display: flex;
  align-items: center;
  justify-content: flex-start;
  padding: 0 40px;
  z-index: 1000;
  border-bottom: 1px solid white !important;

}

h2 {
  color: white;
  margin-right: auto;
  cursor: pointer;
  transition: 0.3s;

}

h2:hover {
  color: #A259FF;
  text-shadow: 0 0 10px #A259FF, 0 0 20px #A259FF;
}

nav {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  background: #333;
  padding: 20px 40px;
  border-radius: 50px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);

}

ul {
  position: relative;
  display: flex;
  gap: 30px;
  list-style: none;
  margin: 0;
  padding: 0;
  
}

ul>li {
  position: relative;

  
}

li a {
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.1rem;
  padding: 10px 20px;
  text-decoration: none;
  z-index: 2;
  position: relative;
  transition: color 0.3s;
}

li.active a {
  color: #1a1a1a;
    display: flex;
  align-items: center;
  justify-content: center;
}

.highlight {
  position: absolute;
  background: #9646fe;
  height: 100%;
  width: 90px;
  top: 0;
  left: 0;
  border-radius: 30px;
  transition: left 0.3s;
  z-index: 1;
  
}
</style>
<script setup>
import { ref, onMounted, nextTick } from 'vue'

const navItems = [
  { id: 'home', label: 'Home' },
  { id: 'about', label: 'About' },
  { id: 'skills', label: 'Skills' },
  { id: 'projects', label: 'Projects' },
  { id: 'contact', label: 'Contact' }
]

const activeSection = ref('home')
const highlightLeft = ref(0)
const navRefs = ref([])

function handleClick(id, event) {
  const el = document.getElementById(id)
  if (el) {
    el.scrollIntoView({ behavior: 'smooth' })
    activeSection.value = id
    moveHighlight(event.target)
  }
}

function moveHighlight(target) {
  nextTick(() => {
    const parentLi = target.closest('li')
    if (parentLi) {
      highlightLeft.value = parentLi.offsetLeft
    }
  })
}

onMounted(() => {
  const firstActive = document.querySelector('li.active a')
  if (firstActive) {
    moveHighlight(firstActive)
  }
})
</script>
