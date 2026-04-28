<script setup>
import { ref, onMounted } from "vue";

const projects = ref([
  {
    id: 1,
    title: "VehicleReg",
    description:
      "An Online Vehicle Registration System that allows users to register vehicles in minutes, skipping long lines and processing everything from home.",
    tech: ["Vue.js/Nuxt.js", "Tailwind CSS", "Laravel", "MySQL", "Vite"],
    image: "/vehiclereg.png",
  },
  {
    id: 2,
    title: "Lexa's Medical Laboratory",
    description:
      "A fully deployed medical laboratory management dashboard actively used by Lexa Medical Company to manage patients, inventory, and appointments.",
    tech: ["Vue 3", "Tailwind CSS", "Laravel", "MySQL"],
    image: "/lexa.png",
  },

  {
    id: 3,
    title: "ThriftersFind OMS",
    description:
      "An Order Management System built during my time at BEULAH COMPANY. This application is actively deployed and currently used by ThriftersFind to manage their sales, orders, and courier logistics.",
    tech: ["Node.js", "Tailwind CSS", "React", "MySQL", "Tailscale"],
    image: "/thriftersfind.png",
  },
]);

const skills = ref([
  {
    name: "JavaScript (ES6+)",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg",
  },
  {
    name: "Vue.js",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg",
  },
  {
    name: "Nuxt.js",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nuxtjs/nuxtjs-original.svg",
  },
  {
    name: "React",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg",
  },
  {
    name: "Node.js",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nodejs/nodejs-original.svg",
  },
  {
    name: "HTML5/CSS3",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg",
  },
  {
    name: "Tailwind CSS",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/tailwindcss/tailwindcss-original.svg",
  },
  {
    name: "Git/GitHub",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original.svg",
  },
  {
    name: "RESTful APIs",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/fastapi/fastapi-original.svg",
  },
  {
    name: "Figma",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/figma/figma-original.svg",
  },
  {
    name: "UI/UX Design",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/xd/xd-original.svg",
  },
  {
    name: "PHP",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/php/php-original.svg",
  },
  {
    name: "Laravel",
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/laravel/laravel-original.svg",
  },
]);

const collaborations = ref([
  {
    id: 1,
    repo: "Lexa-Medical-Lab",
    owner: "johnkristanf",
    description: "Core medical laboratory management system.",
    url: "https://github.com/johnkristanf/Lexa-Medical-Lab",
  },
  {
    id: 2,
    repo: "coop",
    owner: "PLGUPICTO",
    description: "Cooperative management and tracking platform.",
    url: "https://github.com/PLGUPICTO/coop",
  },
  {
    id: 3,
    repo: "Authentication",
    owner: "Carlo1437",
    description: "Secure authentication and authorization service.",
    url: "https://github.com/Carlo1437/Authentication",
  },
  {
    id: 4,
    repo: "thriftersfind",
    owner: "carlobeulahdeano-sketch",
    description: "Order management system for ThriftersFind.",
    url: "https://github.com/carlobeulahdeano-sketch/thriftersfind",
  },
]);

const scrolled = ref(false);

// Typing animation state
const introText = "Hi, I am John Carlo F. Deano";
const mainTextLine1 = "A Passionate";
const mainTextLine2 = "Web Developer";

const typedIntro = ref("");
const typedLine1 = ref("");
const typedLine2 = ref("");

const typingState = ref("intro"); // 'intro', 'line1', 'line2', 'done'

onMounted(() => {
  window.addEventListener("scroll", () => {
    scrolled.value = window.scrollY > 50;
  });

  // Typing animation logic
  let iIntro = 0;
  let i1 = 0;
  let i2 = 0;
  const speed = 60; // typing speed in ms

  const typeLine2 = () => {
    typingState.value = "line2";
    if (i2 < mainTextLine2.length) {
      typedLine2.value += mainTextLine2.charAt(i2);
      i2++;
      setTimeout(typeLine2, speed);
    } else {
      typingState.value = "done";
    }
  };

  const typeLine1 = () => {
    typingState.value = "line1";
    if (i1 < mainTextLine1.length) {
      typedLine1.value += mainTextLine1.charAt(i1);
      i1++;
      setTimeout(typeLine1, speed);
    } else {
      setTimeout(typeLine2, 200);
    }
  };

  const typeIntro = () => {
    typingState.value = "intro";
    if (iIntro < introText.length) {
      typedIntro.value += introText.charAt(iIntro);
      iIntro++;
      setTimeout(typeIntro, speed);
    } else {
      setTimeout(typeLine1, 300);
    }
  };

  setTimeout(typeIntro, 300);
});
</script>

<template>
  <div
    class="min-h-screen font-sans selection:bg-[var(--color-accent-1)] selection:text-white"
  >
    <!-- Floating GIF -->
    <img
      src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExZmp6aDF3ZGd5aGNucjhidWN1Ym44cG1ia293MmpuanhiOGV6Z2M0NCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/kBZ212yGzFaxgkSIKW/giphy.gif"
      alt="Floating character animation"
      class="fixed right-4 bottom-4 z-50 w-20 md:w-28 h-auto pointer-events-none"
    />

    <!-- Navigation -->
    <nav
      class="fixed top-0 left-0 w-full z-50 transition-all duration-300 py-6"
      :class="{
        'py-4 bg-[var(--color-bg-glass)] backdrop-blur-xl border-b border-white/5':
          scrolled,
      }"
    >
      <div class="max-w-7xl mx-auto px-8 flex justify-between items-center">
        <a href="#" class="font-display text-2xl font-extrabold tracking-tight"
          >My Portfolio.</a
        >
        <ul class="hidden md:flex items-center gap-8">
          <li>
            <a
              href="#about"
              class="text-sm font-medium text-[var(--color-text-secondary)] hover:text-white transition-colors"
              >About</a
            >
          </li>
          <li>
            <a
              href="#projects"
              class="text-sm font-medium text-[var(--color-text-secondary)] hover:text-white transition-colors"
              >Projects</a
            >
          </li>
          <li>
            <a
              href="#skills"
              class="text-sm font-medium text-[var(--color-text-secondary)] hover:text-white transition-colors"
              >Skills</a
            >
          </li>
          <li>
            <a
              href="#contact"
              class="inline-flex items-center justify-center px-5 py-2 rounded-full text-sm font-medium text-white bg-gradient-to-br from-[var(--color-accent-1)] to-[var(--color-accent-2)] hover:-translate-y-0.5 shadow-[0_4px_14px_0_rgba(99,102,241,0.39)] hover:shadow-[0_6px_20px_rgba(99,102,241,0.5)] transition-all duration-300"
            >
              Let's Talk
            </a>
          </li>
        </ul>
      </div>
    </nav>

    <!-- Hero Section -->
    <section
      class="relative min-h-screen flex items-center pt-20 overflow-hidden"
    >
      <!-- Background Shapes -->
      <div class="absolute inset-0 -z-10 overflow-hidden">
        <div
          class="absolute -top-10 -right-5 w-[600px] h-[600px] bg-[var(--color-accent-1)] rounded-full blur-[100px] opacity-40 animate-pulse mix-blend-screen duration-[10000ms]"
        ></div>
        <div
          class="absolute -bottom-10 -left-10 w-[500px] h-[500px] bg-[var(--color-accent-2)] rounded-full blur-[100px] opacity-40 animate-pulse mix-blend-screen duration-[10000ms] delay-1000"
        ></div>
      </div>

      <div
        class="max-w-7xl mx-auto px-8 w-full flex flex-col lg:flex-row items-center justify-between gap-12"
      >
        <div class="max-w-3xl lg:w-3/5">
          <p
            class="text-lg font-medium text-[var(--color-accent-1)] mb-4 tracking-widest uppercase min-h-[28px]"
          >
            {{ typedIntro
            }}<span
              v-if="typingState === 'intro'"
              class="inline-block w-[2px] h-[1em] bg-current ml-1 align-text-bottom animate-blink"
            ></span>
          </p>
          <h1
            class="font-display text-5xl md:text-7xl font-bold leading-tight mb-6 tracking-tight min-h-[120px] md:min-h-[160px]"
          >
            {{ typedLine1
            }}<span
              v-if="typingState === 'line1'"
              class="inline-block w-[3px] md:w-[4px] h-[0.9em] bg-white ml-1 md:ml-2 align-text-bottom animate-blink"
            ></span>
            <br />
            <span class="text-gradient">{{ typedLine2 }}</span
            ><span
              v-if="typingState === 'line2' || typingState === 'done'"
              class="inline-block w-[3px] md:w-[4px] h-[0.9em] bg-[var(--color-accent-1)] ml-1 md:ml-2 align-text-bottom animate-blink"
            ></span>
          </h1>
          <p
            class="text-xl text-[var(--color-text-secondary)] mb-10 max-w-2xl leading-relaxed animate-fade-in [animation-delay:200ms]"
          >
            I build modern, scalable, and user-centric web applications. With
            professional experience as a Web Developer at BEULAH COMPANY, I love
            transforming complex problems into elegant, intuitive, and
            high-performance digital experiences.
          </p>
          <div
            class="flex flex-col sm:flex-row gap-4 animate-fade-in [animation-delay:300ms]"
          >
            <a
              href="#projects"
              class="inline-flex items-center justify-center px-8 py-3.5 rounded-full font-medium text-white bg-gradient-to-br from-[var(--color-accent-1)] to-[var(--color-accent-2)] hover:-translate-y-0.5 shadow-[0_4px_14px_0_rgba(99,102,241,0.39)] hover:shadow-[0_6px_20px_rgba(99,102,241,0.5)] transition-all duration-300"
            >
              View My Work
            </a>
            <a
              href="#contact"
              class="inline-flex items-center justify-center px-8 py-3.5 rounded-full font-medium text-white bg-white/5 border border-white/10 backdrop-blur-md hover:bg-white/10 hover:-translate-y-0.5 transition-all duration-300"
            >
              Contact Me
            </a>
          </div>
        </div>

        <div
          class="lg:w-2/5 flex justify-center animate-fade-in [animation-delay:400ms]"
        >
          <div
            class="relative w-64 h-64 md:w-80 md:h-80 lg:w-[400px] lg:h-[400px] rounded-full p-2 bg-gradient-to-br from-[var(--color-accent-1)] via-[var(--color-accent-2)] to-[var(--color-accent-3)] shadow-[0_10px_40px_rgba(168,85,247,0.3)] hover:scale-105 transition-transform duration-500"
          >
            <img
              src="/profile.jpg"
              alt="John Carlo F. Deano"
              class="w-full h-full object-cover rounded-full border-4 border-[var(--color-bg-primary)]"
            />
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-32">
      <div class="max-w-7xl mx-auto px-8">
        <div class="flex flex-col lg:flex-row items-center gap-16">
          <!-- Image Container (Left Side) -->
          <div
            class="w-full lg:w-2/5 flex justify-center lg:justify-start animate-fade-in [animation-delay:200ms]"
          >
            <div
              class="relative w-64 h-64 md:w-80 md:h-80 lg:w-[420px] lg:h-[420px] rounded-3xl p-2 bg-gradient-to-br from-[var(--color-accent-2)] via-[var(--color-accent-3)] to-[var(--color-accent-1)] shadow-[0_10px_40px_rgba(168,85,247,0.2)] hover:-translate-y-2 transition-transform duration-500"
            >
              <img
                src="/profile.jpg"
                alt="John Carlo F. Deano"
                class="w-full h-full object-cover rounded-3xl border-4 border-[var(--color-bg-primary)] transition-all duration-500"
              />
              <div
                class="absolute -bottom-6 -right-6 bg-gradient-to-br from-[var(--color-accent-1)] to-[var(--color-accent-2)] text-white p-6 rounded-2xl shadow-xl hidden md:block animate-bounce [animation-duration:3s]"
              >
                <p class="text-3xl font-bold">1+</p>
                <p class="text-sm font-medium opacity-90">Years Exp.</p>
              </div>
            </div>
          </div>

          <!-- Content Container (Right Side) -->
          <div
            class="w-full lg:w-3/5 text-center lg:text-left animate-fade-in [animation-delay:400ms]"
          >
            <h2 class="font-display text-4xl md:text-5xl font-bold mb-8">
              About Me
            </h2>
            <div
              class="space-y-6 text-lg text-[var(--color-text-secondary)] leading-relaxed"
            >
              <p>
                I'm a 25-year-old web developer from Panabo City, Davao del
                Norte, Philippines. I graduated in 2025 with a Bachelor's degree
                in Information Systems (BSIS) from Davao del Norte State
                College.
              </p>
              <p>
                I specialize in both front-end and back-end development. On the
                front end, I work with HTML, CSS, and JavaScript, and I also
                have experience with modern frameworks such as Vue and React. On
                the back end, I am skilled in PHP and Laravel, and I also have
                experience working with Node.js.
              </p>
              <p>
                As a fresh graduate, I gained hands-on experience as a
                full-stack web developer during my time at Beulah Company, where
                I assisted in building and improving web applications. I focus
                on creating clean, efficient, and user-friendly solutions that
                align with client requirements and deliver a seamless user
                experience.
              </p>
            </div>

            <div
              class="mt-10 flex flex-col sm:flex-row gap-6 justify-center lg:justify-start"
            >
              <div
                class="flex items-center gap-4 bg-white/5 px-6 py-4 rounded-2xl border border-white/10"
              >
                <div
                  class="w-12 h-12 rounded-full bg-[var(--color-accent-1)]/20 flex items-center justify-center text-[var(--color-accent-1)]"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  >
                    <path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"></path>
                    <polyline points="22 4 12 14.01 9 11.01"></polyline>
                  </svg>
                </div>
                <div class="text-left">
                  <h4 class="text-white font-bold text-xl">Front-end</h4>
                  <p class="text-sm text-[var(--color-text-secondary)]">
                    Vue, React, Tailwind
                  </p>
                </div>
              </div>
              <div
                class="flex items-center gap-4 bg-white/5 px-6 py-4 rounded-2xl border border-white/10"
              >
                <div
                  class="w-12 h-12 rounded-full bg-[var(--color-accent-2)]/20 flex items-center justify-center text-[var(--color-accent-2)]"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  >
                    <rect
                      x="2"
                      y="2"
                      width="20"
                      height="8"
                      rx="2"
                      ry="2"
                    ></rect>
                    <rect
                      x="2"
                      y="14"
                      width="20"
                      height="8"
                      rx="2"
                      ry="2"
                    ></rect>
                    <line x1="6" y1="6" x2="6.01" y2="6"></line>
                    <line x1="6" y1="18" x2="6.01" y2="18"></line>
                  </svg>
                </div>
                <div class="text-left">
                  <h4 class="text-white font-bold text-xl">Back-end</h4>
                  <p class="text-sm text-[var(--color-text-secondary)]">
                    Laravel, Node.js
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="py-32 bg-[var(--color-bg-secondary)]">
      <div class="max-w-7xl mx-auto px-8">
        <h2 class="font-display text-4xl font-bold text-center mb-16">
          Featured Projects
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div
            v-for="project in projects"
            :key="project.id"
            class="group bg-[var(--color-bg-primary)] rounded-3xl overflow-hidden border border-white/5 hover:-translate-y-2 hover:shadow-[0_20px_40px_rgba(0,0,0,0.4)] hover:border-white/10 transition-all duration-300"
          >
            <div class="relative h-60 overflow-hidden">
              <img
                :src="project.image"
                :alt="project.title"
                class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700 ease-in-out"
              />
              <div
                class="absolute inset-0 bg-[#0a0a0c]/70 backdrop-blur-[2px] flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300"
              >
                <a
                  href="#"
                  class="inline-flex items-center justify-center px-6 py-2 rounded-full text-sm font-medium text-white bg-gradient-to-br from-[var(--color-accent-1)] to-[var(--color-accent-2)] shadow-lg hover:scale-105 transition-transform"
                >
                  View Details
                </a>
              </div>
            </div>
            <div class="p-8">
              <div class="flex flex-wrap gap-2 mb-4">
                <span
                  v-for="tech in project.tech"
                  :key="tech"
                  class="text-xs px-3 py-1 bg-white/5 rounded-full text-[var(--color-accent-2)] font-medium"
                >
                  {{ tech }}
                </span>
              </div>
              <h3 class="font-display text-2xl font-bold mb-3">
                {{ project.title }}
              </h3>
              <p
                class="text-[var(--color-text-secondary)] leading-relaxed text-sm"
              >
                {{ project.description }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- GitHub Collaborations Section -->
    <section id="collaborations" class="py-32">
      <div class="max-w-7xl mx-auto px-8">
        <h2 class="font-display text-4xl font-bold text-center mb-16">
          GitHub Collaborations
        </h2>
        <div class="flex flex-col lg:flex-row gap-12 items-center">
          <!-- Image Container -->
          <div
            class="w-full lg:w-1/2 h-[280px] md:h-[350px] lg:h-[480px] rounded-2xl overflow-hidden border border-white/10 shadow-[0_20px_40px_rgba(0,0,0,0.4)] group"
          >
            <img
              src="/github.png"
              alt="GitHub Collaborations Dashboard"
              class="w-full h-full object-cover object-left-top group-hover:scale-105 transition-transform duration-700 ease-in-out"
            />
          </div>

          <!-- Collab List -->
          <div class="w-full lg:w-1/2 grid grid-cols-1 gap-6">
            <a
              v-for="collab in collaborations"
              :key="collab.id"
              :href="collab.url"
              target="_blank"
              rel="noopener noreferrer"
              class="flex items-start gap-5 p-6 bg-[var(--color-bg-secondary)] rounded-2xl border border-white/5 hover:border-[var(--color-accent-1)] hover:-translate-y-1 transition-all duration-300 group/card"
            >
              <div
                class="flex-shrink-0 w-12 h-12 flex items-center justify-center rounded-full bg-gradient-to-br from-[var(--color-accent-1)] to-[var(--color-accent-2)] text-white shadow-lg group-hover/card:scale-110 transition-transform duration-300"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="22"
                  height="22"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <path
                    d="M15 22v-4a4.8 4.8 0 0 0-1-3.2c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"
                  />
                  <path d="M9 18c-4.51 2-5-2-7-2" />
                </svg>
              </div>
              <div>
                <h3
                  class="font-display text-xl font-bold text-white mb-2 group-hover/card:text-[var(--color-accent-1)] transition-colors duration-300"
                >
                  {{ collab.owner }} /
                  <span class="text-[var(--color-accent-2)]">{{
                    collab.repo
                  }}</span>
                </h3>
                <p
                  class="text-[var(--color-text-secondary)] text-sm leading-relaxed"
                >
                  {{ collab.description }}
                </p>
              </div>
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="py-32 bg-[var(--color-bg-secondary)]">
      <div class="max-w-7xl mx-auto px-8">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div class="text-center lg:text-left">
            <h2 class="font-display text-4xl font-bold mb-6">My Toolkit</h2>
            <p
              class="text-lg text-[var(--color-text-secondary)] leading-relaxed"
            >
              I specialize in building scalable web applications using the
              latest web standards and frameworks. Always eager to learn and
              adapt to new challenges.
            </p>
          </div>
          <div class="flex flex-wrap gap-4 justify-center lg:justify-start">
            <div
              v-for="skill in skills"
              :key="skill.name"
              class="flex items-center gap-3 px-6 py-3 bg-[var(--color-bg-secondary)] border border-white/5 rounded-full font-medium hover:bg-white/10 hover:-translate-y-1 hover:border-[var(--color-accent-1)] transition-all duration-300 cursor-default"
            >
              <img
                :src="skill.icon"
                :alt="skill.name"
                class="w-5 h-5 object-contain"
              />
              <span>{{ skill.name }}</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-32 bg-[var(--color-bg-secondary)]">
      <div class="max-w-7xl mx-auto px-8">
        <div
          class="relative bg-gradient-to-br from-indigo-500/10 to-purple-500/5 border border-white/10 rounded-[40px] p-12 md:p-20 text-center overflow-hidden"
        >
          <div
            class="absolute inset-0 bg-[url('https://www.transparenttextures.com/patterns/cubes.png')] opacity-10 mix-blend-overlay pointer-events-none"
          ></div>
          <h2
            class="relative z-10 font-display text-4xl md:text-5xl font-bold mb-6 max-w-2xl mx-auto"
          >
            Let's build something extraordinary together.
          </h2>
          <p
            class="relative z-10 text-lg text-[var(--color-text-secondary)] mb-10"
          >
            Currently open for new opportunities and freelance projects.
          </p>
          <a
            href="mailto:johncarlo@gmail.com"
            class="relative z-10 inline-flex items-center justify-center px-10 py-4 rounded-full text-lg font-medium text-white bg-gradient-to-br from-[var(--color-accent-1)] to-[var(--color-accent-2)] hover:-translate-y-1 shadow-[0_4px_14px_0_rgba(99,102,241,0.39)] hover:shadow-[0_8px_25px_rgba(99,102,241,0.5)] transition-all duration-300"
          >
            Say Hello
          </a>

          <div
            class="relative z-10 mt-12 flex flex-col md:flex-row flex-wrap items-center justify-center gap-6 text-[var(--color-text-secondary)]"
          >
            <div
              class="flex items-center gap-3 bg-white/5 px-6 py-3 rounded-full border border-white/10 hover:border-white/20 transition-colors"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path
                  d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"
                ></path>
                <polyline points="22,6 12,13 2,6"></polyline>
              </svg>
              <span>johncarlodeano@gmail.com</span>
            </div>
            <div
              class="flex items-center gap-3 bg-white/5 px-6 py-3 rounded-full border border-white/10 hover:border-white/20 transition-colors"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path
                  d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"
                ></path>
              </svg>
              <span>09156207658</span>
            </div>
            <a
              href="https://www.facebook.com/carlo.diano.142"
              target="_blank"
              rel="noopener noreferrer"
              class="flex items-center gap-3 bg-white/5 px-6 py-3 rounded-full border border-white/10 hover:text-white hover:border-[var(--color-accent-1)] hover:bg-white/10 transition-all"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path
                  d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"
                ></path>
              </svg>
              <span>Facebook</span>
            </a>
          </div>
        </div>
      </div>
    </section>

    <footer class="py-12 border-t border-white/5">
      <div
        class="max-w-7xl mx-auto px-8 flex flex-col md:flex-row justify-between items-center gap-6"
      >
        <p class="text-sm text-[var(--color-text-secondary)]">
          &copy; {{ new Date().getFullYear() }} Portfolio. All rights reserved.
        </p>
        <div class="flex gap-6">
          <a
            href="https://github.com/Carlo1437"
            target="_blank"
            class="text-[var(--color-text-secondary)] hover:text-white transition-colors"
            >GitHub</a
          >
          <a
            href="https://www.facebook.com/carlo.diano.142"
            target="_blank"
            class="text-[var(--color-text-secondary)] hover:text-white transition-colors"
            >Facebook</a
          >
        </div>
      </div>
    </footer>
  </div>
</template>

<style>
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  opacity: 0;
  animation: fadeIn 0.8s cubic-bezier(0.4, 0, 0.2, 1) forwards;
}

@keyframes blink {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
}

.animate-blink {
  animation: blink 1s step-end infinite;
}
</style>
