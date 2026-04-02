<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Samson Chinthenga — Software Developer</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://code.iconify.design/iconify-icon/1.0.7/iconify-icon.min.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            display: ['Space Grotesk', 'sans-serif'],
            mono: ['JetBrains Mono', 'monospace'],
          },
          colors: {
            dark: { 900: '#05050A', 800: '#0A0A10', 700: '#0E0E18', 600: '#14141F' },
            accent: { DEFAULT: '#EAB308', hover: '#FDE047', dim: 'rgba(234,179,8,0.15)' },
            sub: '#A1A1AA',
          }
        }
      }
    }
  </script>
  <style>
    ::selection { background: #EAB308; color: #000; }
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: #05050A; }
    ::-webkit-scrollbar-thumb { background: #334155; border-radius: 3px; }
    ::-webkit-scrollbar-thumb:hover { background: #EAB308; }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    @keyframes slideLeft {
      from { opacity: 0; transform: translateX(40px); }
      to { opacity: 1; transform: translateX(0); }
    }
    @keyframes slideRight {
      from { opacity: 0; transform: translateX(-40px); }
      to { opacity: 1; transform: translateX(0); }
    }
    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-12px); }
    }
    @keyframes pulse-glow {
      0%, 100% { box-shadow: 0 0 20px rgba(234,179,8,0.2); }
      50% { box-shadow: 0 0 40px rgba(234,179,8,0.4); }
    }
    @keyframes typing {
      from { width: 0; }
      to { width: 100%; }
    }
    @keyframes blink {
      50% { border-color: transparent; }
    }
    @keyframes orbit {
      from { transform: rotate(0deg) translateX(120px) rotate(0deg); }
      to { transform: rotate(360deg) translateX(120px) rotate(-360deg); }
    }
    @keyframes gradient-shift {
      0%, 100% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
    }
    @keyframes counter {
      from { opacity: 0; transform: scale(0.5); }
      to { opacity: 1; transform: scale(1); }
    }

    .animate-on-scroll { opacity: 0; transform: translateY(30px); transition: all 0.8s cubic-bezier(0.16, 1, 0.3, 1); }
    .animate-on-scroll.visible { opacity: 1; transform: translateY(0); }
    .animate-on-scroll.visible.delay-1 { transition-delay: 0.1s; }
    .animate-on-scroll.visible.delay-2 { transition-delay: 0.2s; }
    .animate-on-scroll.visible.delay-3 { transition-delay: 0.3s; }
    .animate-on-scroll.visible.delay-4 { transition-delay: 0.4s; }
    .animate-on-scroll.visible.delay-5 { transition-delay: 0.5s; }

    .gradient-text {
      background: linear-gradient(to right, #FACC15, #EAB308, #FDE047);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .gradient-text-subtle {
      background: linear-gradient(to right, #EAB308, #FDE047);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .skill-card {
      position: relative;
      overflow: hidden;
      transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
    }
    .skill-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 2px;
      background: linear-gradient(to right, transparent, #EAB308, transparent);
      transform: scaleX(0);
      transition: transform 0.5s ease;
    }
    .skill-card:hover::before { transform: scaleX(1); }
    .skill-card:hover { transform: translateY(-4px); border-color: rgba(234,179,8,0.3); }

    .tech-pill {
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
    }
    .tech-pill::after {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(234,179,8,0.1), transparent);
      opacity: 0;
      transition: opacity 0.3s;
    }
    .tech-pill:hover::after { opacity: 1; }
    .tech-pill:hover { border-color: rgba(234,179,8,0.5); transform: translateY(-2px); }

    .project-card {
      transition: all 0.5s cubic-bezier(0.16, 1, 0.3, 1);
    }
    .project-card:hover { transform: translateY(-6px); }
    .project-card:hover .project-img { transform: scale(1.05); }
    .project-card:hover .project-overlay { opacity: 1; }

    .status-dot {
      animation: pulse-glow 2s ease-in-out infinite;
    }

    .orbit-item {
      animation: orbit 20s linear infinite;
    }
    .orbit-item:nth-child(2) { animation-delay: -5s; animation-duration: 25s; }
    .orbit-item:nth-child(3) { animation-delay: -10s; animation-duration: 30s; }
    .orbit-item:nth-child(4) { animation-delay: -15s; animation-duration: 22s; }
    .orbit-item:nth-child(5) { animation-delay: -8s; animation-duration: 28s; }
    .orbit-item:nth-child(6) { animation-delay: -3s; animation-duration: 35s; }

    .nav-link { position: relative; }
    .nav-link::after {
      content: '';
      position: absolute;
      bottom: -2px; left: 0;
      width: 0; height: 1px;
      background: #EAB308;
      transition: width 0.3s ease;
    }
    .nav-link:hover::after { width: 100%; }

    .glass {
      background: rgba(255,255,255,0.03);
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255,255,255,0.05);
    }

    .noise-overlay {
      position: fixed; inset: 0; z-index: 9999; pointer-events: none; opacity: 0.03;
    }

    .tab-btn.active { color: #EAB308; border-color: #EAB308; background: rgba(234,179,8,0.08); }
    .tab-content { display: none; }
    .tab-content.active { display: grid; }

    .contact-link {
      transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
    }
    .contact-link:hover {
      transform: translateX(8px);
      border-color: rgba(234,179,8,0.4);
    }
    .contact-link:hover .contact-icon {
      color: #EAB308;
      transform: scale(1.1);
    }

    .hero-badge {
      animation: fadeUp 0.8s ease forwards;
    }
    .hero-title {
      animation: fadeUp 0.8s ease 0.2s forwards;
      opacity: 0;
    }
    .hero-sub {
      animation: fadeUp 0.8s ease 0.4s forwards;
      opacity: 0;
    }
    .hero-cta {
      animation: fadeUp 0.8s ease 0.6s forwards;
      opacity: 0;
    }
    .hero-scroll {
      animation: fadeUp 0.8s ease 0.8s forwards;
      opacity: 0;
    }

    @media (max-width: 768px) {
      .orbit-item { display: none; }
    }
  </style>
</head>
<body class="bg-dark-900 text-white font-sans antialiased overflow-x-hidden">

  <!-- Noise Overlay -->
  <svg class="noise-overlay" width="100%" height="100%">
    <filter id="noise"><feTurbulence type="fractalNoise" baseFrequency="0.65" numOctaves="3" stitchTiles="stitch"/></filter>
    <rect width="100%" height="100%" filter="url(#noise)"/>
  </svg>

  <!-- Navigation -->
  <nav class="fixed top-0 left-0 right-0 z-50 transition-all duration-500" id="navbar">
    <div class="max-w-7xl mx-auto px-6">
      <div class="flex items-center justify-between h-20">
        <a href="#" class="font-display font-bold text-xl tracking-tight">
          <span class="text-accent">S</span><span class="text-white">.</span>
        </a>
        <div class="hidden md:flex items-center gap-8">
          <a href="#about" class="nav-link text-sm font-medium text-sub hover:text-white transition-colors tracking-wide uppercase">About</a>
          <a href="#stack" class="nav-link text-sm font-medium text-sub hover:text-white transition-colors tracking-wide uppercase">Stack</a>
          <a href="#projects" class="nav-link text-sm font-medium text-sub hover:text-white transition-colors tracking-wide uppercase">Projects</a>
          <a href="#contact" class="nav-link text-sm font-medium text-sub hover:text-white transition-colors tracking-wide uppercase">Contact</a>
        </div>
        <a href="#contact" class="hidden md:inline-flex items-center gap-2 px-5 py-2.5 bg-accent text-black text-xs font-bold tracking-widest uppercase rounded-sm hover:bg-accent-hover transition-all duration-300 hover:shadow-[0_0_30px_rgba(234,179,8,0.3)]">
          Let's Talk
          <iconify-icon icon="lucide:arrow-right" width="14"></iconify-icon>
        </a>
        <button class="md:hidden text-white" id="menuBtn">
          <iconify-icon icon="lucide:menu" width="24"></iconify-icon>
        </button>
      </div>
    </div>
    <!-- Mobile Menu -->
    <div class="md:hidden hidden bg-dark-800/95 backdrop-blur-xl border-t border-white/5" id="mobileMenu">
      <div class="px-6 py-6 flex flex-col gap-4">
        <a href="#about" class="text-sub hover:text-white transition-colors py-2 mobile-link">About</a>
        <a href="#stack" class="text-sub hover:text-white transition-colors py-2 mobile-link">Stack</a>
        <a href="#projects" class="text-sub hover:text-white transition-colors py-2 mobile-link">Projects</a>
        <a href="#contact" class="text-sub hover:text-white transition-colors py-2 mobile-link">Contact</a>
        <a href="#contact" class="mt-2 inline-flex items-center justify-center gap-2 px-5 py-3 bg-accent text-black text-xs font-bold tracking-widest uppercase rounded-sm mobile-link">Let's Talk</a>
      </div>
    </div>
  </nav>

  <!-- Hero Section -->
  <section class="relative min-h-screen flex items-center justify-center px-6 overflow-hidden">
    <!-- Background Elements -->
    <div class="absolute inset-0">
      <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-accent/5 rounded-full blur-[120px]"></div>
      <div class="absolute bottom-1/4 right-1/4 w-80 h-80 bg-accent/3 rounded-full blur-[100px]"></div>
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] rounded-full border border-white/[0.03]"></div>
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[400px] h-[400px] rounded-full border border-white/[0.03]"></div>
      <!-- Grid -->
      <div class="absolute inset-0 opacity-[0.03]" style="background-image: linear-gradient(rgba(255,255,255,0.1) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,0.1) 1px, transparent 1px); background-size: 60px 60px;"></div>
    </div>

    <!-- Orbiting Icons -->
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-0 h-0 hidden md:block">
      <div class="orbit-item absolute text-accent/40"><iconify-icon icon="logos:flutter" width="28"></iconify-icon></div>
      <div class="orbit-item absolute text-accent/40"><iconify-icon icon="logos:react" width="28"></iconify-icon></div>
      <div class="orbit-item absolute text-accent/40"><iconify-icon icon="logos:firebase" width="24"></iconify-icon></div>
      <div class="orbit-item absolute text-accent/40"><iconify-icon icon="logos:nodejs-icon" width="28"></iconify-icon></div>
      <div class="orbit-item absolute text-accent/40"><iconify-icon icon="logos:python" width="24"></iconify-icon></div>
      <div class="orbit-item absolute text-accent/40"><iconify-icon icon="logos:docker-icon" width="28"></iconify-icon></div>
    </div>

    <div class="relative z-10 text-center max-w-4xl mx-auto">
      <!-- Status Badge -->
      <div class="hero-badge inline-flex items-center gap-2.5 px-4 py-2 rounded-full border border-white/10 bg-white/[0.03] mb-8">
        <span class="relative flex h-2 w-2">
          <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-green-400 opacity-75"></span>
          <span class="relative inline-flex rounded-full h-2 w-2 bg-green-400"></span>
        </span>
        <span class="text-xs font-medium text-sub tracking-wide">Available for opportunities</span>
      </div>

      <!-- Name -->
      <h1 class="hero-title font-display font-bold text-5xl md:text-7xl lg:text-8xl tracking-tighter leading-[0.95] mb-6">
        Samson<br>
        <span class="gradient-text">Chinthenga</span>
      </h1>

      <!-- Roles -->
      <div class="hero-sub flex flex-wrap items-center justify-center gap-3 mb-8">
        <span class="px-3 py-1 text-[10px] font-semibold tracking-[0.2em] uppercase border border-accent/30 text-accent rounded-sm bg-accent/5">Mobile Dev</span>
        <span class="text-sub text-xs">•</span>
        <span class="px-3 py-1 text-[10px] font-semibold tracking-[0.2em] uppercase border border-white/10 text-sub rounded-sm bg-white/[0.02]">Backend</span>
        <span class="text-sub text-xs">•</span>
        <span class="px-3 py-1 text-[10px] font-semibold tracking-[0.2em] uppercase border border-white/10 text-sub rounded-sm bg-white/[0.02]">Web Dev</span>
      </div>

      <!-- Description -->
      <p class="hero-sub text-sub text-base md:text-lg font-light leading-relaxed max-w-2xl mx-auto mb-10">
        I craft high-performance mobile apps, robust backend systems, and sleek web experiences. 
        Turning complex problems into elegant, user-centric solutions.
      </p>

      <!-- CTAs -->
      <div class="hero-cta flex flex-col sm:flex-row items-center justify-center gap-4">
        <a href="#projects" class="inline-flex items-center gap-2.5 px-8 py-4 bg-accent text-black text-xs font-bold tracking-widest uppercase rounded-sm hover:bg-accent-hover transition-all duration-300 hover:shadow-[0_0_40px_rgba(234,179,8,0.3)]">
          View My Work
          <iconify-icon icon="lucide:arrow-down-right" width="16"></iconify-icon>
        </a>
        <a href="#contact" class="inline-flex items-center gap-2.5 px-8 py-4 border border-white/20 text-white text-xs font-bold tracking-widest uppercase rounded-sm hover:border-accent/50 hover:text-accent transition-all duration-300">
          Get In Touch
        </a>
      </div>

      <!-- Scroll Indicator -->
      <div class="hero-scroll mt-16 md:mt-24 flex flex-col items-center gap-2">
        <span class="text-[10px] tracking-[0.3em] uppercase text-sub/50">Scroll</span>
        <div class="w-px h-12 bg-gradient-to-b from-accent/50 to-transparent"></div>
      </div>
    </div>
  </section>

  <!-- About Section -->
  <section id="about" class="relative py-24 md:py-32 px-6">
    <div class="max-w-7xl mx-auto">
      <div class="grid lg:grid-cols-2 gap-16 items-center">
        <!-- Left: Visual -->
        <div class="animate-on-scroll relative">
          <div class="relative aspect-square max-w-md mx-auto lg:mx-0">
            <!-- Background decoration -->
            <div class="absolute inset-0 border border-white/5 rounded-sm"></div>
            <div class="absolute -top-4 -left-4 w-24 h-24 border-t-2 border-l-2 border-accent/50 rounded-tl-sm"></div>
            <div class="absolute -bottom-4 -right-4 w-24 h-24 border-b-2 border-r-2 border-accent/50 rounded-br-sm"></div>
            
            <!-- Code block visual -->
            <div class="absolute inset-4 bg-dark-800 rounded-sm border border-white/5 p-6 font-mono text-sm overflow-hidden">
              <div class="flex items-center gap-2 mb-4">
                <div class="w-3 h-3 rounded-full bg-red-500/60"></div>
                <div class="w-3 h-3 rounded-full bg-yellow-500/60"></div>
                <div class="w-3 h-3 rounded-full bg-green-500/60"></div>
                <span class="ml-2 text-[10px] text-sub/40 tracking-wider">samson_dev.dart</span>
              </div>
              <div class="space-y-1.5 text-xs leading-relaxed">
                <div><span class="text-purple-400">class</span> <span class="text-accent">SamsonChinthenga</span> {</div>
                <div class="pl-4"><span class="text-purple-400">final</span> roles = [</div>
                <div class="pl-8"><span class="text-green-400">'Mobile Developer'</span>,</div>
                <div class="pl-8"><span class="text-green-400">'Backend Engineer'</span>,</div>
                <div class="pl-8"><span class="text-green-400">'Web Developer'</span>,</div>
                <div class="pl-4">];</div>
                <div class="pl-4"></div>
                <div class="pl-4"><span class="text-purple-400">void</span> <span class="text-blue-400">buildAmazingThings</span>() {</div>
                <div class="pl-8"><span class="text-sub/40">// shipped to production 🚀</span></div>
                <div class="pl-8">deploy(quality: <span class="text-accent">Quality.high</span>);</div>
                <div class="pl-4">}</div>
                <div>}</div>
              </div>
            </div>
          </div>
        </div>

        <!-- Right: Content -->
        <div>
          <div class="animate-on-scroll">
            <span class="text-[10px] font-semibold tracking-[0.25em] uppercase text-accent">About Me</span>
            <h2 class="font-display font-bold text-3xl md:text-4xl tracking-tight mt-3 mb-6">
              Building software that<br><span class="gradient-text-subtle">matters</span>
            </h2>
          </div>
          <div class="animate-on-scroll delay-1">
            <p class="text-sub font-light leading-relaxed mb-6">
              I'm a full-spectrum developer who thrives at the intersection of design and engineering. With deep expertise in <strong class="text-white font-medium">Flutter</strong> and <strong class="text-white font-medium">React Native</strong> for mobile, paired with solid backend and web skills, I deliver complete solutions from database to pixel-perfect UI.
            </p>
            <p class="text-sub font-light leading-relaxed mb-8">
              Currently focused on AI-integrated applications and health-tech solutions. I believe great software isn't just functional — it's intuitive, fast, and genuinely improves people's lives.
            </p>
          </div>
          
          <!-- Stats -->
          <div class="animate-on-scroll delay-2 grid grid-cols-3 gap-6 mb-8">
            <div class="text-center lg:text-left">
              <div class="font-display font-bold text-3xl gradient-text" data-count="15">0</div>
              <div class="text-xs text-sub mt-1 tracking-wide uppercase">Projects</div>
            </div>
            <div class="text-center lg:text-left">
              <div class="font-display font-bold text-3xl gradient-text" data-count="3">0</div>
              <div class="text-xs text-sub mt-1 tracking-wide uppercase">Years Exp</div>
            </div>
            <div class="text-center lg:text-left">
              <div class="font-display font-bold text-3xl gradient-text" data-count="10">0</div>
              <div class="text-xs text-sub mt-1 tracking-wide uppercase">Tech Stack</div>
            </div>
          </div>

          <!-- Currently -->
          <div class="animate-on-scroll delay-3 flex flex-wrap gap-3">
            <div class="flex items-center gap-2 px-3 py-2 bg-accent/5 border border-accent/20 rounded-sm">
              <iconify-icon icon="lucide:zap" width="14" class="text-accent"></iconify-icon>
              <span class="text-xs text-accent font-medium">Building Health-Tech App</span>
            </div>
            <div class="flex items-center gap-2 px-3 py-2 bg-white/[0.03] border border-white/10 rounded-sm">
              <iconify-icon icon="lucide:brain" width="14" class="text-sub"></iconify-icon>
              <span class="text-xs text-sub font-medium">Learning Advanced AI/ML</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Tech Stack Section -->
  <section id="stack" class="relative py-24 md:py-32 px-6">
    <div class="absolute inset-0 bg-dark-800/50"></div>
    <div class="relative max-w-7xl mx-auto">
      <!-- Header -->
      <div class="text-center mb-16">
        <span class="animate-on-scroll text-[10px] font-semibold tracking-[0.25em] uppercase text-accent">Tech Stack</span>
        <h2 class="animate-on-scroll delay-1 font-display font-bold text-3xl md:text-4xl tracking-tight mt-3 mb-4">
          Tools I <span class="gradient-text">master</span>
        </h2>
        <p class="animate-on-scroll delay-2 text-sub font-light max-w-lg mx-auto">
          From frontend to backend, mobile to cloud — here's the technology I use to bring ideas to life.
        </p>
      </div>

      <!-- Tabs -->
      <div class="animate-on-scroll delay-2 flex flex-wrap justify-center gap-2 mb-12">
        <button class="tab-btn active px-5 py-2.5 text-xs font-semibold tracking-widest uppercase border border-white/10 rounded-sm transition-all duration-300" data-tab="mobile">
          <iconify-icon icon="lucide:smartphone" width="14" class="mr-1.5 align-middle"></iconify-icon>Mobile
        </button>
        <button class="tab-btn px-5 py-2.5 text-xs font-semibold tracking-widest uppercase text-sub border border-white/10 rounded-sm transition-all duration-300 hover:text-white" data-tab="backend">
          <iconify-icon icon="lucide:server" width="14" class="mr-1.5 align-middle"></iconify-icon>Backend
        </button>
        <button class="tab-btn px-5 py-2.5 text-xs font-semibold tracking-widest uppercase text-sub border border-white/10 rounded-sm transition-all duration-300 hover:text-white" data-tab="web">
          <iconify-icon icon="lucide:globe" width="14" class="mr-1.5 align-middle"></iconify-icon>Web
        </button>
        <button class="tab-btn px-5 py-2.5 text-xs font-semibold tracking-widest uppercase text-sub border border-white/10 rounded-sm transition-all duration-300 hover:text-white" data-tab="tools">
          <iconify-icon icon="lucide:wrench" width="14" class="mr-1.5 align-middle"></iconify-icon>Tools
        </button>
      </div>

      <!-- Mobile Tab -->
      <div class="tab-content active grid sm:grid-cols-2 lg:grid-cols-3 gap-4" id="tab-mobile">
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:flutter" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">Flutter</h3>
              <span class="text-[10px] text-accent tracking-wider uppercase">Primary</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">Cross-platform mobile apps with beautiful UI, state management (Riverpod, BLoC), and native integrations.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:95%"></div></div>
        </div>
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:react" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">React Native</h3>
              <span class="text-[10px] text-sub tracking-wider uppercase">Experienced</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">Native-feeling iOS & Android apps with hooks, navigation, and deep native module integration.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:88%"></div></div>
        </div>
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:dart" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">Dart</h3>
              <span class="text-[10px] text-sub tracking-wider uppercase">Fluent</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">Strong typing, async patterns, advanced OOP, and custom Flutter packages.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:92%"></div></div>
        </div>
      </div>

      <!-- Backend Tab -->
      <div class="tab-content grid sm:grid-cols-2 lg:grid-cols-3 gap-4" id="tab-backend">
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:nodejs-icon" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">Node.js</h3>
              <span class="text-[10px] text-accent tracking-wider uppercase">Primary</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">REST & GraphQL APIs, Express/Fastify, real-time services with WebSockets.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:90%"></div></div>
        </div>
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:python" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">Python</h3>
              <span class="text-[10px] text-sub tracking-wider uppercase">Experienced</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">Django/Flask APIs, scripting, data processing, and ML model integration.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:82%"></div></div>
        </div>
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:firebase" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">Firebase</h3>
              <span class="text-[10px] text-accent tracking-wider uppercase">Primary</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">Auth, Firestore, Cloud Functions, Storage, Push Notifications, and Analytics.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:93%"></div></div>
        </div>
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:mongodb-icon" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">MongoDB</h3>
              <span class="text-[10px] text-sub tracking-wider uppercase">Experienced</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">Schema design, aggregation pipelines, indexing, and Mongoose ODM.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:85%"></div></div>
        </div>
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:postgresql" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">PostgreSQL</h3>
              <span class="text-[10px] text-sub tracking-wider uppercase">Intermediate</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">Relational database design, complex queries, and Prisma ORM integration.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:75%"></div></div>
        </div>
      </div>

      <!-- Web Tab -->
      <div class="tab-content grid sm:grid-cols-2 lg:grid-cols-3 gap-4" id="tab-web">
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:react" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">React</h3>
              <span class="text-[10px] text-accent tracking-wider uppercase">Experienced</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">SPAs with Next.js, hooks, context, and modern React patterns.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:87%"></div></div>
        </div>
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:javascript" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">JavaScript / TS</h3>
              <span class="text-[10px] text-sub tracking-wider uppercase">Fluent</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">ES6+, TypeScript, DOM manipulation, and full-stack JS development.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:90%"></div></div>
        </div>
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:tailwindcss-icon" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">Tailwind CSS</h3>
              <span class="text-[10px] text-accent tracking-wider uppercase">Primary</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">Utility-first CSS, responsive design, dark modes, and custom themes.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:94%"></div></div>
        </div>
        <div class="skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm">
          <div class="flex items-center gap-3 mb-4">
            <iconify-icon icon="logos:html-5" width="32"></iconify-icon>
            <div>
              <h3 class="font-display font-semibold text-sm">HTML / CSS</h3>
              <span class="text-[10px] text-sub tracking-wider uppercase">Fluent</span>
            </div>
          </div>
          <p class="text-xs text-sub font-light leading-relaxed">Semantic markup, CSS Grid/Flexbox, animations, and accessibility.</p>
          <div class="mt-4 w-full bg-white/5 rounded-full h-1"><div class="bg-accent h-1 rounded-full" style="width:95%"></div></div>
        </div>
      </div>

      <!-- Tools Tab -->
      <div class="tab-content grid sm:grid-cols-2 lg:grid-cols-4 gap-4" id="tab-tools">
        <div class="skill-card p-5 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <iconify-icon icon="logos:git-icon" width="36" class="mb-3"></iconify-icon>
          <h3 class="font-display font-semibold text-sm">Git</h3>
          <span class="text-[10px] text-sub tracking-wider uppercase">Version Control</span>
        </div>
        <div class="skill-card p-5 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <iconify-icon icon="logos:docker-icon" width="36" class="mb-3"></iconify-icon>
          <h3 class="font-display font-semibold text-sm">Docker</h3>
          <span class="text-[10px] text-sub tracking-wider uppercase">Containers</span>
        </div>
        <div class="skill-card p-5 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <iconify-icon icon="logos:github-icon" width="36" class="mb-3" style="filter: invert(1);"></iconify-icon>
          <h3 class="font-display font-semibold text-sm">GitHub</h3>
          <span class="text-[10px] text-sub tracking-wider uppercase">CI/CD & Collab</span>
        </div>
        <div class="skill-card p-5 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <iconify-icon icon="logos:visual-studio-code" width="36" class="mb-3"></iconify-icon>
          <h3 class="font-display font-semibold text-sm">VS Code</h3>
          <span class="text-[10px] text-sub tracking-wider uppercase">IDE</span>
        </div>
        <div class="skill-card p-5 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <iconify-icon icon="logos:figma" width="28" class="mb-3"></iconify-icon>
          <h3 class="font-display font-semibold text-sm">Figma</h3>
          <span class="text-[10px] text-sub tracking-wider uppercase">Design</span>
        </div>
        <div class="skill-card p-5 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <iconify-icon icon="logos:postman-icon" width="36" class="mb-3"></iconify-icon>
          <h3 class="font-display font-semibold text-sm">Postman</h3>
          <span class="text-[10px] text-sub tracking-wider uppercase">API Testing</span>
        </div>
        <div class="skill-card p-5 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <iconify-icon icon="logos:linux-tux" width="36" class="mb-3"></iconify-icon>
          <h3 class="font-display font-semibold text-sm">Linux</h3>
          <span class="text-[10px] text-sub tracking-wider uppercase">Server Admin</span>
        </div>
        <div class="skill-card p-5 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <iconify-icon icon="logos:google-cloud" width="36" class="mb-3"></iconify-icon>
          <h3 class="font-display font-semibold text-sm">GCP</h3>
          <span class="text-[10px] text-sub tracking-wider uppercase">Cloud</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Projects Section -->
  <section id="projects" class="relative py-24 md:py-32 px-6">
    <div class="max-w-7xl mx-auto">
      <!-- Header -->
      <div class="text-center mb-16">
        <span class="animate-on-scroll text-[10px] font-semibold tracking-[0.25em] uppercase text-accent">Selected Work</span>
        <h2 class="animate-on-scroll delay-1 font-display font-bold text-3xl md:text-4xl tracking-tight mt-3 mb-4">
          Things I've <span class="gradient-text">built</span>
        </h2>
        <p class="animate-on-scroll delay-2 text-sub font-light max-w-lg mx-auto">
          A curated selection of projects that showcase my skills across mobile, backend, and web.
        </p>
      </div>

      <!-- Project Grid -->
      <div class="grid md:grid-cols-2 gap-6">
        <!-- Project 1 -->
        <div class="animate-on-scroll project-card group relative bg-dark-800 border border-white/5 rounded-sm overflow-hidden">
          <div class="aspect-[16/10] overflow-hidden">
            <img src="https://picsum.photos/seed/healthapp-delivery/800/500.jpg" alt="Health Product Delivery" class="project-img w-full h-full object-cover transition-transform duration-700 grayscale opacity-60 group-hover:grayscale-0 group-hover:opacity-80">
          </div>
          <div class="project-overlay absolute inset-0 bg-gradient-to-t from-dark-900 via-dark-900/60 to-transparent opacity-0 transition-opacity duration-500 flex items-end p-8">
            <div>
              <div class="flex flex-wrap gap-2 mb-3">
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-accent/20 text-accent rounded-sm">Flutter</span>
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-white/10 text-sub rounded-sm">Firebase</span>
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-white/10 text-sub rounded-sm">AI</span>
              </div>
              <p class="text-xs text-sub font-light leading-relaxed">AI-powered health product delivery with real-time tracking, smart recommendations, and seamless checkout.</p>
            </div>
          </div>
          <div class="p-6">
            <div class="flex items-center justify-between mb-2">
              <span class="text-[10px] text-accent font-semibold tracking-widest uppercase">Featured</span>
              <span class="text-[10px] text-sub tracking-wider">2024</span>
            </div>
            <h3 class="font-display font-bold text-xl tracking-tight">Health Product Delivery</h3>
            <p class="text-xs text-sub mt-1 font-light">Mobile App • Flutter + Firebase</p>
          </div>
        </div>

        <!-- Project 2 -->
        <div class="animate-on-scroll delay-1 project-card group relative bg-dark-800 border border-white/5 rounded-sm overflow-hidden">
          <div class="aspect-[16/10] overflow-hidden">
            <img src="https://picsum.photos/seed/ai-chatbot-mobile/800/500.jpg" alt="AI Chatbot" class="project-img w-full h-full object-cover transition-transform duration-700 grayscale opacity-60 group-hover:grayscale-0 group-hover:opacity-80">
          </div>
          <div class="project-overlay absolute inset-0 bg-gradient-to-t from-dark-900 via-dark-900/60 to-transparent opacity-0 transition-opacity duration-500 flex items-end p-8">
            <div>
              <div class="flex flex-wrap gap-2 mb-3">
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-accent/20 text-accent rounded-sm">React Native</span>
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-white/10 text-sub rounded-sm">Node.js</span>
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-white/10 text-sub rounded-sm">OpenAI</span>
              </div>
              <p class="text-xs text-sub font-light leading-relaxed">Conversational AI chatbot with context memory, multi-platform support, and custom personality tuning.</p>
            </div>
          </div>
          <div class="p-6">
            <div class="flex items-center justify-between mb-2">
              <span class="text-[10px] text-sub font-semibold tracking-widest uppercase">Mobile + Backend</span>
              <span class="text-[10px] text-sub tracking-wider">2024</span>
            </div>
            <h3 class="font-display font-bold text-xl tracking-tight">AI Chatbot Platform</h3>
            <p class="text-xs text-sub mt-1 font-light">Cross-Platform • React Native + Node</p>
          </div>
        </div>

        <!-- Project 3 -->
        <div class="animate-on-scroll project-card group relative bg-dark-800 border border-white/5 rounded-sm overflow-hidden">
          <div class="aspect-[16/10] overflow-hidden">
            <img src="https://picsum.photos/seed/ecommerce-web-dash/800/500.jpg" alt="E-Commerce" class="project-img w-full h-full object-cover transition-transform duration-700 grayscale opacity-60 group-hover:grayscale-0 group-hover:opacity-80">
          </div>
          <div class="project-overlay absolute inset-0 bg-gradient-to-t from-dark-900 via-dark-900/60 to-transparent opacity-0 transition-opacity duration-500 flex items-end p-8">
            <div>
              <div class="flex flex-wrap gap-2 mb-3">
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-accent/20 text-accent rounded-sm">React</span>
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-white/10 text-sub rounded-sm">Node.js</span>
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-white/10 text-sub rounded-sm">MongoDB</span>
              </div>
              <p class="text-xs text-sub font-light leading-relaxed">Full-stack e-commerce with admin dashboard, payment integration, and real-time inventory management.</p>
            </div>
          </div>
          <div class="p-6">
            <div class="flex items-center justify-between mb-2">
              <span class="text-[10px] text-sub font-semibold tracking-widest uppercase">Full Stack</span>
              <span class="text-[10px] text-sub tracking-wider">2023</span>
            </div>
            <h3 class="font-display font-bold text-xl tracking-tight">E-Commerce Platform</h3>
            <p class="text-xs text-sub mt-1 font-light">Web • React + Node + MongoDB</p>
          </div>
        </div>

        <!-- Project 4 -->
        <div class="animate-on-scroll delay-1 project-card group relative bg-dark-800 border border-white/5 rounded-sm overflow-hidden">
          <div class="aspect-[16/10] overflow-hidden">
            <img src="https://picsum.photos/seed/fitness-tracker-app/800/500.jpg" alt="Fitness Tracker" class="project-img w-full h-full object-cover transition-transform duration-700 grayscale opacity-60 group-hover:grayscale-0 group-hover:opacity-80">
          </div>
          <div class="project-overlay absolute inset-0 bg-gradient-to-t from-dark-900 via-dark-900/60 to-transparent opacity-0 transition-opacity duration-500 flex items-end p-8">
            <div>
              <div class="flex flex-wrap gap-2 mb-3">
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-accent/20 text-accent rounded-sm">Flutter</span>
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-white/10 text-sub rounded-sm">Dart</span>
                <span class="px-2 py-1 text-[9px] font-bold tracking-wider uppercase bg-white/10 text-sub rounded-sm">Firebase</span>
              </div>
              <p class="text-xs text-sub font-light leading-relaxed">Fitness tracking with workout plans, progress charts, social features, and health data sync.</p>
            </div>
          </div>
          <div class="p-6">
            <div class="flex items-center justify-between mb-2">
              <span class="text-[10px] text-sub font-semibold tracking-widest uppercase">Mobile App</span>
              <span class="text-[10px] text-sub tracking-wider">2023</span>
            </div>
            <h3 class="font-display font-bold text-xl tracking-tight">Fitness Tracker App</h3>
            <p class="text-xs text-sub mt-1 font-light">Mobile • Flutter + Firebase</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- What I Bring Section -->
  <section class="relative py-24 md:py-32 px-6">
    <div class="absolute inset-0 bg-dark-800/50"></div>
    <div class="relative max-w-7xl mx-auto">
      <div class="text-center mb-16">
        <span class="animate-on-scroll text-[10px] font-semibold tracking-[0.25em] uppercase text-accent">Why Me</span>
        <h2 class="animate-on-scroll delay-1 font-display font-bold text-3xl md:text-4xl tracking-tight mt-3">
          What I <span class="gradient-text">bring</span>
        </h2>
      </div>
      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <div class="animate-on-scroll skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <div class="w-12 h-12 mx-auto mb-4 rounded-full bg-accent/10 flex items-center justify-center">
            <iconify-icon icon="lucide:layers" width="22" class="text-accent"></iconify-icon>
          </div>
          <h3 class="font-display font-semibold text-sm mb-2">Full-Spectrum</h3>
          <p class="text-xs text-sub font-light leading-relaxed">Mobile, backend, and web — I handle the entire stack end-to-end.</p>
        </div>
        <div class="animate-on-scroll delay-1 skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <div class="w-12 h-12 mx-auto mb-4 rounded-full bg-accent/10 flex items-center justify-center">
            <iconify-icon icon="lucide:rocket" width="22" class="text-accent"></iconify-icon>
          </div>
          <h3 class="font-display font-semibold text-sm mb-2">Ship Fast</h3>
          <p class="text-xs text-sub font-light leading-relaxed">Rapid prototyping to production-ready code without sacrificing quality.</p>
        </div>
        <div class="animate-on-scroll delay-2 skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <div class="w-12 h-12 mx-auto mb-4 rounded-full bg-accent/10 flex items-center justify-center">
            <iconify-icon icon="lucide:brain" width="22" class="text-accent"></iconify-icon>
          </div>
          <h3 class="font-display font-semibold text-sm mb-2">AI-Forward</h3>
          <p class="text-xs text-sub font-light leading-relaxed">Integrating AI/ML capabilities into mobile and web applications.</p>
        </div>
        <div class="animate-on-scroll delay-3 skill-card p-6 bg-dark-900/80 border border-white/5 rounded-sm text-center">
          <div class="w-12 h-12 mx-auto mb-4 rounded-full bg-accent/10 flex items-center justify-center">
            <iconify-icon icon="lucide:heart-handshake" width="22" class="text-accent"></iconify-icon>
          </div>
          <h3 class="font-display font-semibold text-sm mb-2">User-Centric</h3>
          <p class="text-xs text-sub font-light leading-relaxed">Every decision is guided by how it impacts the end user's experience.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="relative py-24 md:py-32 px-6">
    <div class="max-w-7xl mx-auto">
      <div class="grid lg:grid-cols-2 gap-16">
        <!-- Left -->
        <div>
          <span class="animate-on-scroll text-[10px] font-semibold tracking-[0.25em] uppercase text-accent">Get In Touch</span>
          <h2 class="animate-on-scroll delay-1 font-display font-bold text-3xl md:text-4xl tracking-tight mt-3 mb-6">
            Let's build something<br><span class="gradient-text">amazing</span>
          </h2>
          <p class="animate-on-scroll delay-2 text-sub font-light leading-relaxed mb-10">
            Whether you have a project idea, need a technical consult, or just want to connect — I'd love to hear from you. I'm currently open to freelance, collaboration, and full-time opportunities.
          </p>

          <!-- Contact Links -->
          <div class="space-y-4">
            <a href="mailto:samsonchinthenga29@gmail.com" class="animate-on-scroll delay-2 contact-link flex items-center gap-4 p-4 border border-white/5 rounded-sm group">
              <div class="contact-icon w-10 h-10 flex items-center justify-center bg-accent/10 rounded-sm transition-all duration-300">
                <iconify-icon icon="lucide:mail" width="18" class="text-accent"></iconify-icon>
              </div>
              <div>
                <div class="text-xs text-sub mb-0.5">Email</div>
                <div class="text-sm font-medium">samsonchinthenga29@gmail.com</div>
              </div>
              <iconify-icon icon="lucide:arrow-up-right" width="16" class="ml-auto text-sub group-hover:text-accent transition-colors"></iconify-icon>
            </a>
            <a href="https://www.linkedin.com/in/samson-chinthenga-5ab6aa321" target="_blank" class="animate-on-scroll delay-3 contact-link flex items-center gap-4 p-4 border border-white/5 rounded-sm group">
              <div class="contact-icon w-10 h-10 flex items-center justify-center bg-accent/10 rounded-sm transition-all duration-300">
                <iconify-icon icon="lucide:linkedin" width="18" class="text-accent"></iconify-icon>
              </div>
              <div>
                <div class="text-xs text-sub mb-0.5">LinkedIn</div>
                <div class="text-sm font-medium">Samson Chinthenga</div>
              </div>
              <iconify-icon icon="lucide:arrow-up-right" width="16" class="ml-auto text-sub group-hover:text-accent transition-colors"></iconify-icon>
            </a>
            <a href="https://github.com/" target="_blank" class="animate-on-scroll delay-4 contact-link flex items-center gap-4 p-4 border border-white/5 rounded-sm group">
              <div class="contact-icon w-10 h-10 flex items-center justify-center bg-accent/10 rounded-sm transition-all duration-300">
                <iconify-icon icon="lucide:github" width="18" class="text-accent"></iconify-icon>
              </div>
              <div>
                <div class="text-xs text-sub mb-0.5">GitHub</div>
                <div class="text-sm font-medium">View my repositories</div>
              </div>
              <iconify-icon icon="lucide:arrow-up-right" width="16" class="ml-auto text-sub group-hover:text-accent transition-colors"></iconify-icon>
            </a>
          </div>
        </div>

        <!-- Right: CTA Card -->
        <div class="animate-on-scroll delay-2 flex items-center">
          <div class="relative w-full p-8 md:p-12 border border-white/5 rounded-sm bg-dark-800/50 overflow-hidden">
            <!-- Background accent -->
            <div class="absolute -top-20 -right-20 w-60 h-60 bg-accent/5 rounded-full blur-[80px]"></div>
            <div class="absolute -bottom-10 -left-10 w-40 h-40 bg-accent/3 rounded-full blur-[60px]"></div>
            
            <div class="relative">
              <div class="text-6xl font-display font-bold gradient-text mb-4">"'</div>
              <blockquote class="text-lg font-light text-white/80 leading-relaxed mb-6">
                Technology can change lives. I build software that proves it — one app at a time.
              </blockquote>
              <div class="flex items-center gap-3">
                <div class="w-10 h-10 rounded-full bg-accent/20 flex items-center justify-center">
                  <span class="text-accent font-bold text-sm">SC</span>
                </div>
                <div>
                  <div class="text-sm font-semibold">Samson Chinthenga</div>
                  <div class="text-xs text-sub">Software Developer</div>
                </div>
              </div>
            </div>

            <!-- Decorative elements -->
            <div class="absolute top-4 right-4 flex flex-col gap-1.5">
              <div class="w-1.5 h-1.5 rounded-full bg-accent/30"></div>
              <div class="w-1.5 h-1.5 rounded-full bg-accent/20"></div>
              <div class="w-1.5 h-1.5 rounded-full bg-accent/10"></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="border-t border-white/5 py-12 px-6">
    <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
      <div class="flex items-center gap-3">
        <span class="font-display font-bold text-lg"><span class="text-accent">S</span><span class="text-white">.</span></span>
        <span class="text-xs text-sub font-light">© 2024 Samson Chinthenga. Crafted with code & caffeine.</span>
      </div>
      <div class="flex items-center gap-6">
        <a href="mailto:samsonchinthenga29@gmail.com" class="text-sub hover:text-accent transition-colors">
          <iconify-icon icon="lucide:mail" width="18"></iconify-icon>
        </a>
        <a href="https://www.linkedin.com/in/samson-chinthenga-5ab6aa321" target="_blank" class="text-sub hover:text-accent transition-colors">
          <iconify-icon icon="lucide:linkedin" width="18"></iconify-icon>
        </a>
        <a href="https://github.com/" target="_blank" class="text-sub hover:text-accent transition-colors">
          <iconify-icon icon="lucide:github" width="18"></iconify-icon>
        </a>
      </div>
    </div>
  </footer>

  <!-- Back to Top -->
  <button id="backToTop" class="fixed bottom-8 right-8 w-10 h-10 bg-accent/10 border border-accent/30 rounded-sm flex items-center justify-center text-accent opacity-0 translate-y-4 transition-all duration-300 hover:bg-accent/20 z-40 cursor-pointer">
    <iconify-icon icon="lucide:arrow-up" width="16"></iconify-icon>
  </button>

  <script>
    // Mobile Menu Toggle
    const menuBtn = document.getElementById('menuBtn');
    const mobileMenu = document.getElementById('mobileMenu');
    let menuOpen = false;
    menuBtn.addEventListener('click', () => {
      menuOpen = !menuOpen;
      mobileMenu.classList.toggle('hidden');
      menuBtn.innerHTML = menuOpen 
        ? '<iconify-icon icon="lucide:x" width="24"></iconify-icon>' 
        : '<iconify-icon icon="lucide:menu" width="24"></iconify-icon>';
    });
    document.querySelectorAll('.mobile-link').forEach(link => {
      link.addEventListener('click', () => {
        mobileMenu.classList.add('hidden');
        menuOpen = false;
        menuBtn.innerHTML = '<iconify-icon icon="lucide:menu" width="24"></iconify-icon>';
      });
    });

    // Navbar background on scroll
    const navbar = document.getElementById('navbar');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 50) {
        navbar.style.background = 'rgba(5,5,10,0.9)';
        navbar.style.backdropFilter = 'blur(12px)';
        navbar.style.borderBottom = '1px solid rgba(255,255,255,0.05)';
      } else {
        navbar.style.background = 'transparent';
        navbar.style.backdropFilter = 'none';
        navbar.style.borderBottom = 'none';
      }
    });

    // Scroll animations
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });

    document.querySelectorAll('.animate-on-scroll').forEach(el => observer.observe(el));

    // Tab switching
    document.querySelectorAll('.tab-btn').forEach(btn => {
      btn.addEventListener('click', () => {
        document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
        document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
        btn.classList.add('active');
        document.getElementById('tab-' + btn.dataset.tab).classList.add('active');
      });
    });

    // Counter animation
    const counterObserver = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          const el = entry.target;
          const target = parseInt(el.dataset.count);
          let current = 0;
          const increment = target / 40;
          const timer = setInterval(() => {
            current += increment;
            if (current >= target) {
              current = target;
              clearInterval(timer);
            }
            el.textContent = Math.floor(current) + '+';
          }, 40);
          counterObserver.unobserve(el);
        }
      });
    }, { threshold: 0.5 });

    document.querySelectorAll('[data-count]').forEach(el => counterObserver.observe(el));

    // Back to top button
    const backToTop = document.getElementById('backToTop');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 600) {
        backToTop.style.opacity = '1';
        backToTop.style.transform = 'translateY(0)';
      } else {
        backToTop.style.opacity = '0';
        backToTop.style.transform = 'translateY(16px)';
      }
    });
    backToTop.addEventListener('click', () => {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    // Smooth scroll for anchor links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function(e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
          target.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
      });
    });
  </script>
</body>
</html>
