<script setup lang="ts">
const skillCategories = [
  {
    title: 'Frontend',
    icon: 'fa-solid fa-code',
    color: 'text-blue-600',
    bgColor: 'bg-blue-50 dark:bg-blue-900/20',
    skills: ['Vue.js / Nuxt.js', 'React / Next.js', 'TypeScript', 'Tailwind CSS', 'Gerenciamento de Estado', 'Testes (Vitest/Jest)', 'Otimização de Performance']
  },
  {
    title: 'Backend',
    icon: 'fa-solid fa-server',
    color: 'text-green-600',
    bgColor: 'bg-green-50 dark:bg-green-900/20',
    skills: ['Node.js / NestJS', 'Python (FastAPI)', 'PostgreSQL / MySQL', 'MongoDB / Redis', 'Microserviços', 'APIs RESTful & GraphQL', 'Arquitetura Serverless']
  },
  {
    title: 'Análise de Dados',
    icon: 'fa-solid fa-chart-line',
    color: 'text-orange-600',
    bgColor: 'bg-orange-50 dark:bg-orange-900/20',
    skills: ['Python (Pandas/NumPy)', 'SQL Avançado', 'Power BI / Tableau', 'Visualização de Dados', 'Processos ETL', 'Conceitos de Big Data', 'Google Analytics']
  },
  {
    title: 'DevOps & Design',
    icon: 'fa-solid fa-screwdriver-wrench',
    color: 'text-purple-600',
    bgColor: 'bg-purple-50 dark:bg-purple-900/20',
    skills: ['Git & GitHub', 'Docker / Kubernetes', 'AWS / Azure', 'Pipelines CI/CD', 'Linux (Bash)', 'Figma (Design Systems)', 'Metodologias Ágeis']
  }
];
</script>

<template>
  <section id="skills" class="section-padding bg-gray-50 dark:bg-gray-800 transition-colors duration-300">
    <div class="container mx-auto">
      <div class="text-center mb-16" data-aos="fade-up">
        <h2 class="text-4xl font-bold text-gray-800 dark:text-white mb-4">Habilidades Técnicas</h2>
        <p class="text-gray-600 dark:text-gray-400 max-w-2xl mx-auto">
          Conjunto de tecnologias e ferramentas que utilizo para construir soluções digitais de alto impacto e performance, sempre alinhado com as demandas do mercado.
        </p>
      </div>
      
      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
        <div 
          v-for="(category, index) in skillCategories" 
          :key="category.title"
          class="bg-white dark:bg-gray-900 p-6 rounded-2xl shadow-xl border border-transparent dark:border-gray-700 hover:border-primary/30 transition-all duration-300"
          data-aos="fade-up"
          :data-aos-delay="index * 150"
        >
          <div class="flex items-center mb-8">
            <div :class="['w-10 h-10 rounded-xl flex items-center justify-center mr-3 shrink-0', category.bgColor]">
              <i :class="[category.icon, category.color, 'text-lg']"></i>
            </div>
            <h3 class="text-xl font-bold text-gray-800 dark:text-white leading-tight">{{ category.title }}</h3>
          </div>
          
          <div class="flex flex-wrap gap-2">
            <span 
              v-for="skill in category.skills" 
              :key="skill"
              class="px-3 py-1.5 bg-gray-50 dark:bg-gray-800 text-gray-700 dark:text-gray-300 rounded-lg text-xs font-medium border border-gray-100 dark:border-gray-700 hover:bg-primary hover:text-white dark:hover:bg-primary transition-all duration-200 cursor-default"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
