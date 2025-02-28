<template>
  <div class="contact">
    <h1>联系我</h1>
    <div class="contact-container">
      <div class="contact-info">
        <h2>联系方式</h2>
        <div class="info-item">
          <i class="fas fa-envelope"></i>
          <p>邮箱：your.email@example.com</p>
        </div>
        <div class="info-item">
          <i class="fas fa-phone"></i>
          <p>电话：+86 xxx xxxx xxxx</p>
        </div>
        <div class="info-item">
          <i class="fab fa-weixin"></i>
          <p>微信：your_wechat_id</p>
        </div>
      </div>

      <form class="contact-form" @submit.prevent="submitForm">
        <div class="form-group">
          <label for="name">姓名</label>
          <input type="text" id="name" v-model="form.name" required>
        </div>
        
        <div class="form-group">
          <label for="email">邮箱</label>
          <input type="email" id="email" v-model="form.email" required>
        </div>
        
        <div class="form-group">
          <label for="message">留言</label>
          <textarea id="message" v-model="form.message" rows="5" required></textarea>
        </div>
        
        <button type="submit" class="submit-btn">发送消息</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      }
    }
  },
  methods: {
    submitForm() {
      // 这里添加表单提交逻辑
      console.log('表单提交', this.form)
      // 重置表单
      this.form = {
        name: '',
        email: '',
        message: ''
      }
      alert('消息已发送！')
    }
  }
}
</script>

<style scoped>
.contact {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}

.contact-container {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 3rem;
  margin-top: 2rem;
}

.contact-info {
  background: #f8f9fa;
  padding: 2rem;
  border-radius: 8px;
}

.info-item {
  display: flex;
  align-items: center;
  margin: 1.5rem 0;
}

.info-item i {
  font-size: 1.5rem;
  color: #42b983;
  margin-right: 1rem;
}

.contact-form {
  background: #fff;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.form-group {
  margin-bottom: 1.5rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 500;
}

input, textarea {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
}

textarea {
  resize: vertical;
}

.submit-btn {
  background: #42b983;
  color: white;
  border: none;
  padding: 0.75rem 2rem;
  border-radius: 4px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.submit-btn:hover {
  background: #3aa876;
}

@media (max-width: 768px) {
  .contact-container {
    grid-template-columns: 1fr;
  }
}
</style> 