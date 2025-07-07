<template>
  <h2>Projects</h2>
  <div class="projects">
    <section class="project project-left-text">
      <div class="text">
        <h3>Estatein</h3>
        <p>what is this <br> – “This is a real estate web platform that allows users to find and list apartments</p>
        <span>What technologies are used here:</span>
        <div class="icons">
          <img src="../assets/Logos/Vue.png" alt="">
          <img src="../assets/Logos/HTML.png" alt="">
          <img src="../assets/Logos/CSS.png" alt="">
          <img src="../assets/Logos/JavaScript.png" alt="">
        </div>
        <div class="btns">
          <button>Github</button>
          <button>Link</button>
        </div>
      </div>
      <div class="image">
        <img src="../assets/Photos/estatein.png" alt="">
      </div>
    </section>

    <section class="project project-left-image">
      <div class="image">
        <img src="../assets/Photos/Crypto.png" alt="">
      </div>
      <div class="text">
        <h3>Crypto Project</h3>
        <p>what is this <br> – “This is a crypto web platform that allows users to trade cryptocurrencies</p>
        <span>What technologies are used here:</span>
        <div class="icons">
          <img src="../assets/Logos/Vue.png" alt="">
          <img src="../assets/Logos/HTML.png" alt="">
          <img src="../assets/Logos/CSS.png" alt="">
          <img src="../assets/Logos/JavaScript.png" alt="">
        </div>
        <div class="btns">
          <button>Github</button>
          <button>Link</button>
        </div>
      </div>
    </section>

       <section class="project project-left-text">
      <div class="text">
        <h3>Posts</h3>
        <p>what is this <br> – “This is a real estate web platform that allows users to find and list apartments</p>
        <span>What technologies are used here:</span>
        <div class="icons">
          <img src="../assets/Logos/Vue.png" alt="">
          <img src="../assets/Logos/HTML.png" alt="">
          <img src="../assets/Logos/CSS.png" alt="">
          <img src="../assets/Logos/JavaScript.png" alt="">
        </div>
        <div class="btns">
          <button>Github</button>
          <button>Link</button>
        </div>
      </div>
      <div class="image">
        <img src="../assets/Photos/user_posts.png" alt="">
      </div>
    </section>
    
       <section class="project project-left-text">
          <div class="image">
        <img src="../assets/Photos/login.png" alt="">
      </div>
      <div class="text">
        
        <h3>Log in</h3>
        <p>what is this <br> – “This is a real estate web platform that allows users to find and list apartments</p>
        <span>What technologies are used here:</span>
        <div class="icons">
          <img src="../assets/Logos/Vue.png" alt="">
          <img src="../assets/Logos/HTML.png" alt="">
          <img src="../assets/Logos/CSS.png" alt="">
          <img src="../assets/Logos/JavaScript.png" alt="">
        </div>
        <div class="btns">
          <button>Github</button>
          <button>Link</button>
        </div>
      </div>
    
    </section>

           <section class="project project-left-text">
      <div class="text">
        <h3>Posts</h3>
        <p>what is this <br> – “This is a real estate web platform that allows users to find and list apartments</p>
        <span>What technologies are used here:</span>
        <div class="icons">
          <img src="../assets/Logos/Vue.png" alt="">
          <img src="../assets/Logos/HTML.png" alt="">
          <img src="../assets/Logos/CSS.png" alt="">
          <img src="../assets/Logos/JavaScript.png" alt="">
        </div>
        <div class="btns">
          <button>Github</button>
          <button>Link</button>
        </div>
      </div>
      <div class="image">
        <img src="../assets/Photos/cosmo.png" alt="">
      </div>
    </section>
  </div>
  <h4>Here is a small list of my projects.</h4>
</template>


<style scoped>
.projects {
  background: linear-gradient(to left, #161616, #1a1128);
  display: flex;
  flex-direction: column;
  gap: 150px;
  padding-top: 100px;
  color: white;
  padding: 40px;
}

h2 {
  text-align: center;
  font-size: 48px;
  background: linear-gradient(to left, #161616, #1a1128);
  padding-top: 150px;
  color: white;

}
h4{
    text-align: center;
  font-size: 48px;
  background: linear-gradient(to left, #161616, #1a1128);
  padding-top: 150px;
  color: white;
}

.project {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 30px;
  align-items: center;
  font-size: 26px;
}


.text {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.image img {
  width: 100%;
  border-radius: 8px;
}

h3 {
  font-size: 36px;
}

.icons {
  display: flex;
  gap: 20px;
  padding-top: 20px;
  width: max-content;
}

.icons img {
  width: 40px;
}

.btns {
  display: flex;
  gap: 20px;
  padding-top: 20px;
}

.btns button {
  padding: 20px 40px;
  border: none;
  border-radius: 12px;
  color: white;
  font-size: 16px;
  cursor: pointer;
  transition: 0.4s;
}

.btns button:first-child {
  background-color: #A259FF;
  box-shadow: none;
}

.btns button:hover {
  box-shadow: 0 0 10px #A259FF, 0 0 20px #A259FF;
}

.btns button:last-child {
  background: transparent;
  border: 1px solid #A259FF;
}

</style>
