<template>
  <footer class="bg-gray-900 dark:bg-black text-white py-12 transition-colors duration-300">
    <div class="container mx-auto px-4 text-center">
      <div class="mb-8">
        <h3 class="text-2xl font-bold mb-4">Lucas Alves</h3>
        <p class="text-gray-400 max-w-md mx-auto">
          Desenvolvedor Front End focado em criar experiências digitais incríveis.
        </p>
      </div>
      <div class="flex justify-center space-x-6 mb-8">
        <a href="https://wa.me/5511981927567" target="_blank" class="w-12 h-12 bg-gray-800 hover:bg-green-500 rounded-full flex items-center justify-center transition-all duration-300">
          <i class="fab fa-whatsapp text-xl"></i>
        </a>
        <a href="https://github.com/Lucas19Alves" target="_blank" class="w-12 h-12 bg-gray-800 hover:bg-gray-700 rounded-full flex items-center justify-center transition-all duration-300">
          <i class="fab fa-github text-xl"></i>
        </a>
        <a href="https://www.linkedin.com/in/lucaas19alves/" target="_blank" class="w-12 h-12 bg-gray-800 hover:bg-blue-600 rounded-full flex items-center justify-center transition-all duration-300">
          <i class="fab fa-linkedin-in text-xl"></i>
        </a>
      </div>
      <div class="border-t border-gray-800 pt-8">
        <p class="text-gray-500 text-sm">
          &copy; {{ new Date().getFullYear() }} Lucas Alves. Todos os direitos reservados.
        </p>
      </div>
    </div>
  </footer>
</template>

<!-- Importar FontAwesome -->
<style>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css');
</style>