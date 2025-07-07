<template>
  <div class="contact">
    <!-- Left side: Info -->
    <div class="info">
      <h2>Contact <b>Me</b></h2>
      <span>Let's Work Together</span>
      <p>
        Thank you for visiting my personal portfolio website! If you have any questions, suggestions,
        or would like to collaborate, feel free to reach out using this form. I'll do my best to respond
        to your message as soon as possible.
      </p>

      <!-- Contact Details -->
      <div class="contact-details">
        <div class="contact-item">
          <img src="../assets/Photos/sendd.png" alt="Email icon" />
          <p><b>georgertolordava5@gmail.com</b></p>
        </div>
        <div class="contact-item">
          <img src="../assets/Photos/call.png" alt="Phone icon" />
          <p><b>(+995) 571-218-901</b></p>
        </div>
      </div>

      <!-- Socials -->
      <div class="socials">
        <a href="https://www.facebook.com/giorgi.tolordava.576786" target="_blank">
          <img src="../assets/Photos/facebook.png" alt="Facebook" />
        </a>
        <a href="https://www.instagram.com/georgetolordava5/" target="_blank">
          <img src="../assets/Photos/instagram.webp" alt="Instagram" />
        </a>
        <a href="https://github.com/Tolordava5" target="_blank">
          <img src="../assets/Photos/github.png" alt="GitHub" />
        </a>
        <a href="https://www.linkedin.com/in/george-george-629411258/" target="_blank">
          <img src="../assets/Photos/linkdin.png" alt="LinkedIn" />
        </a>
      </div>
    </div>

    <!-- Right side: Form -->
    <div class="form">
      <input type="text" placeholder="Enter Your Name" />
      <input type="email" placeholder="Enter Your Email" />
      <input type="text" placeholder="Enter Your Subject" />
      <textarea placeholder="Enter Your Message"></textarea>
      <button>Submit</button>
    </div>
  </div>
</template>

<style scoped>
.contact {
  display: grid;
  grid-template-columns: 1fr 1fr;
  background: linear-gradient(to left, #161616, #1a1128);
  color: white;
  font-size: 21px;
  padding: 30px 50px 30px 200px;
  overflow-x: clip;
  gap: 40px;
  padding-top: 200px;
}

/* Left */
.info {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.info h2 {
  font-size: 72px;
  display: flex;
  gap: 10px;
  justify-content: center;
}

.info h2 b {
  color: #a259ff;
  text-shadow: 0 0 4px #A259FF, 0 0 8px #A259FF;
}

.info span {
  font-size: 20px;
  opacity: 0.8;
}

.info p {
  max-width: 600px;
  line-height: 1.5;
}

/* Contact details */
.contact-details {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 15px;
}

.contact-item img {
  width: 32px;
}

/* Socials */
.socials {
  display: flex;
  gap: 20px;
  margin-top: 20px;
}

.socials img {
  width: 36px;
  height: 36px;
  transition: transform 0.3s ease;
}

.socials img:hover {
  transform: scale(1.1);
}

/* Right */
.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 15px;
}

.form input,
.form textarea {
  max-width: 400px;
  width: 100%;
  border-radius: 12px;
  border: none;
  padding: 20px;
  background-color: rgba(255, 255, 255, 0.08);
  color: white;
  font-size: 16px;
  font-family: inherit;
}

.form textarea {
  height: 140px;
  resize: none;
}

.form button {
  background-color: #a259ff;
  border: none;
  border-radius: 12px;
  width: 200px;
  height: 51px;
  cursor: pointer;
  margin-top: 30px;
  transition: 0.4s ease;
}

.form button:hover {
  box-shadow: 0 0 10px #a259ff, 0 0 20px #a259ff;
}

@media screen and (max-width: 768px) {
  .contact {
    display: flex;
    flex-direction: column;
    padding: 30px 20px;
    gap: 50px;
    border-top: 1px solid white;


  }

  .info h2 {
    font-size: 42px;
    justify-content: flex-start;
  }

  .form,
  .form input,
  .form textarea {
    width: 100%;
    align-items: center;
    
  }

  .form {
    align-items: center;
  }
}
</style>
