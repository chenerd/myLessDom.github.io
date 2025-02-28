<template>
    <div class="about">
      <h2>关于我</h2>
      <div class="about-content">
        <div class="bio">
          <h3>个人简介</h3>
          <p>这里是您的个人简介内容，可以描述您的经历、教育背景等。</p>
        </div>
        
        <div class="experience">
          <h3>工作经历</h3>
          <div class="timeline">
            <div class="timeline-item" v-for="job in experience" :key="job.company">
              <h4>{{ job.company }}</h4>
              <p class="period">{{ job.period }}</p>
              <p>{{ job.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'About',
    data() {
      return {
        experience: [
          {
            company: '某科技公司',
            period: '2020 - 至今',
            description: '担任前端开发工程师，负责公司主要产品的开发与维护。'
          },
          {
            company: '某网络公司',
            period: '2018 - 2020',
            description: '担任初级前端开发工程师，参与多个项目开发。'
          }
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  .about {
    max-width: 800px;
    margin: 0 auto;
    padding: 2rem;
  }
  
  .about-content {
    margin-top: 2rem;
  }
  
  .timeline {
    margin-top: 2rem;
  }
  
  .timeline-item {
    padding: 1rem;
    border-left: 2px solid #42b983;
    margin-bottom: 2rem;
    position: relative;
  }
  
  .timeline-item::before {
    content: '';
    position: absolute;
    left: -8px;
    top: 0;
    width: 14px;
    height: 14px;
    border-radius: 50%;
    background-color: #42b983;
  }
  
  .period {
    color: #666;
    font-style: italic;
  }
  </style>