<template>
  <div class="portfolio">
    <h1>我的作品集</h1>
    <div class="projects-grid">
      <div class="project-card" v-for="project in projects" :key="project.id">
        <img :src="project.image" :alt="project.title">
        <div class="project-info">
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
          <div class="project-tags">
            <span v-for="tag in project.tags" :key="tag" class="tag">{{ tag }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Portfolio',
  data() {
    return {
      projects: [
        {
          id: 1,
          title: '个人博客网站',
          description: '使用Vue.js开发的响应式个人博客网站',
          image: 'https://picsum.photos/600/400?random=1',
          tags: ['Vue.js', 'JavaScript', 'CSS3']
        },
        {
          id: 2,
          title: '电商平台',
          description: '基于Vue.js的现代电商平台前端实现',
          image: 'https://picsum.photos/600/400?random=2',
          tags: ['Vue.js', 'Vuex', 'Element UI']
        },
        {
          id: 3,
          title: '社交媒体应用',
          description: '移动优先的社交媒体web应用',
          image: 'https://picsum.photos/600/400?random=3',
          tags: ['Vue.js', 'Firebase', 'Tailwind CSS']
        }
      ]
    }
  }
}
</script>

<style scoped>
.portfolio {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.project-card {
  background: #fff;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.project-card:hover {
  transform: translateY(-5px);
}

.project-card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.project-info {
  padding: 1.5rem;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-top: 1rem;
}

.tag {
  background: #42b983;
  color: white;
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
  font-size: 0.875rem;
}
</style> 