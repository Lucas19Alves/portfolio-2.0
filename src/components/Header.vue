<script setup lang="ts">
import { ref } from 'vue';
import ThemeToggle from './ThemeToggle.vue';

const menuAberto = ref(false);

const itensMenu = [
  { nome: 'Início', link: '#inicio' },
  { nome: 'Sobre', link: '#about' },
  { nome: 'Habilidades', link: '#skills' },
  { nome: 'Projetos', link: '#projetos' },
  { nome: 'Contato', link: '#contato' },
];
</script>

<template>
  <header class="fixed w-full bg-white/90 dark:bg-gray-900/90 backdrop-blur-sm shadow-sm z-50 transition-colors duration-300">
    <nav class="container mx-auto px-4 py-4">
      <div class="flex justify-between items-center">
        <a href="#" class="text-2xl font-bold gradient-text">Lucas Alves</a>

        <!-- Menu para Desktop -->
        <div class="hidden md:flex items-center space-x-8">
          <a v-for="item in itensMenu" :key="item.nome" :href="item.link"
            class="text-gray-700 dark:text-gray-300 hover:text-primary dark:hover:text-primary transition-colors">
            {{ item.nome }}
          </a>
          <ThemeToggle />
        </div>

        <!-- Botão do Menu Mobile e Toggle -->
        <div class="flex items-center space-x-4 md:hidden">
          <ThemeToggle />
          <button 
            @click="menuAberto = !menuAberto" 
            class="text-gray-700 dark:text-gray-300 p-2"
            :aria-label="menuAberto ? 'Fechar menu' : 'Abrir menu'"
            :aria-expanded="menuAberto"
          >
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path v-if="!menuAberto" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16" />
              <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </div>

      <!-- Menu Mobile -->
      <div v-show="menuAberto" class="md:hidden">
        <div class="flex flex-col space-y-4 pt-4 pb-3">
          <a v-for="item in itensMenu" :key="item.nome" :href="item.link" @click="menuAberto = false"
            class="text-gray-700 dark:text-gray-300 hover:text-primary dark:hover:text-primary transition-colors">
            {{ item.nome }}
          </a>
        </div>
      </div>
    </nav>
  </header>
</template>
