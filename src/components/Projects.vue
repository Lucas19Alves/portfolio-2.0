<script setup lang="ts">
type Projeto = {
  titulo: string;
  descricao: string;
  tecnologias: string[];
  imagem: string;
  alt: string;
  github?: string;
  demo: string;
  demoLabel?: string;
  openSource?: boolean;
  destaques?: string[];
  contain?: boolean;
};

const img = (nome: string) => new URL(`../assets/${nome}`, import.meta.url).href;

const destaques: Projeto[] = [
  {
    titulo: 'Dev Room',
    descricao: 'Um desktop de produtividade para desenvolvedores no navegador: tarefas, Kanban, notas, Pomodoro e mais de 15 utilitários de dev em janelas organizáveis, com atalho Ctrl+K para abrir qualquer ferramenta.',
    destaques: [
      'Login com GitHub (OAuth com PKCE) e backup sincronizado em repositório privado',
      'Mescla entre dispositivos ferramenta a ferramenta, sem perder alterações',
      'Assistente de IA com a chave do próprio usuário (OpenAI, Claude, Gemini e outros)',
    ],
    tecnologias: ['Vue 3', 'Vite', 'JavaScript', 'GitHub OAuth', 'Vercel Functions', 'Docker'],
    imagem: img('dev-room.jpg'),
    alt: 'Área de trabalho do Dev Room com atalhos para tarefas, Pomodoro, notas e snippets',
    github: 'https://github.com/Lucas19Alves/dev-room',
    demo: 'https://dev-room-three.vercel.app/',
    demoLabel: 'Abrir o Dev Room',
    openSource: true,
    contain: true,
  },
  {
    titulo: 'Sítio Mutirão',
    descricao: 'Jogo cooperativo de fazenda em 3D para 2 a 4 pessoas, direto no navegador. Todos cuidam da mesma propriedade: coletam, plantam, produzem em cadeia e erguem prédios juntos.',
    destaques: [
      'Mundo 3D com Three.js: 25 prédios e personagens com esqueleto gerados por código',
      'Multiplayer em tempo real e chat de voz com Supabase Realtime',
      'Trilha sonora generativa em Web Audio e instalação como app (PWA)',
    ],
    tecnologias: ['Three.js', 'React 19', 'TypeScript', 'Supabase', 'WebAudio', 'Playwright'],
    imagem: img('sitio-mutirao.webp'),
    alt: 'Prédios 3D do Sítio Mutirão: celeiro, casas, barracas de feira e estufa',
    github: 'https://github.com/Lucas19Alves/sitio-mutirao',
    demo: 'https://sitio-mutirao.vercel.app/',
    demoLabel: 'Jogar agora',
    openSource: true,
  },
];

const projetos: Projeto[] = [
  {
    titulo: 'Véspera Convites',
    descricao: 'Estúdio de convites digitais animados para casamentos, aniversários e chás. Site, simulador de preço e convites interativos com confirmação de presença.',
    tecnologias: ['HTML', 'CSS', 'JavaScript', 'GSAP', 'Vercel'],
    imagem: img('vespera.webp'),
    alt: 'Página inicial da Véspera com um envelope lacrado',
    demo: 'https://vesperaconvites.vercel.app/',
    demoLabel: 'Visitar site',
  },
  {
    titulo: 'Dashboard TI',
    descricao: 'Painel para auditorias de estoque e controle de validades no varejo. Transforma planilhas do ERP em indicadores, agenda semanal e listas de conferência, tudo offline.',
    tecnologias: ['Vue 3', 'Tailwind CSS', 'Dexie.js', 'PWA'],
    imagem: img('dashboard-ti.webp'),
    alt: 'Tela inicial do Dashboard TI com agenda de auditorias e indicadores',
    github: 'https://github.com/Lucas19Alves/dashboard-ti',
    demo: 'https://dashboard-ti.vercel.app/',
  },
  {
    titulo: 'Gerador de QR Code',
    descricao: 'QR Codes de links, WhatsApp, Wi-Fi e e-mail com prévia instantânea, cores personalizadas e download em PNG ou SVG.',
    tecnologias: ['Vue 3', 'Vite', 'qrcode'],
    imagem: img('qrcode.webp'),
    alt: 'Gerador de QR Code com formulário e prévia do código',
    github: 'https://github.com/Lucas19Alves/gerador-qr-code',
    demo: 'https://gerador-qr-code-plum.vercel.app/',
  },
  {
    titulo: 'Gerador de Currículo',
    descricao: 'Currículo em 5 etapas com 5 modelos e prévia em tempo real. Exporta PDF com texto selecionável, legível por sistemas de recrutamento.',
    tecnologias: ['Vue 3', 'Tailwind CSS', 'Vuedraggable'],
    imagem: img('curriculo.webp'),
    alt: 'Gerador de Currículo com formulário e prévia de um currículo preenchido',
    github: 'https://github.com/Lucas19Alves/gerador-curriculo',
    demo: 'https://gerador-curriculo-rho.vercel.app/',
  },
];
</script>

<template>
  <section id="projetos" class="section-padding bg-white dark:bg-gray-900 transition-colors duration-300">
    <div class="container mx-auto px-4">
      <div class="max-w-2xl mb-14" data-aos="fade-up">
        <h2 class="text-4xl font-bold text-gray-800 dark:text-white mb-4">Projetos</h2>
        <p class="text-gray-600 dark:text-gray-400">
          Produtos que estão no ar e que eu mantenho. Os dois primeiros são open source: o código está aberto para estudar, usar e contribuir.
        </p>
      </div>

      <!-- Destaques -->
      <div class="space-y-10 lg:space-y-16 mb-24">
        <article
          v-for="(p, i) in destaques"
          :key="p.titulo"
          class="grid lg:grid-cols-[1.15fr_1fr] gap-0 rounded-3xl overflow-hidden bg-gray-50 dark:bg-gray-800 border border-gray-200 dark:border-gray-700"
          data-aos="fade-up"
        >
          <a
            :href="p.demo"
            target="_blank"
            rel="noopener noreferrer"
            :class="['relative block min-h-[240px] sm:min-h-[340px] bg-slate-100 dark:bg-gray-950 overflow-hidden', i % 2 ? 'lg:order-2' : '']"
            :aria-label="`${p.demoLabel ?? 'Abrir'}: ${p.titulo}`"
          >
            <img :src="p.imagem" :alt="p.alt" loading="lazy" width="1280" height="800" :class="['absolute inset-0 w-full h-full', p.contain ? 'object-contain p-4 lg:p-6' : 'object-cover']">
          </a>

          <div class="p-8 lg:p-12 flex flex-col">
            <div class="flex flex-wrap items-center gap-2 mb-5">
              <span v-if="p.openSource" class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-sm font-semibold bg-emerald-100 text-emerald-800 dark:bg-emerald-900/40 dark:text-emerald-300">
                <i class="fa-solid fa-code-branch" aria-hidden="true"></i> Open source
              </span>
              <span class="text-sm text-gray-500 dark:text-gray-400">Em destaque</span>
            </div>

            <h3 class="text-3xl lg:text-4xl font-bold mb-4 text-gray-900 dark:text-white tracking-tight">{{ p.titulo }}</h3>
            <p class="text-lg text-gray-600 dark:text-gray-300 mb-6 leading-relaxed">{{ p.descricao }}</p>

            <ul class="space-y-2 mb-8 text-gray-700 dark:text-gray-300">
              <li v-for="d in p.destaques" :key="d" class="flex gap-3">
                <i class="fa-solid fa-check text-primary mt-1.5 text-sm" aria-hidden="true"></i>
                <span>{{ d }}</span>
              </li>
            </ul>

            <div class="flex flex-wrap gap-2 mb-8">
              <span v-for="tech in p.tecnologias" :key="tech" class="px-3 py-1 bg-blue-100 dark:bg-blue-900/40 text-blue-800 dark:text-blue-200 rounded-lg text-sm font-medium">
                {{ tech }}
              </span>
            </div>

            <div class="mt-auto flex flex-col sm:flex-row gap-3">
              <a :href="p.demo" target="_blank" rel="noopener noreferrer"
                 class="flex-1 text-center bg-primary hover:bg-secondary text-white px-6 py-3.5 rounded-xl font-bold transition-colors focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-primary">
                <i class="fas fa-arrow-up-right-from-square mr-2" aria-hidden="true"></i>{{ p.demoLabel }}
              </a>
              <a v-if="p.github" :href="p.github" target="_blank" rel="noopener noreferrer"
                 class="flex-1 text-center bg-gray-900 dark:bg-white text-white dark:text-gray-900 hover:opacity-90 px-6 py-3.5 rounded-xl font-bold transition-opacity focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-primary">
                <i class="fab fa-github mr-2" aria-hidden="true"></i>Ver o código
              </a>
            </div>
          </div>
        </article>
      </div>

      <!-- Demais projetos -->
      <h3 class="text-2xl font-bold text-gray-800 dark:text-white mb-8" data-aos="fade-up">Outros projetos</h3>

      <div class="grid sm:grid-cols-2 xl:grid-cols-4 gap-6">
        <article
          v-for="p in projetos"
          :key="p.titulo"
          class="group flex flex-col bg-gray-50 dark:bg-gray-800 rounded-2xl overflow-hidden border border-gray-200 dark:border-gray-700"
        >
          <a :href="p.demo" target="_blank" rel="noopener noreferrer" tabindex="-1" aria-hidden="true" class="block aspect-[16/10] overflow-hidden bg-slate-100 dark:bg-gray-950">
            <img :src="p.imagem" :alt="p.alt" loading="lazy" width="1280" height="800" class="w-full h-full object-cover object-top transition-transform duration-500 group-hover:scale-105">
          </a>

          <div class="p-5 flex flex-col flex-1">
            <h4 class="text-lg font-bold mb-2 text-gray-900 dark:text-gray-100">{{ p.titulo }}</h4>
            <p class="text-gray-600 dark:text-gray-400 mb-4 text-sm leading-relaxed">{{ p.descricao }}</p>
            <div class="flex flex-wrap gap-1.5 mb-5">
              <span v-for="tech in p.tecnologias" :key="tech" class="px-2 py-0.5 bg-blue-100 dark:bg-blue-900/30 text-blue-800 dark:text-blue-200 rounded-md text-xs font-medium">
                {{ tech }}
              </span>
            </div>
            <div class="mt-auto flex gap-4 text-sm font-semibold">
              <a :href="p.demo" target="_blank" rel="noopener noreferrer" class="text-primary hover:underline underline-offset-4">
                {{ p.demoLabel ?? 'Ver online' }}
              </a>
              <a v-if="p.github" :href="p.github" target="_blank" rel="noopener noreferrer" class="text-gray-700 dark:text-gray-300 hover:underline underline-offset-4">
                Código
              </a>
            </div>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>
