<template>
  <div class="app-container">
    <header class="header">
      <nav>
        <router-link to="/">首页</router-link> |
        <router-link to="/about">关于我</router-link> |
        <router-link to="/portfolio">作品集</router-link> |
        <router-link to="/contact">联系我</router-link>
      </nav>
    </header>

    <main>
      <router-view></router-view>
    </main>

    <footer>
      <p>&copy; 2024 我的个人网站</p>
    </footer>
  </div>
</template>

<style scoped>
.app-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.header {
  background-color: #2c3e50;
  color: white;
  padding: 1rem;
}

nav {
  text-align: center;
}

nav a {
  color: white;
  text-decoration: none;
  margin: 0 1rem;
}

nav a.router-link-active {
  color: #42b983;
}

main {
  flex: 1;
  padding: 2rem;
}

footer {
  background-color: #2c3e50;
  color: white;
  text-align: center;
  padding: 1rem;
}
</style>