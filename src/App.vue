<template>
  <div class="min-h-screen bg-white dark:bg-gray-900 transition-colors duration-300">

    <!-- 导航栏 -->
    <header class="fixed w-full top-0 z-50 bg-white/90 dark:bg-gray-900/90 backdrop-blur-sm shadow-sm">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <div class="text-xl font-bold text-blue-600 dark:text-blue-400">
            MyPortfolio
          </div>

          <nav class="hidden md:flex space-x-8">
            <a href=" " class="nav-link">首页</a >
            <a href="#about" class="nav-link">关于我</a >
            <a href="#skills" class="nav-link">技能</a >
            <a href="#projects" class="nav-link">项目</a >
            <a href="#contact" class="nav-link">联系我</a >
          </nav>

          <!-- 暗黑模式开关 -->
          <button @click="toggleDark" class="p-2 rounded-full hover:bg-gray-100 dark:hover:bg-gray-800">
            <svg v-if="!isDark" class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"></path>
            </svg>
            <svg v-else class="w-6 h-6 text-yellow-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"></path>
            </svg>
          </button>
        </div>
      </div>
    </header>

    <!-- Hero 区域 -->
    <section id="home" class="pt-32 pb-20 px-4">
      <div class="max-w-7xl mx-auto text-center">
        <h1 class="text-4xl md:text-6xl font-bold text-gray-800 dark:text-white mb-4">
          你好，我是一名 <span class="text-blue-600 dark:text-blue-400">前端开发工程师</span>
        </h1>
        <p class="text-lg md:text-xl text-gray-600 dark:text-gray-300 mb-8 max-w-2xl mx-auto">
          专注 Vue3 / 响应式 / 交互开发，热爱创造优质用户体验
        </p >
        <div class="flex justify-center gap-4">
          <a href="#projects" class="btn-primary">查看项目</a >
          <a href="#contact" class="btn-outline">联系我</a >
        </div>
      </div>
    </section>

    <!-- 关于我 -->
    <section id="about" class="py-20 bg-gray-50 dark:bg-gray-800">
      <div class="max-w-7xl mx-auto px-4">
        <h2 class="section-title">关于我</h2>
        <div class="grid md:grid-cols-2 gap-10 items-center">
          <div class="flex justify-center">
            <div class="w-64 h-64 bg-blue-100 dark:bg-blue-900 rounded-full flex items-center justify-center">
              <span class="text-4xl">👨‍💻</span>
            </div>
          </div>
          <div class="text-gray-700 dark:text-gray-200 space-y-4 text-lg">
            <p>我是一名前端开发者，熟练掌握 Vue3、JavaScript、CSS 等技术。</p >
            <p>喜欢干净的代码、优雅的交互、漂亮的界面。</p >
            <p>持续学习，不断进步，努力成为更优秀的前端工程师。</p >
            <div class="flex flex-wrap gap-2 mt-4">
              <span class="tag">前端开发</span>
              <span class="tag">Vue3</span>
              <span class="tag">响应式</span>
              <span class="tag">工程化</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- 技能 -->
    <section id="skills" class="py-20">
      <div class="max-w-7xl mx-auto px-4">
        <h2 class="section-title">我的技能</h2>
        <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-6">
          <div class="skill-card">HTML5</div>
          <div class="skill-card">CSS3</div>
          <div class="skill-card">JavaScript ES6+</div>
          <div class="skill-card">Vue3</div>
          <div class="skill-card">Vite</div>
          <div class="skill-card">Pinia</div>
          <div class="skill-card">VueRouter</div>
          <div class="skill-card">TailwindCSS</div>
        </div>
      </div>
    </section>

    <!-- 项目 -->
    <section id="projects" class="py-20 bg-gray-50 dark:bg-gray-800">
      <div class="max-w-7xl mx-auto px-4">
        <h2 class="section-title">我的项目</h2>
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div class="project-card" v-for="item in projects" :key="item.id">
            <div class="h-48 bg-blue-100 dark:bg-blue-900 rounded-lg mb-4 flex items-center justify-center">
              <span class="text-5xl">📁</span>
            </div>
            <h3 class="text-xl font-semibold dark:text-white mb-2">{{ item.name }}</h3>
            <p class="text-gray-600 dark:text-gray-300 mb-4 text-sm">{{ item.desc }}</p >
            <div class="flex gap-2">
              <a class="btn-sm" :href="item.demo" target="_blank">预览</a >
              <a class="btn-sm-outline" :href="item.code" target="_blank">源码</a >
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- 联系我 -->
    <section id="contact" class="py-20">
      <div class="max-w-3xl mx-auto px-4 text-center">
        <h2 class="section-title">联系我</h2>
        <p class="text-gray-600 dark:text-gray-300 mb-8">期待与你合作交流</p >
        <div class="bg-white dark:bg-gray-800 shadow-md rounded-lg p-6">
          <input type="text" placeholder="你的名字" class="input mb-4" />
          <input type="email" placeholder="你的邮箱" class="input mb-4" />
          <textarea placeholder="留言内容" rows="4" class="input mb-4"></textarea>
          <button class="btn-primary w-full">提交留言</button>
        </div>
      </div>
    </section>

    <!-- 页脚 -->
    <footer class="py-6 text-center text-gray-500 dark:text-gray-400 text-sm">
      © 2026 MyPortfolio | 前端个人作品集
    </footer>

  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const isDark = ref(false)

const toggleDark = () => {
  isDark.value = !isDark.value
  document.documentElement.classList.toggle('dark')
}

const projects = ref([
  {
    id: 1,
    name: 'Vue3 个人作品集',
    desc: '响应式作品集 + 后台管理',
    demo: '#',
    code: '#'
  },
  {
    id: 2,
    name: '后台管理系统',
    desc: '权限、表单、表格、路由守卫',
    demo: '#',
    code: '#'
  },
  {
    id: 3,
    name: '移动端 H5 项目',
    desc: '适配移动端、流畅交互',
    demo: '#',
    code: '#'
  }
])

onMounted(() => {
  if (window.matchMedia('(prefers-color-scheme: dark)').matches) {
    isDark.value = true
    document.documentElement.classList.add('dark')
  }
})
</script>

<style scoped>
.nav-link {
  @apply text-gray-700 dark:text-gray-200 hover:text-blue-600 dark:hover:text-blue-400 font-medium transition-colors;
}

.section-title {
  @apply text-3xl font-bold text-center mb-12 text-gray-800 dark:text-white;
}

.btn-primary {
  @apply bg-blue-600 text-white px-6 py-3 rounded-lg hover:bg-blue-700 transition-colors;
}

.btn-outline {
  @apply border border-blue-600 text-blue-600 px-6 py-3 rounded-lg hover:bg-blue-50 dark:hover:bg-gray-700 transition-colors;
}

.btn-sm {
  @apply bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700 text-sm transition-colors;
}

.btn-sm-outline {
  @apply border border-blue-600 text-blue-600 px-4 py-2 rounded hover:bg-blue-50 dark:hover:bg-gray-700 text-sm transition-colors;
}

.input {
  @apply w-full border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-700 text-gray-900 dark:text-white rounded-lg px-4 py-2 outline-none focus:ring-2 focus:ring-blue-500;
}

.skill-card {
  @apply bg-white dark:bg-gray-800 shadow-sm rounded-lg p-6 text-center font-medium text-gray-800 dark:text-white hover:scale-105 transition-transform;
}

.project-card {
  @apply bg-white dark:bg-gray-800 shadow-md rounded-lg p-6 hover:shadow-lg transition-shadow;
}

.tag {
  @apply bg-blue-100 dark:bg-blue-900 text-blue-700 dark:text-blue-300 px-3 py-1 rounded-full text-sm;
}
</style>