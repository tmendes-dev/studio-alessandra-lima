<script setup>
import { ref } from 'vue'
import { Menu, X, Instagram, Facebook, Phone, MapPin, Star, Calendar } from 'lucide-vue-next'

// State
const isMenuOpen = ref(false)

// Navigation
const navItems = [
  { name: 'Início', href: '#hero' },
  { name: 'Serviços', href: '#services' },
  { name: 'Sobre', href: '#about' },
  { name: 'Depoimentos', href: '#testimonials' },
  { name: 'Galeria', href: '#gallery' },
  { name: 'Contato', href: '#contact' },
]

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <div class="min-h-screen flex flex-col">
    <!-- Navigation -->
    <nav class="fixed w-full bg-white/90 backdrop-blur-sm z-50 shadow-sm transition-all duration-300">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-20">
          <!-- Logo -->
          <div class="flex-shrink-0 flex items-center">
            <span class="text-2xl font-serif font-bold text-primary">Studio Alessandra Lima</span>
          </div>

          <!-- Desktop Menu -->
          <div class="hidden md:flex space-x-8">
            <a v-for="item in navItems" :key="item.name" :href="item.href" 
               class="text-gray-600 hover:text-primary transition-colors duration-200 font-medium">
              {{ item.name }}
            </a>
            <a href="#contact" class="bg-primary text-white px-6 py-2 rounded-full hover:bg-opacity-90 transition-all shadow-md hover:shadow-lg transform hover:-translate-y-0.5">
              Agendar
            </a>
          </div>

          <!-- Mobile Menu Button -->
          <div class="md:hidden flex items-center">
            <button @click="toggleMenu" class="text-gray-600 hover:text-primary focus:outline-none">
              <Menu v-if="!isMenuOpen" class="h-6 w-6" />
              <X v-else class="h-6 w-6" />
            </button>
          </div>
        </div>
      </div>

      <!-- Mobile Menu -->
      <div v-show="isMenuOpen" class="md:hidden bg-white border-t border-gray-100 absolute w-full">
        <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
          <a v-for="item in navItems" :key="item.name" :href="item.href" 
             @click="isMenuOpen = false"
             class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-primary hover:bg-gray-50">
            {{ item.name }}
          </a>
          <a href="#contact" @click="isMenuOpen = false" class="block w-full text-center mt-4 bg-primary text-white px-6 py-3 rounded-full font-medium">
            Agendar Agora
          </a>
        </div>
      </div>
    </nav>

    <!-- Main Content Placeholder -->
    <main class="flex-grow pt-20">
      <!-- Hero Section -->
      <section id="hero" class="relative min-h-screen flex items-center justify-center overflow-hidden">
        <!-- Background Image with Overlay -->
        <div class="absolute inset-0 z-0">
          <img 
            src="https://images.unsplash.com/photo-1570172619644-dfd03ed5d881?q=80&w=2070&auto=format&fit=crop" 
            alt="Studio Alessandra Lima Interior" 
            class="w-full h-full object-cover"
          />
          <div class="absolute inset-0 bg-white/40 backdrop-blur-[2px]"></div>
          <div class="absolute inset-0 bg-gradient-to-r from-white/90 via-white/70 to-transparent"></div>
        </div>

        <!-- Content -->
        <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 w-full pt-20">
          <div class="max-w-2xl animate-fade-in-up">
            <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/80 backdrop-blur-sm shadow-sm mb-6 border border-primary/20">
              <Star class="w-4 h-4 text-primary fill-primary" />
              <span class="text-sm font-medium text-gray-600 tracking-wide uppercase">Estética Avançada & Bem-estar</span>
            </div>
            
            <h1 class="text-5xl md:text-7xl font-serif font-bold text-dark mb-6 leading-tight">
              Realce sua <br/>
              <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-pink-600">Beleza Natural</span>
            </h1>
            
            <p class="text-xl text-gray-600 mb-10 max-w-lg leading-relaxed">
              Descubra tratamentos personalizados que unem tecnologia e cuidado para revelar sua melhor versão.
            </p>
            
            <div class="flex flex-col sm:flex-row gap-4">
              <a href="#contact" class="group bg-primary text-white px-8 py-4 rounded-full text-lg font-medium hover:bg-opacity-90 transition-all shadow-lg hover:shadow-primary/30 flex items-center justify-center gap-2">
                Agendar Horário
                <Calendar class="w-5 h-5 group-hover:translate-x-1 transition-transform" />
              </a>
              <a href="#services" class="bg-white/80 backdrop-blur-sm text-dark border border-white/50 px-8 py-4 rounded-full text-lg font-medium hover:bg-white transition-all shadow-sm hover:shadow-md flex items-center justify-center">
                Conhecer Serviços
              </a>
            </div>

            <!-- Trust Indicators -->
            <div class="mt-12 flex items-center gap-8 text-gray-500">
              <div class="flex items-center gap-2">
                <div class="flex -space-x-2">
                  <img class="w-8 h-8 rounded-full border-2 border-white" src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=100&h=100&fit=crop" alt="Client" />
                  <img class="w-8 h-8 rounded-full border-2 border-white" src="https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?w=100&h=100&fit=crop" alt="Client" />
                  <img class="w-8 h-8 rounded-full border-2 border-white" src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=100&h=100&fit=crop" alt="Client" />
                </div>
                <span class="text-sm font-medium">+500 Clientes Satisfeitos</span>
              </div>
              <div class="h-4 w-px bg-gray-300"></div>
              <div class="flex items-center gap-2">
                <Star class="w-5 h-5 text-yellow-400 fill-yellow-400" />
                <span class="text-sm font-medium">4.9/5 Avaliação</span>
              </div>
            </div>
          </div>
        </div>
      </section>
      <!-- Services Section -->
      <section id="services" class="py-24 bg-white relative overflow-hidden">
        <!-- Decorative Elements -->
        <div class="absolute top-0 right-0 -mr-20 -mt-20 w-96 h-96 bg-primary/5 rounded-full blur-3xl"></div>
        <div class="absolute bottom-0 left-0 -ml-20 -mb-20 w-96 h-96 bg-blue-50 rounded-full blur-3xl"></div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
          <div class="text-center max-w-3xl mx-auto mb-16">
            <span class="text-primary font-medium tracking-wider uppercase text-sm">Nossos Tratamentos</span>
            <h2 class="text-4xl md:text-5xl font-serif font-bold text-dark mt-3 mb-6">Cuidado Completo para Você</h2>
            <p class="text-gray-600 text-lg">
              Oferecemos uma gama completa de serviços estéticos faciais e corporais, 
              realizados com produtos de alta qualidade e técnicas avançadas.
            </p>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Service Card 1 -->
            <div class="group bg-white rounded-2xl p-8 shadow-sm hover:shadow-xl transition-all duration-300 border border-gray-100 hover:border-primary/20">
              <div class="w-14 h-14 bg-primary/10 rounded-xl flex items-center justify-center mb-6 group-hover:bg-primary group-hover:text-white transition-colors duration-300 text-primary">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-sparkles"><path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"/></svg>
              </div>
              <h3 class="text-xl font-bold text-dark mb-3">Limpeza de Pele</h3>
              <p class="text-gray-600 mb-4">
                Remoção profunda de impurezas, células mortas e cravos, revitalizando sua pele.
              </p>
              <a href="#contact" class="inline-flex items-center text-primary font-medium hover:gap-2 transition-all">
                Saiba mais <span class="ml-1">→</span>
              </a>
            </div>

            <!-- Service Card 2 -->
            <div class="group bg-white rounded-2xl p-8 shadow-sm hover:shadow-xl transition-all duration-300 border border-gray-100 hover:border-primary/20">
              <div class="w-14 h-14 bg-primary/10 rounded-xl flex items-center justify-center mb-6 group-hover:bg-primary group-hover:text-white transition-colors duration-300 text-primary">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-syringe"><path d="m18 2 4 4"/><path d="m17 7 3-3"/><path d="M19 9 8.7 19.3c-1 1-2.5 1-3.4 0l-.6-.6c-1-1-1-2.5 0-3.4L15 5"/><path d="m9 11 4 4"/><path d="m5 19-3 3"/><path d="m14 4 6 6"/></svg>
              </div>
              <h3 class="text-xl font-bold text-dark mb-3">Botox e Preenchimento</h3>
              <p class="text-gray-600 mb-4">
                Procedimentos minimamente invasivos para suavizar linhas de expressão e harmonizar traços.
              </p>
              <a href="#contact" class="inline-flex items-center text-primary font-medium hover:gap-2 transition-all">
                Saiba mais <span class="ml-1">→</span>
              </a>
            </div>

            <!-- Service Card 3 -->
            <div class="group bg-white rounded-2xl p-8 shadow-sm hover:shadow-xl transition-all duration-300 border border-gray-100 hover:border-primary/20">
              <div class="w-14 h-14 bg-primary/10 rounded-xl flex items-center justify-center mb-6 group-hover:bg-primary group-hover:text-white transition-colors duration-300 text-primary">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-flower-2"><path d="M12 5a3 3 0 1 1 3 3m-3-3a3 3 0 1 0-3 3m3-3v18m9-9a3 3 0 0 1-3 3m3-3a3 3 0 0 0-3-3m3 3h-18m9 9a3 3 0 0 1-3-3m3 3a3 3 0 0 0 3-3M3 12a3 3 0 0 1 3-3m-3 3a3 3 0 0 0 3 3"/></svg>
              </div>
              <h3 class="text-xl font-bold text-dark mb-3">Massagem Relaxante</h3>
              <p class="text-gray-600 mb-4">
                Técnicas terapêuticas para aliviar o estresse, dores musculares e promover bem-estar.
              </p>
              <a href="#contact" class="inline-flex items-center text-primary font-medium hover:gap-2 transition-all">
                Saiba mais <span class="ml-1">→</span>
              </a>
            </div>

            <!-- Service Card 4 -->
            <div class="group bg-white rounded-2xl p-8 shadow-sm hover:shadow-xl transition-all duration-300 border border-gray-100 hover:border-primary/20">
              <div class="w-14 h-14 bg-primary/10 rounded-xl flex items-center justify-center mb-6 group-hover:bg-primary group-hover:text-white transition-colors duration-300 text-primary">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-droplets"><path d="M7 16.3c2.2 0 4-1.83 4-4.05 0-1.16-.57-2.26-1.71-3.19S7.29 6.75 7 5.3c-.29 1.45-1.14 2.84-2.29 3.76S3 11.1 3 12.25c0 2.22 1.8 4.05 4 4.05z"/><path d="M12.56 6.6A10.97 10.97 0 0 0 14 3.02c.5 2.5 2 4.9 4 6.5s3 3.5 3 5.5a6.98 6.98 0 0 1-11.91 4.97"/></svg>
              </div>
              <h3 class="text-xl font-bold text-dark mb-3">Drenagem Linfática</h3>
              <p class="text-gray-600 mb-4">
                Estimula o sistema linfático, reduzindo a retenção de líquidos e eliminando toxinas.
              </p>
              <a href="#contact" class="inline-flex items-center text-primary font-medium hover:gap-2 transition-all">
                Saiba mais <span class="ml-1">→</span>
              </a>
            </div>

            <!-- Service Card 5 -->
            <div class="group bg-white rounded-2xl p-8 shadow-sm hover:shadow-xl transition-all duration-300 border border-gray-100 hover:border-primary/20">
              <div class="w-14 h-14 bg-primary/10 rounded-xl flex items-center justify-center mb-6 group-hover:bg-primary group-hover:text-white transition-colors duration-300 text-primary">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-zap"><path d="M4 14a1 1 0 0 1-.78-1.63l9.9-10.2a.5.5 0 0 1 .86.46l-1.92 6.02A1 1 0 0 0 13 10h7a1 1 0 0 1 .78 1.63l-9.9 10.2a.5.5 0 0 1-.86-.46l1.92-6.02A1 1 0 0 0 11 14H4z"/></svg>
              </div>
              <h3 class="text-xl font-bold text-dark mb-3">Depilação a Laser</h3>
              <p class="text-gray-600 mb-4">
                Tecnologia de ponta para remoção definitiva de pelos com conforto e segurança.
              </p>
              <a href="#contact" class="inline-flex items-center text-primary font-medium hover:gap-2 transition-all">
                Saiba mais <span class="ml-1">→</span>
              </a>
            </div>

            <!-- Service Card 6 -->
            <div class="group bg-white rounded-2xl p-8 shadow-sm hover:shadow-xl transition-all duration-300 border border-gray-100 hover:border-primary/20">
              <div class="w-14 h-14 bg-primary/10 rounded-xl flex items-center justify-center mb-6 group-hover:bg-primary group-hover:text-white transition-colors duration-300 text-primary">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-heart-pulse"><path d="M19 14c1.49-1.28 3.6-1.28 5.14 0 1.98 1.65 2.03 4.49.12 6.19l-.03.03L19 25l-5.23-4.78-.03-.03c-1.91-1.7-1.86-4.54.12-6.19 1.54-1.28 3.65-1.28 5.14 0zM2 12h4l3 9 4-17 3 9h4"/></svg>
              </div>
              <h3 class="text-xl font-bold text-dark mb-3">Microagulhamento</h3>
              <p class="text-gray-600 mb-4">
                Indução de colágeno para tratamento de cicatrizes, manchas e rejuvenescimento.
              </p>
              <a href="#contact" class="inline-flex items-center text-primary font-medium hover:gap-2 transition-all">
                Saiba mais <span class="ml-1">→</span>
              </a>
            </div>
          </div>
        </div>
      </section>

      <!-- About Section -->
      <section id="about" class="py-24 bg-secondary/30">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="flex flex-col lg:flex-row items-center gap-16">
            <!-- Image Side -->
            <div class="w-full lg:w-1/2 relative">
              <div class="relative z-10 rounded-2xl overflow-hidden shadow-2xl">
                <img 
                  src="https://images.unsplash.com/photo-1595476108010-b4d1f102b1b1?q=80&w=2072&auto=format&fit=crop" 
                  alt="Alessandra Lima - Especialista" 
                  class="w-full h-auto object-cover"
                />
              </div>
              <!-- Decorative Frame -->
              <div class="absolute -bottom-6 -right-6 w-full h-full border-2 border-primary rounded-2xl z-0 hidden md:block"></div>
              
              <!-- Experience Badge -->
              <div class="absolute -bottom-10 -left-10 bg-white p-6 rounded-xl shadow-xl z-20 hidden md:block animate-fade-in-up">
                <div class="text-center">
                  <span class="block text-4xl font-bold text-primary">10+</span>
                  <span class="text-gray-600 font-medium">Anos de<br>Experiência</span>
                </div>
              </div>
            </div>

            <!-- Content Side -->
            <div class="w-full lg:w-1/2">
              <span class="text-primary font-medium tracking-wider uppercase text-sm">Sobre a Especialista</span>
              <h2 class="text-4xl md:text-5xl font-serif font-bold text-dark mt-3 mb-6">Alessandra Lima</h2>
              
              <div class="space-y-6 text-gray-600 text-lg leading-relaxed">
                <p>
                  Com mais de uma década de dedicação à estética avançada, minha missão é proporcionar não apenas beleza, 
                  mas autoestima e bem-estar a cada cliente que passa pelo nosso studio.
                </p>
                <p>
                  Formada em Estética e Cosmetologia, com especializações internacionais em harmonização facial e 
                  tratamentos corporais de alta performance. Acredito que cada rosto é único e merece um protocolo 
                  personalizado que respeite sua anatomia e realce seus traços naturais.
                </p>
              </div>

              <div class="mt-10 grid grid-cols-1 sm:grid-cols-2 gap-6">
                <div class="flex items-start gap-3">
                  <div class="p-2 bg-primary/10 rounded-lg text-primary">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-award"><circle cx="12" cy="8" r="7"/><polyline points="8.21 13.89 7 23 12 20 17 23 15.79 13.88"/></svg>
                  </div>
                  <div>
                    <h4 class="font-bold text-dark">Certificação Internacional</h4>
                    <p class="text-sm text-gray-500">Especialista em Harmonização</p>
                  </div>
                </div>
                <div class="flex items-start gap-3">
                  <div class="p-2 bg-primary/10 rounded-lg text-primary">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-users"><path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M22 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
                  </div>
                  <div>
                    <h4 class="font-bold text-dark">Atendimento Personalizado</h4>
                    <p class="text-sm text-gray-500">Foco total em você</p>
                  </div>
                </div>
              </div>

              <div class="mt-10">
                <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e4/Signature_sample.svg/1200px-Signature_sample.svg.png" alt="Assinatura" class="h-12 opacity-50" />
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Testimonials Section -->
      <section id="testimonials" class="py-24 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="text-center max-w-3xl mx-auto mb-16">
            <span class="text-primary font-medium tracking-wider uppercase text-sm">Depoimentos</span>
            <h2 class="text-4xl md:text-5xl font-serif font-bold text-dark mt-3 mb-6">O Que Dizem Nossas Clientes</h2>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <!-- Testimonial 1 -->
            <div class="bg-secondary/20 p-8 rounded-2xl relative">
              <div class="text-primary mb-4">
                <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="currentColor" stroke="none" class="opacity-30"><path d="M3 21c3 0 7-1 7-8V5c0-1.25-.756-2.017-2-2H4c-1.25 0-2 .75-2 1.972V11c0 1.25.75 2 2 2 1 0 1 0 1 1v1c0 1-1 2-2 2s-1 .008-1 1.031V20c0 1 0 1 1 1z"/><path d="M15 21c3 0 7-1 7-8V5c0-1.25-.757-2.017-2-2h-4c-1.25 0-2 .75-2 1.972V11c0 1.25.75 2 2 2 1 0 1 0 1 1v1c0 1-1 2-2 2s-1 .008-1 1.031V20c0 1 0 1 1 1z"/></svg>
              </div>
              <p class="text-gray-600 mb-6 italic">
                "Simplesmente encantada com o resultado da minha harmonização! A Alessandra é super atenciosa e o ambiente é maravilhoso. Me sinto renovada!"
              </p>
              <div class="flex items-center gap-4">
                <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=100&h=100&fit=crop" alt="Mariana S." class="w-12 h-12 rounded-full object-cover" />
                <div>
                  <h4 class="font-bold text-dark">Mariana Silva</h4>
                  <div class="flex text-yellow-400">
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                  </div>
                </div>
              </div>
            </div>

            <!-- Testimonial 2 -->
            <div class="bg-secondary/20 p-8 rounded-2xl relative">
              <div class="text-primary mb-4">
                <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="currentColor" stroke="none" class="opacity-30"><path d="M3 21c3 0 7-1 7-8V5c0-1.25-.756-2.017-2-2H4c-1.25 0-2 .75-2 1.972V11c0 1.25.75 2 2 2 1 0 1 0 1 1v1c0 1-1 2-2 2s-1 .008-1 1.031V20c0 1 0 1 1 1z"/><path d="M15 21c3 0 7-1 7-8V5c0-1.25-.757-2.017-2-2h-4c-1.25 0-2 .75-2 1.972V11c0 1.25.75 2 2 2 1 0 1 0 1 1v1c0 1-1 2-2 2s-1 .008-1 1.031V20c0 1 0 1 1 1z"/></svg>
              </div>
              <p class="text-gray-600 mb-6 italic">
                "Faço limpeza de pele e drenagem há 6 meses e minha pele nunca esteve tão boa. Profissionalismo nota 1000! Recomendo de olhos fechados."
              </p>
              <div class="flex items-center gap-4">
                <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=100&h=100&fit=crop" alt="Fernanda O." class="w-12 h-12 rounded-full object-cover" />
                <div>
                  <h4 class="font-bold text-dark">Fernanda Oliveira</h4>
                  <div class="flex text-yellow-400">
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                  </div>
                </div>
              </div>
            </div>

            <!-- Testimonial 3 -->
            <div class="bg-secondary/20 p-8 rounded-2xl relative">
              <div class="text-primary mb-4">
                <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="currentColor" stroke="none" class="opacity-30"><path d="M3 21c3 0 7-1 7-8V5c0-1.25-.756-2.017-2-2H4c-1.25 0-2 .75-2 1.972V11c0 1.25.75 2 2 2 1 0 1 0 1 1v1c0 1-1 2-2 2s-1 .008-1 1.031V20c0 1 0 1 1 1z"/><path d="M15 21c3 0 7-1 7-8V5c0-1.25-.757-2.017-2-2h-4c-1.25 0-2 .75-2 1.972V11c0 1.25.75 2 2 2 1 0 1 0 1 1v1c0 1-1 2-2 2s-1 .008-1 1.031V20c0 1 0 1 1 1z"/></svg>
              </div>
              <p class="text-gray-600 mb-6 italic">
                "O melhor investimento que fiz em mim mesma. O botox ficou super natural, exatamente como eu queria. A Alessandra tem mãos de fada!"
              </p>
              <div class="flex items-center gap-4">
                <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?w=100&h=100&fit=crop" alt="Patricia M." class="w-12 h-12 rounded-full object-cover" />
                <div>
                  <h4 class="font-bold text-dark">Patricia Mendes</h4>
                  <div class="flex text-yellow-400">
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                    <Star class="w-4 h-4 fill-current" />
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Gallery Section -->
      <section id="gallery" class="py-24 bg-secondary/30">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="text-center max-w-3xl mx-auto mb-16">
            <span class="text-primary font-medium tracking-wider uppercase text-sm">Portfólio</span>
            <h2 class="text-4xl md:text-5xl font-serif font-bold text-dark mt-3 mb-6">Resultados Reais</h2>
          </div>

          <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
            <div class="group relative overflow-hidden rounded-xl aspect-square cursor-pointer">
              <img src="https://images.unsplash.com/photo-1512290923902-8a9f81dc236c?w=500&h=500&fit=crop" alt="Resultado 1" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110" />
              <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                <span class="text-white font-medium border border-white px-4 py-2 rounded-full">Ver Mais</span>
              </div>
            </div>
            <div class="group relative overflow-hidden rounded-xl aspect-square cursor-pointer">
              <img src="https://images.unsplash.com/photo-1616394584738-fc6e612e71b9?w=500&h=500&fit=crop" alt="Resultado 2" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110" />
              <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                <span class="text-white font-medium border border-white px-4 py-2 rounded-full">Ver Mais</span>
              </div>
            </div>
            <div class="group relative overflow-hidden rounded-xl aspect-square cursor-pointer">
              <img src="https://images.unsplash.com/photo-1519699047748-de8e457a634e?w=500&h=500&fit=crop" alt="Resultado 3" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110" />
              <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                <span class="text-white font-medium border border-white px-4 py-2 rounded-full">Ver Mais</span>
              </div>
            </div>
            <div class="group relative overflow-hidden rounded-xl aspect-square cursor-pointer">
              <img src="https://images.unsplash.com/photo-1522337660859-02fbefca4702?w=500&h=500&fit=crop" alt="Resultado 4" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110" />
              <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                <span class="text-white font-medium border border-white px-4 py-2 rounded-full">Ver Mais</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Contact Section -->
      <section id="contact" class="py-24 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="bg-primary rounded-3xl overflow-hidden shadow-2xl flex flex-col md:flex-row">
            <div class="md:w-1/2 p-12 text-white flex flex-col justify-between relative overflow-hidden">
              <div class="absolute top-0 right-0 -mr-20 -mt-20 w-64 h-64 bg-white/10 rounded-full blur-3xl"></div>
              <div class="absolute bottom-0 left-0 -ml-20 -mb-20 w-64 h-64 bg-black/10 rounded-full blur-3xl"></div>
              
              <div class="relative z-10">
                <h2 class="text-3xl md:text-4xl font-serif font-bold mb-6">Pronta para realçar sua beleza?</h2>
                <p class="text-white/90 text-lg mb-8">
                  Agende sua avaliação gratuita e descubra o tratamento ideal para você.
                </p>
                
                <div class="space-y-6">
                  <div class="flex items-center gap-4">
                    <div class="w-10 h-10 bg-white/20 rounded-full flex items-center justify-center">
                      <Phone class="w-5 h-5" />
                    </div>
                    <span>(11) 99999-9999</span>
                  </div>
                  <div class="flex items-center gap-4">
                    <div class="w-10 h-10 bg-white/20 rounded-full flex items-center justify-center">
                      <MapPin class="w-5 h-5" />
                    </div>
                    <span>Av. Paulista, 1000 - São Paulo, SP</span>
                  </div>
                  <div class="flex items-center gap-4">
                    <div class="w-10 h-10 bg-white/20 rounded-full flex items-center justify-center">
                      <Instagram class="w-5 h-5" />
                    </div>
                    <span>@studioalessandralima</span>
                  </div>
                </div>
              </div>
            </div>
            
            <div class="md:w-1/2 bg-white p-12">
              <form class="space-y-6" @submit.prevent>
                <div>
                  <label class="block text-sm font-medium text-gray-700 mb-2">Nome Completo</label>
                  <input type="text" class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:border-primary focus:ring-2 focus:ring-primary/20 outline-none transition-all" placeholder="Seu nome" />
                </div>
                <div>
                  <label class="block text-sm font-medium text-gray-700 mb-2">Telefone / WhatsApp</label>
                  <input type="tel" class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:border-primary focus:ring-2 focus:ring-primary/20 outline-none transition-all" placeholder="(11) 99999-9999" />
                </div>
                <div>
                  <label class="block text-sm font-medium text-gray-700 mb-2">Mensagem (Opcional)</label>
                  <textarea rows="3" class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:border-primary focus:ring-2 focus:ring-primary/20 outline-none transition-all" placeholder="Gostaria de agendar..."></textarea>
                </div>
                <button class="w-full bg-primary text-white py-4 rounded-lg font-bold text-lg hover:bg-opacity-90 transition-all shadow-lg hover:shadow-primary/30">
                  Enviar Mensagem
                </button>
              </form>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- Footer -->
    <footer class="bg-dark text-white py-12 border-t border-gray-800">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-col md:flex-row justify-between items-center gap-8">
          <div class="text-center md:text-left">
            <span class="text-2xl font-serif font-bold text-white">Studio Alessandra Lima</span>
            <p class="text-gray-400 mt-2">Realçando sua beleza natural com tecnologia e carinho.</p>
          </div>
          
          <div class="flex gap-6">
            <a href="#" class="text-gray-400 hover:text-primary transition-colors">
              <Instagram class="w-6 h-6" />
            </a>
            <a href="#" class="text-gray-400 hover:text-primary transition-colors">
              <Facebook class="w-6 h-6" />
            </a>
          </div>
        </div>
        
        <div class="mt-12 pt-8 border-t border-gray-800 text-center text-gray-500 text-sm">
          <p>&copy; 2024 Studio Alessandra Lima. Todos os direitos reservados.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<style>
/* Custom fonts can be imported here or in index.html */
</style>
