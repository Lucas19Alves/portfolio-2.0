<script setup lang="ts">
import emailjs from '@emailjs/browser';
import { onMounted } from 'vue';

onMounted(() => {
  emailjs.init('cu17r5y9QKLHIvYoR');
});

const sendEmail = (event: Event) => {
  event.preventDefault();

  const form = event.target as HTMLFormElement;

  emailjs.sendForm('service_3g23jfi', 'template_y7ontwx', form)
    .then(() => {
      alert('Mensagem enviada com sucesso!');
      form.reset();
    })
    .catch((error) => {
      console.error('Erro ao enviar mensagem:', error);
      alert('Erro ao enviar a mensagem.');
    });
};
</script>


<template>
  <section id="contato" class="section-padding bg-gray-50 dark:bg-gray-800 transition-colors duration-300">
    <div class="container mx-auto px-4">
      <!-- Título -->
      <div class="text-center mb-12" data-aos="fade-up">
        <h2 class="text-4xl font-bold text-gray-800 dark:text-white mb-4">
          Entre em Contato
        </h2>
        <p class="text-gray-600 dark:text-gray-400 max-w-xl mx-auto">
          Tem alguma ideia ou projeto em mente? Vamos conversar e transformar isso em realidade.
        </p>
      </div>

      <!-- Formulário e Info -->
      <div class="max-w-4xl mx-auto grid md:grid-cols-2 gap-12">
        <!-- Informações de Contato -->
        <div class="space-y-8" data-aos="fade-right">
          <div>
            <h3 class="text-2xl font-bold text-gray-800 dark:text-white mb-6">Informações</h3>
            <div class="space-y-4">
              <div class="flex items-center gap-4 text-gray-600 dark:text-gray-400">
                <div class="w-12 h-12 bg-blue-100 dark:bg-blue-900/30 text-primary rounded-xl flex items-center justify-center">
                  <i class="fas fa-envelope text-xl"></i>
                </div>
                <div>
                  <p class="text-sm font-semibold text-gray-500 uppercase">E-mail</p>
                  <a href="mailto:lucaas19alves@gmail.com" class="text-gray-800 dark:text-gray-200 hover:text-primary transition-colors">lucaas19alves@gmail.com</a>
                </div>
              </div>
              <div class="flex items-center gap-4 text-gray-600 dark:text-gray-400">
                <div class="w-12 h-12 bg-green-100 dark:bg-green-900/30 text-green-600 rounded-xl flex items-center justify-center">
                  <i class="fab fa-whatsapp text-xl"></i>
                </div>
                <div>
                  <p class="text-sm font-semibold text-gray-500 uppercase">WhatsApp</p>
                  <a href="https://wa.me/5511981927567" target="_blank" class="text-gray-800 dark:text-gray-200 hover:text-green-500 transition-colors">+55 11 98192-7567</a>
                </div>
              </div>
              <div class="flex items-center gap-4 text-gray-600 dark:text-gray-400">
                <div class="w-12 h-12 bg-purple-100 dark:bg-purple-900/30 text-purple-600 rounded-xl flex items-center justify-center">
                  <i class="fas fa-location-dot text-xl"></i>
                </div>
                <div>
                  <p class="text-sm font-semibold text-gray-500 uppercase">Localização</p>
                  <span class="text-gray-800 dark:text-gray-200">São Paulo, SP - Brasil</span>
                </div>
              </div>
            </div>
          </div>

          <!-- Redes Sociais -->
          <div>
            <h4 class="text-lg font-bold text-gray-800 dark:text-white mb-4">Redes Sociais</h4>
            <div class="flex gap-4">
              <a href="https://github.com/Lucas19Alves" target="_blank" class="w-10 h-10 bg-white dark:bg-gray-700 shadow-md flex items-center justify-center rounded-lg text-gray-700 dark:text-gray-200 hover:bg-primary hover:text-white dark:hover:bg-primary transition-all">
                <i class="fab fa-github"></i>
              </a>
              <a href="https://www.linkedin.com/in/lucaas19alves/" target="_blank" class="w-10 h-10 bg-white dark:bg-gray-700 shadow-md flex items-center justify-center rounded-lg text-gray-700 dark:text-gray-200 hover:bg-primary hover:text-white dark:hover:bg-primary transition-all">
                <i class="fab fa-linkedin-in"></i>
              </a>
            </div>
          </div>
        </div>

        <!-- Formulário -->
        <div class="bg-white dark:bg-gray-900 p-8 rounded-2xl shadow-xl" data-aos="fade-left">
          <form id="contactForm" @submit="sendEmail" class="space-y-4">
            <div>
              <label for="name" class="block text-sm font-semibold text-gray-700 dark:text-gray-300 mb-2">Nome Completo</label>
              <input type="text" id="name" name="name" placeholder="Como devo te chamar?"
                class="w-full px-4 py-3 bg-gray-50 dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl text-gray-700 dark:text-gray-200 focus:ring-2 focus:ring-primary focus:border-transparent transition-all outline-none"
                required autocomplete="name">
            </div>

            <div>
              <label for="email" class="block text-sm font-semibold text-gray-700 dark:text-gray-300 mb-2">Seu E-mail</label>
              <input type="email" id="email" name="email" placeholder="email@exemplo.com"
                class="w-full px-4 py-3 bg-gray-50 dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl text-gray-700 dark:text-gray-200 focus:ring-2 focus:ring-primary focus:border-transparent transition-all outline-none"
                required autocomplete="email">
            </div>

            <div>
              <label for="message" class="block text-sm font-semibold text-gray-700 dark:text-gray-300 mb-2">Sua Mensagem</label>
              <textarea id="message" name="message" rows="4" placeholder="Em que posso te ajudar?"
                class="w-full px-4 py-3 bg-gray-50 dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl text-gray-700 dark:text-gray-200 focus:ring-2 focus:ring-primary focus:border-transparent transition-all outline-none resize-none"
                required></textarea>
            </div>

            <button type="submit"
              class="w-full bg-primary hover:bg-secondary text-white font-bold py-4 rounded-xl shadow-lg shadow-blue-500/30 transition-all duration-300 transform hover:-translate-y-1">
              Enviar Mensagem
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>



<style>
input,
textarea {
  transition: box-shadow 0.3s ease-in-out;
}

input:focus,
textarea:focus {
  box-shadow: 0 0 0 2px #3b82f6;
}
</style>
