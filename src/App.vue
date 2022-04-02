<template>
  <div class="wrap">
    <div class="container">
      <div class="home">
        <div class="avatar">
          <div class="image" :style="{backgroundImage: `url(${avatar})`}"></div>
        </div>
        <div class="details">
          <h3 class="name">{{ name }}</h3>
          <p class="excerpt">{{ excerpt }}</p>
          <ul class="social">
            <li v-for="social in socials">
              <a :href="social.url" target="_blank"><i :class="`fab ${social.icon}`"></i></a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
let avatar = 'avatar.jpg'
let name = 'Ngo Quoc Dat'
let excerpt = 'The only way to learn a new programming language is by writing programs in it.'
let socials = [
  { name: 'Facebook', url: 'https://www.facebook.com/datlechinvn', icon: 'fa-facebook-f' },
  { name: 'Twitter', url: 'https://twitter.com/datlechin', icon: 'fa-twitter' },
  { name: 'Instagram', url: 'https://www.instagram.com/datlechin', icon: 'fa-instagram' },
  { name: 'Linkedin', url: 'https://www.linkedin.com/in/datlechin', icon: 'fa-linkedin-in' },
  { name: 'Github', url: 'https://github.com/datlechin', icon: 'fa-github' },
]
document.title = name
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Mulish:ital,wght@0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

* {
  margin: 0;
  padding: 0;
}

html {
  overflow-x: hidden;
  padding: 0;
  margin: 0;
  scroll-behavior: smooth;
}

body {
  font-family: "Mulish",serif;
  font-size: 15px;
  line-height: 30px;
  letter-spacing: 0.5px;
  word-wrap: break-word;
  font-weight: 400;
  background-color: #1a1a1a;
  color: #bbb;
  box-sizing: border-box;
}

.container {
  max-width: 960px;
  width: 100%;
  margin-left: auto;
  margin-right: auto;
  height: auto;
  padding: 0 40px;
  position: relative;
  clear: both;
}

h3 {
  font-weight: 500;
  line-height: 1.2;
  font-family: "Montserrat",serif;
  color: white;
  font-size: 30px;
}

.wrap {
  width: 100%;
  height: auto;
  clear: both;
  float: left;
  position: relative;
}

.wrap * {
  box-sizing: border-box;
}

.home {
  width: 100%;
  min-height: 100vh;
  clear: both;
  justify-content: center;
  position: relative;
  display: -webkit-flex;
  display: flex;
  align-items: center;
}

.avatar {
  min-width: 300px;
  min-height: 300px;
  position: relative;
  border-radius: 100%;
}

.avatar .image {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-repeat: no-repeat;
  background-position: 50%;
  background-size: cover;
  animation: morph 8s ease-in-out 1s infinite;
  background-blend-mode: multiply;
  box-shadow: inset 0 0 0 9px hsl(0deg 0% 100% / 30%);
  border-radius: 60% 40% 30% 70%/60% 30% 70% 40%;
  overflow: hidden;
}

@keyframes morph {
  0% {
    border-radius: 60% 40% 30% 70%/60% 30% 70% 40%;
  }
  50% {
    border-radius: 30% 60% 70% 40%/50% 60% 30% 60%;
  }
  to {
    border-radius: 60% 40% 30% 70%/60% 30% 70% 40%;
  }
}

.details {
  margin-left: 80px;
}

.details .name {
  font-size: 55px;
  font-weight: 800;
  text-transform: uppercase;
  margin-bottom: 19px;
}

.details .excerpt {
  font-family: "Montserrat",serif;
  font-style: italic;
  font-weight: 500;
  max-width: 450px;
  margin-bottom: 30px;
}

.social {
  width: 100%;
  float: left;
  margin: 0;
  list-style-type: none;
}

.social li {
  margin: 0 15px 0 0;
  display: -webkit-inline-flex;
  display: inline-flex;
}

.social li:last-child {
  margin-right: 0;
}

.social li a {
  filter: invert(1);
  text-decoration: none;
  color: #000;
  transition: 0.3s ease-in-out;
}

.social li a:hover {
  -webkit-filter: opacity(0.7);
  filter: opacity(0.7) invert(0.8);
  transform: translateY(-5px);
}

.social li i {
  font-size: 17px;
}

@media (max-width: 1200px) {
  .home {
    padding: 120px 0;
  }
}

@media (max-width: 1040px) {
  .home {
    flex-direction: column;
    text-align: center;
  }

  .avatar {
    margin-bottom: 30px;
  }

  .details {
    margin-left: 0;
  }

  .container {
    padding: 0 20px;
  }
}

@media (max-width: 767px) {
  .details .name {
    font-size: 35px;
  }

  .avatar {
    min-width: 200px;
    min-height: 200px;
  }
}
</style>