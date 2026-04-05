<script setup lang="ts">
import { ref, onMounted } from 'vue';

const roles = ['Desenvolvedor Front End', 'Full Stack Developer', 'Freelancer'];
const currentRoleIndex = ref(0);
const displayedRole = ref('');
const isDeleting = ref(false);
const typeSpeed = ref(150);

const type = () => {
  const currentRole = roles[currentRoleIndex.value];
  
  if (isDeleting.value) {
    displayedRole.value = currentRole.substring(0, displayedRole.value.length - 1);
    typeSpeed.value = 75;
  } else {
    displayedRole.value = currentRole.substring(0, displayedRole.value.length + 1);
    typeSpeed.value = 150;
  }

  if (!isDeleting.value && displayedRole.value === currentRole) {
    isDeleting.value = true;
    typeSpeed.value = 2000; // Pause at end
  } else if (isDeleting.value && displayedRole.value === '') {
    isDeleting.value = false;
    currentRoleIndex.value = (currentRoleIndex.value + 1) % roles.length;
    typeSpeed.value = 500;
  }

  setTimeout(type, typeSpeed.value);
};

onMounted(() => {
  type();
});
</script>

<template>
  <section id="inicio" class="relative min-h-screen flex items-center section-padding overflow-hidden bg-white dark:bg-gray-900 transition-colors duration-300">
    <!-- Background Decorativo -->
    <div class="absolute inset-0 z-0">
      <div class="absolute top-0 right-0 w-1/2 h-1/2 bg-blue-50 dark:bg-blue-900/10 rounded-full blur-3xl -translate-y-1/2 translate-x-1/2 opacity-50"></div>
      <div class="absolute bottom-0 left-0 w-1/3 h-1/3 bg-blue-100 dark:bg-blue-800/10 rounded-full blur-3xl translate-y-1/2 -translate-x-1/2 opacity-50"></div>
    </div>

    <div class="container mx-auto relative z-10">
      <div class="flex flex-col lg:flex-row items-center justify-between gap-12">
        <div class="flex-1 text-center lg:text-left">
          <span class="inline-block px-4 py-1.5 mb-6 text-sm font-semibold tracking-wider text-primary uppercase bg-blue-50 dark:bg-blue-900/30 rounded-full" data-aos="fade-down">
            Bem-vindo ao meu portfólio
          </span>
          <h1 class="text-4xl md:text-6xl font-extrabold mb-6 text-gray-900 dark:text-white leading-tight" data-aos="fade-up" data-aos-delay="100">
            Olá, eu sou o <span class="text-primary">Lucas</span>
          </h1>
          <div class="h-12 md:h-16 mb-8" data-aos="fade-up" data-aos-delay="200">
            <span class="text-2xl md:text-4xl font-bold text-gray-700 dark:text-gray-300">
              {{ displayedRole }}<span class="animate-pulse">|</span>
            </span>
          </div>
          <p class="text-lg text-gray-600 dark:text-gray-400 mb-10 max-w-2xl mx-auto lg:mx-0" data-aos="fade-up" data-aos-delay="300">
            Especialista em criar interfaces modernas, responsivas e intuitivas. Foco em proporcionar a melhor experiência para o usuário final.
          </p>
          <div class="flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4" data-aos="fade-up" data-aos-delay="400">
            <a href="#contato"
              class="w-full sm:w-auto px-8 py-4 bg-primary hover:bg-secondary text-white font-bold rounded-xl shadow-lg shadow-blue-500/30 hover:shadow-blue-600/40 transition-all duration-300 transform hover:-translate-y-1">
              Vamos conversar!
            </a>
            <div class="flex items-center gap-6 mt-4 sm:mt-0 px-4">
              <a href="https://wa.me/5511981927567" target="_blank" class="text-gray-600 dark:text-gray-400 hover:text-green-500 transition-colors">
                <i class="fa-brands fa-whatsapp fa-2xl"></i>
              </a>
              <a href="https://github.com/Lucas19Alves" target="_blank" class="text-gray-600 dark:text-gray-400 hover:text-black dark:hover:text-white transition-colors">
                <i class="fa-brands fa-github fa-2xl"></i>
              </a>
              <a href="https://www.linkedin.com/in/lucaas19alves/" target="_blank" class="text-gray-600 dark:text-gray-400 hover:text-blue-600 transition-colors">
                <i class="fa-brands fa-linkedin fa-2xl"></i>
              </a>
            </div>
          </div>
        </div>
        
        <div class="flex-1 relative" data-aos="zoom-in" data-aos-delay="200">
          <div class="relative w-64 h-64 md:w-80 md:h-80 mx-auto">
            <!-- Circulos decorativos atrás da foto -->
            <div class="absolute inset-0 bg-primary/20 rounded-full animate-ping"></div>
            <div class="absolute -inset-4 border-2 border-primary/30 rounded-full border-dashed animate-[spin_10s_linear_infinite]"></div>
            
            <img 
              src="../assets/perfil.jpg" 
              alt="Lucas" 
              class="relative z-10 w-full h-full object-cover rounded-full border-4 border-white dark:border-gray-800 shadow-2xl shadow-primary/20"
            >
          </div>
        </div>
      </div>
    </div>
    
    <!-- Botão de scroll para baixo -->
    <div class="absolute bottom-10 left-1/2 -translate-x-1/2 animate-bounce hidden lg:block">
      <a href="#about" class="text-gray-400 hover:text-primary transition-colors">
        <i class="fa-solid fa-chevron-down fa-2x"></i>
      </a>
    </div>
  </section>
</template>

<style>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css');
</style>

