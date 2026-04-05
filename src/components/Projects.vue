<script setup lang="ts">
const destaque = {
  titulo: 'Dev Room',
  descricao: 'Uma plataforma completa projetada para maximizar a produtividade de desenvolvedores. O Dev Room oferece um ambiente de trabalho otimizado com ferramentas de gerenciamento de tarefas, cronômetro Pomodoro integrado e uma interface minimalista que elimina distrações, permitindo foco total no código.',
  tecnologias: ['Vite', 'JavaScript', 'NodeJS', 'VueJS', 'TailwindCSS' , 'API', 'Supabase'],
  imagem: new URL('../assets/devroom.png', import.meta.url).href,
  github: 'https://github.com/Lucas19Alves/dev-room',
  demo: 'https://dev-room-three.vercel.app/'
};

const projetos = [
  {
    titulo: 'Cardápio dígital',
    descricao: 'Cardápio interativo para lanchonetes com sistema de pedidos via WhatsApp e controle de horário.',
    tecnologias: ['JavaScript', 'TailwindCSS', 'API'],
    imagem: new URL('../assets/cardapio.png', import.meta.url).href,
    github: 'https://github.com/Lucas19Alves/cardapio',
    demo: 'https://cardapio-flax-five.vercel.app/'
  },
  {
    titulo: 'Gerador de Currículo',
    descricao: 'Ferramenta prática para criação de currículos profissionais com exportação direta para PDF.',
    tecnologias: ['JavaScript', 'HTML/CSS'],
    imagem: new URL('../assets/curriculo.png', import.meta.url).href,
    github: 'https://github.com/Lucas19Alves/gerador-curriculo',
    demo: 'https://gerador-curriculo-bice.vercel.app/'
  },
  {
    titulo: 'Gerador de QRCode',
    descricao: 'Aplicação para geração dinâmica de QRCodes personalizáveis com suporte a download.',
    tecnologias: ['VueJS', 'NodeJS', 'Express', 'API'],
    imagem: new URL('../assets/qrcode.png', import.meta.url).href,
    github: 'https://github.com/Lucas19Alves/gerador-qr-code',
    demo: 'https://gerador-qr-code-plum.vercel.app/'
  },
  {
    titulo: 'Landing Page Tech',
    descricao: 'Landing page moderna e responsiva para empresas de tecnologia, com foco em conversão.',
    tecnologias: ['React', 'TailwindCSS' , 'Framer Motion'],
    imagem: new URL('../assets/landing.png', import.meta.url).href,
    github: 'https://github.com/Lucas19Alves/sunshine-sol',
    demo: 'https://sunshine-sol-build.vercel.app/'
  },
];
</script>

<template>
  <section id="projetos" class="section-padding bg-white dark:bg-gray-900 transition-colors duration-300">
    <div class="container mx-auto px-4">
      <div class="text-center mb-16" data-aos="fade-up">
        <h2 class="text-4xl font-bold text-gray-800 dark:text-white mb-4">Meus Projetos</h2>
        <p class="text-gray-600 dark:text-gray-400 max-w-2xl mx-auto">
          Uma seleção dos meus trabalhos mais recentes, demonstrando minha evolução técnica e criatividade.
        </p>
      </div>
      
      <!-- Projeto em Destaque: Dev Room -->
      <div class="mb-20" data-aos="fade-up">
        <div class="relative bg-gray-50 dark:bg-gray-800 rounded-3xl overflow-hidden border border-gray-100 dark:border-gray-700 shadow-2xl">
          <div class="absolute top-4 left-4 z-20">
            <span class="px-4 py-1.5 bg-primary text-white text-xs font-bold uppercase tracking-widest rounded-full shadow-lg">
              PROJETO EM DESTAQUE
            </span>
          </div>
          
          <div class="grid lg:grid-cols-2 items-center">
            <div class="relative overflow-hidden group h-64 lg:h-full">
              <img :src="destaque.imagem" :alt="destaque.titulo" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105">
              <div class="absolute inset-0 bg-black/20 group-hover:bg-black/10 transition-colors"></div>
            </div>
            
            <div class="p-8 lg:p-12">
              <h3 class="text-3xl lg:text-4xl font-bold mb-6 text-gray-800 dark:text-white group-hover:text-primary transition-colors">
                {{ destaque.titulo }}
              </h3>
              <p class="text-lg text-gray-600 dark:text-gray-400 mb-8 leading-relaxed">
                {{ destaque.descricao }}
              </p>
              
              <div class="flex flex-wrap gap-2 mb-8">
                <span v-for="tech in destaque.tecnologias" 
                      :key="tech"
                      class="px-4 py-1.5 bg-blue-100 dark:bg-blue-900/40 text-blue-700 dark:text-blue-300 rounded-xl text-sm font-semibold">
                  {{ tech }}
                </span>
              </div>
              
              <div class="flex flex-col sm:flex-row gap-4">
                <a :href="destaque.demo" target="_blank" 
                   class="flex-1 text-center bg-primary hover:bg-secondary text-white px-6 py-4 rounded-xl font-bold transition-all shadow-lg shadow-blue-500/30 transform hover:-translate-y-1">
                  <i class="fas fa-external-link-alt mr-2"></i> Ver Demo Online
                </a>
                <a :href="destaque.github" target="_blank" 
                   class="flex-1 text-center bg-gray-200 dark:bg-gray-700 hover:bg-gray-300 dark:hover:bg-gray-600 text-gray-800 dark:text-white px-6 py-4 rounded-xl font-bold transition-all transform hover:-translate-y-1">
                  <i class="fab fa-github mr-2"></i> Repositório GitHub
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Outros Projetos -->
      <h3 class="text-2xl font-bold text-gray-800 dark:text-white mb-10 text-center lg:text-left" data-aos="fade-up">Outras Criações</h3>
      
      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
        <div 
          v-for="(projeto, index) in projetos" 
          :key="projeto.titulo"
          class="group bg-gray-50 dark:bg-gray-800 rounded-2xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-2 border border-transparent dark:border-gray-700"
          data-aos="fade-up"
          :data-aos-delay="index * 100"
        >
          <div class="relative overflow-hidden h-40">
            <img :src="projeto.imagem" :alt="projeto.titulo" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110">
            <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-4">
              <div class="flex space-x-2 w-full">
                <a :href="projeto.github" target="_blank" class="flex-1 bg-white/20 backdrop-blur-md hover:bg-white/40 text-white py-1.5 rounded-lg text-center text-xs font-medium transition-colors">
                  GitHub
                </a>
                <a :href="projeto.demo" target="_blank" class="flex-1 bg-primary hover:bg-secondary text-white py-1.5 rounded-lg text-center text-xs font-medium transition-colors">
                  Demo
                </a>
              </div>
            </div>
          </div>

          <div class="p-5">
            <h4 class="text-lg font-bold mb-2 text-gray-800 dark:text-gray-100 group-hover:text-primary transition-colors line-clamp-1">
              {{ projeto.titulo }}
            </h4>
            <p class="text-gray-600 dark:text-gray-400 mb-4 text-xs line-clamp-2">
              {{ projeto.descricao }}
            </p>
            <div class="flex flex-wrap gap-1.5">
              <span v-for="tech in projeto.tecnologias" 
                    :key="tech"
                    class="px-2 py-0.5 bg-blue-100 dark:bg-blue-900/30 text-blue-700 dark:text-blue-300 rounded-md text-[10px] font-bold">
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css');

.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.line-clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
