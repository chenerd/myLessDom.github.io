<template>
  <nav class="navbar">
    <div class="nav-brand">
      <router-link to="/" class="logo-container">
        <img src="../assets/your-logo.svg" alt="Logo" class="logo">
      </router-link>
    </div>
    
    <div class="nav-links" :class="{ 'nav-active': isMenuOpen }">
      <router-link 
        v-for="item in menuItems" 
        :key="item.path" 
        :to="item.path"
        class="nav-link"
        :class="{ 'current': $route.path === item.path }"
      >
        <span class="nav-icon"><i :class="item.icon"></i></span>
        <span class="nav-text">{{ item.text }}</span>
      </router-link>
    </div>

    <div class="menu-toggle" @click="toggleMenu" :class="{ 'active': isMenuOpen }">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'NavBar',
  data() {
    return {
      isMenuOpen: false,
      menuItems: [
        { path: '/', text: '首页', icon: 'fas fa-home' },
        { path: '/portfolio', text: '作品集', icon: 'fas fa-briefcase' },
        { path: '/contact', text: '联系我', icon: 'fas fa-envelope' }
      ]
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    }
  }
}
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 2rem;
  background: rgba(44, 62, 80, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
  z-index: 1000;
}

.nav-brand {
  display: flex;
  align-items: center;
}

.logo-container {
  width: 50px;
  height: 50px;
  overflow: hidden;
  transition: transform 0.3s ease;
}

.logo-container:hover {
  transform: rotate(360deg);
}

.logo {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-link {
  position: relative;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: #fff;
  text-decoration: none;
  font-weight: 500;
  padding: 0.5rem 1rem;
  transition: all 0.3s ease;
}

.nav-link::before {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: #42b983;
  transition: width 0.3s ease;
}

.nav-link:hover::before,
.nav-link.current::before {
  width: 100%;
}

.nav-icon {
  font-size: 1.2rem;
  color: #42b983;
  transition: transform 0.3s ease;
}

.nav-link:hover .nav-icon {
  transform: translateY(-3px);
}

.nav-text {
  position: relative;
  overflow: hidden;
}

.nav-link:hover .nav-text {
  animation: textGlow 1.5s ease-in-out infinite;
}

@keyframes textGlow {
  0%, 100% { text-shadow: 0 0 5px rgba(66, 185, 131, 0); }
  50% { text-shadow: 0 0 10px rgba(66, 185, 131, 0.5); }
}

.menu-toggle {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 21px;
  cursor: pointer;
}

.menu-toggle span {
  display: block;
  width: 100%;
  height: 3px;
  background: #fff;
  border-radius: 3px;
  transition: all 0.3s ease;
}

@media (max-width: 768px) {
  .menu-toggle {
    display: flex;
  }

  .nav-links {
    position: fixed;
    top: 70px;
    left: 0;
    right: 0;
    flex-direction: column;
    align-items: center;
    background: rgba(44, 62, 80, 0.95);
    backdrop-filter: blur(10px);
    padding: 2rem;
    gap: 1.5rem;
    transform: translateY(-150%);
    transition: transform 0.3s ease;
  }

  .nav-links.nav-active {
    transform: translateY(0);
  }

  .menu-toggle.active span:nth-child(1) {
    transform: translateY(9px) rotate(45deg);
  }

  .menu-toggle.active span:nth-child(2) {
    opacity: 0;
  }

  .menu-toggle.active span:nth-child(3) {
    transform: translateY(-9px) rotate(-45deg);
  }
}

/* 暗色主题支持 */
@media (prefers-color-scheme: dark) {
  .navbar {
    background: rgba(26, 32, 44, 0.95);
  }
}
</style> 