<template>
    <div class="home">
      <h1>欢迎来到我的个人网站</h1>
      <div class="hero-section">
        <img src="../assets/image/avatar.png" alt="个人头像" class="avatar">
        <h2>你好，我是 动挥洒</h2>
        <p>前端开发工程师 / UI设计师 / 摄影爱好者</p>
      </div>
      
      <div class="skills-section">
        <h3>专业技能</h3>
        <div class="skills-grid">
          <div class="skill-card" v-for="skill in skills" :key="skill.name">
            <i :class="skill.icon"></i>
            <h4>{{ skill.name }}</h4>
            <p>{{ skill.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Home',
    data() {
      return {
        skills: [
          {
            name: 'Vue.js开发',
            icon: 'fab fa-vuejs',
            description: '精通Vue.js框架及其生态系统'
          },
          {
            name: '前端开发',
            icon: 'fas fa-code',
            description: 'HTML5, CSS3, JavaScript'
          },
          {
            name: 'UI设计',
            icon: 'fas fa-paint-brush',
            description: '用户界面设计与用户体验优化'
          }
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  .home {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
  }
  
  .hero-section {
    text-align: center;
    margin: 3rem 0;
  }
  
  .avatar {
    width: 200px;
    height: 200px;
    border-radius: 50%;
    object-fit: cover;
    margin-bottom: 1rem;
  }
  
  .skills-section {
    margin-top: 4rem;
  }
  
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
    margin-top: 2rem;
  }
  
  .skill-card {
    padding: 2rem;
    background-color: #f8f9fa;
    border-radius: 8px;
    text-align: center;
  }
  
  .skill-card i {
    font-size: 2.5rem;
    color: #42b983;
    margin-bottom: 1rem;
  }
  </style>