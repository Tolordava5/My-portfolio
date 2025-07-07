<template>
  <canvas ref="canvas" :width="width" :height="height" @mousemove="onMouseMove" />
</template>

<style scoped>


canvas {
  display: block;
  background: linear-gradient(to left, #161616, #1a1128);
  width: 100%;
  height: 100%;
  cursor: pointer;
}
</style>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const canvas = ref(null)
const width = window.innerWidth
const height = window.innerHeight

let ctx, animationFrameId

class Particle {
  constructor(x, y, color) {
    this.x = x
    this.y = y
    this.baseX = x
    this.baseY = y
    this.size = 2
    this.color = color
    this.velocityX = 0
    this.velocityY = 0
    this.friction = 0.9
    this.ease = 0.1
  }

  update() {
    this.x += this.velocityX
    this.y += this.velocityY

    this.velocityX *= this.friction
    this.velocityY *= this.friction

    const dx = this.baseX - this.x
    const dy = this.baseY - this.y

    this.velocityX += dx * this.ease
    this.velocityY += dy * this.ease
  }

  draw(ctx) {
    ctx.fillStyle = this.color
    ctx.beginPath()
    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2)
    ctx.closePath()
    ctx.fill()
  }
}

const particles = []
let mouse = { x: null, y: null, radius: 100 }

function createParticles(ctx) {
  ctx.clearRect(0, 0, width, height)
  ctx.font = "bold 150px Arial"
  ctx.fillStyle = "white"
  ctx.textAlign = "center"
  ctx.textBaseline = "middle"
  ctx.fillText("My Portfolio", width / 2, height / 2)

  const imageData = ctx.getImageData(0, 0, width, height)

  particles.length = 0

  for (let y = 0; y < height; y += 6) {
    for (let x = 0; x < width; x += 6) {
      const index = (y * width + x) * 4
      const alpha = imageData.data[index + 3]
      if (alpha > 128) {
        const color = `rgba(${imageData.data[index]},${imageData.data[index + 1]},${imageData.data[index + 2]},${alpha / 255})`
        particles.push(new Particle(x, y, color))
      }
    }
  }
}

function animate() {
  ctx.clearRect(0, 0, width, height)
  particles.forEach(p => {
    if (mouse.x && mouse.y) {
      const dx = p.x - mouse.x
      const dy = p.y - mouse.y
      const dist = Math.sqrt(dx * dx + dy * dy)
      if (dist < mouse.radius) {
        const force = (mouse.radius - dist) / mouse.radius
        const angle = Math.atan2(dy, dx)
        p.velocityX += force * Math.cos(angle) * 5
        p.velocityY += force * Math.sin(angle) * 5
      }
    }
    p.update()
    p.draw(ctx)
  })

  animationFrameId = requestAnimationFrame(animate)
}

function onMouseMove(e) {
  mouse.x = e.clientX
  mouse.y = e.clientY
}

onMounted(() => {
  ctx = canvas.value.getContext('2d')
  createParticles(ctx)
  animate()

  window.addEventListener('resize', () => {
    canvas.value.width = window.innerWidth
    canvas.value.height = window.innerHeight
    createParticles(ctx)
  })
})

onUnmounted(() => {
  cancelAnimationFrame(animationFrameId)
  window.removeEventListener('resize', () => {})
})
</script>
