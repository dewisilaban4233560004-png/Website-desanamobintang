<!DOCTYPE html>
<html lang="id" class="scroll-smooth">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Desa Namo Bintang — Website Resmi</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
<link href="https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.css" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.js"></script>
<script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.1/dist/chart.umd.min.js"></script>
<script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
<script>
tailwind.config = {
  darkMode: 'class',
  theme: { extend: {
    colors: { primary: { DEFAULT: '#0B3C91', light: '#1E5BB8', soft: '#60A5FA' }, gold: { DEFAULT: '#D4AF37', light: '#F5C542', deep: '#B8941F' }, accent: { DEFAULT: '#10B981', light: '#34D399' } },
    fontFamily: { display: ['Poppins', 'sans-serif'], body: ['Inter', 'sans-serif'] },
  }}
}
</script>
<style>
  * { -webkit-font-smoothing: antialiased; }
  html, body { font-family: 'Inter', sans-serif; }
  h1,h2,h3,h4,h5,h6,.font-display { font-family: 'Poppins', sans-serif; letter-spacing: -0.02em; }
  
  body { position: relative; background-color: #f8fafc; }
  body::before {
    content: '';
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background-image: url('https://z-cdn-media.chatglm.cn/files/f09c0a12-a0b5-46ce-a728-c0f583328dc9.png?auth_key=1886614175-a7011d5416d6435995606971fd457f2b-0-ebb113cd6386fc60e927dfefe4a8a37a');
    background-size: 400px;
    background-position: center;
    background-repeat: repeat;
    opacity: 0.04;
    z-index: 0;
    pointer-events: none;
  }
  .dark body::before { opacity: 0.02; filter: grayscale(1) brightness(2); }

  nav, section, footer, #loader, #lightbox, #backToTop { position: relative; z-index: 1; }

  .glass { background: rgba(255,255,255,0.7); backdrop-filter: blur(16px) saturate(180%); border: 1px solid rgba(255,255,255,0.5); box-shadow: 0 4px 20px rgba(11, 60, 145, 0.05); }
  .dark .glass { background: rgba(15,23,42,0.7); border: 1px solid rgba(255,255,255,0.08); }
  
  .glass-strong { background: rgba(255,255,255,0.9); backdrop-filter: blur(20px) saturate(180%); border: 1px solid rgba(255,255,255,0.6); box-shadow: 0 8px 32px rgba(11, 60, 145, 0.08); }
  .dark .glass-strong { background: rgba(15,23,42,0.9); border: 1px solid rgba(255,255,255,0.05); box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3); }

  .gradient-text-gold { background: linear-gradient(135deg, #D4AF37, #F5C542, #D4AF37); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; }
  .gradient-text-blue { background: linear-gradient(135deg, #0B3C91, #1E5BB8, #60A5FA); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; }
  
  .hero-gradient { background: radial-gradient(ellipse 80% 50% at 20% 30%, rgba(30,91,184,0.4), transparent 50%), radial-gradient(ellipse 60% 40% at 80% 70%, rgba(212,175,55,0.15), transparent 50%), linear-gradient(135deg, #061b4d, #0B3C91, #1E5BB8); }
  
  @keyframes float { 0%,100% { transform: translateY(0) rotate(0deg); } 50% { transform: translateY(-25px) rotate(2deg); } }
  .float-anim { animation: float 6s ease-in-out infinite; }
  
  @keyframes pulseGlow { 0%,100% { box-shadow: 0 0 40px rgba(212,175,55,0.3), 0 0 80px rgba(11,60,145,0.2); } 50% { box-shadow: 0 0 60px rgba(212,175,55,0.5), 0 0 120px rgba(11,60,145,0.4); } }
  .pulse-glow { animation: pulseGlow 4s ease-in-out infinite; }
  
  .loader-ring { width: 70px; height: 70px; border: 4px solid rgba(212,175,55,0.2); border-top-color: #D4AF37; border-right-color: #0B3C91; border-radius: 50%; animation: spin 1.2s linear infinite; }
  @keyframes spin { to { transform: rotate(360deg); } }
  
  @keyframes marquee { 0% { transform: translateX(0); } 100% { transform: translateX(-50%); } }
  .marquee-track { display: inline-flex; animation: marquee 40s linear infinite; white-space: nowrap; }
  
  .timeline-line { background: linear-gradient(180deg, transparent, #0B3C91 10%, #1E5BB8 50%, #D4AF37 90%, transparent); }
  .dark .timeline-line { background: linear-gradient(180deg, transparent, #60A5FA 10%, #1E5BB8 50%, #D4AF37 90%, transparent); }
  
  .card-hover { transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1); }
  .card-hover:hover { transform: translateY(-6px); box-shadow: 0 20px 40px -10px rgba(11,60,145,0.2), 0 0 0 1px rgba(212,175,55,0.1); }
  
  .btn-shimmer { position: relative; overflow: hidden; }
  .btn-shimmer::after { content: ''; position: absolute; top: 0; left: -100%; width: 100%; height: 100%; background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent); transition: left 0.6s; }
  .btn-shimmer:hover::after { left: 100%; }
  
  .org-line { background: linear-gradient(180deg, #0B3C91, #1E5BB8); }
  .masonry-item { break-inside: avoid; margin-bottom: 1rem; }
  
  ::-webkit-scrollbar { width: 8px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: linear-gradient(180deg, #0B3C91, #1E5BB8); border-radius: 10px; }
  ::-webkit-scrollbar-thumb:hover { background: #D4AF37; }
  
  .kadus-img { object-position: center 15%; }
  .org-img { object-position: top center; }
  .mandela-img { object-position: center 15%; }
  
  .progress-bar-track { background: rgba(148, 163, 184, 0.15); border-radius: 20px; height: 6px; overflow: hidden; }
  .progress-bar-fill { height: 100%; border-radius: 20px; transition: width 1.5s cubic-bezier(0.16, 1, 0.3, 1); box-shadow: 0 0 10px rgba(11, 60, 145, 0.3); }
  
  .gallery-item { position: relative; overflow: hidden; }
  .gallery-item img { transition: transform 0.6s cubic-bezier(0.16, 1, 0.3, 1); }
  .gallery-item:hover img { transform: scale(1.08); }
  .gallery-caption { position: absolute; bottom: 0; left: 0; right: 0; padding: 2rem 1rem 1rem; background: linear-gradient(to top, rgba(0,0,0,0.85), transparent); opacity: 0; transform: translateY(10px); transition: all 0.4s ease; }
  .gallery-item:hover .gallery-caption { opacity: 1; transform: translateY(0); }

  /* Map Styling */
  .map-frame { filter: grayscale(20%) contrast(1.1); border: 4px solid rgba(255,255,255,0.8); box-shadow: 0 20px 50px -10px rgba(11,60,145,0.2); }
  .dark .map-frame { border-color: rgba(30,41,59,0.8); filter: grayscale(40%) invert(90%) hue-rotate(180deg) contrast(0.9); }
</style>
</head>
<body class="bg-slate-50 dark:bg-[#0a0f1f] text-slate-800 dark:text-slate-200 overflow-x-hidden">

<!-- LOADER -->
<div id="loader" class="fixed inset-0 z-[100] flex flex-col items-center justify-center bg-[#061b4d] transition-opacity duration-700">
  <div class="loader-ring mb-6"></div>
  <p class="text-white/80 font-display font-medium tracking-widest text-sm">DESA NAMO BINTANG</p>
</div>

<!-- RUNNING TEXT -->
<div class="bg-gradient-to-r from-primary via-primary-light to-primary text-white py-2 overflow-hidden relative z-40 shadow-lg">
  <div class="flex items-center">
    <div class="flex-shrink-0 bg-gold text-primary px-4 py-1 text-xs font-bold rounded-r-full mr-4 flex items-center gap-1.5"><i data-lucide="megaphone" class="w-3.5 h-3.5"></i> PENGUMUMAN</div>
    <div class="overflow-hidden flex-1"><div class="marquee-track text-sm">
      <span class="px-8">📢 Pendaftaran Program Bantuan Sosial Desa telah dibuka — silakan mengunjungi Kantor Desa.</span>
      <span class="px-8">🗓️ Posyandu Lansia rutin dilaksanakan setiap tanggal 11 dan Posyandu Balita setiap tanggal 12 di Aula Kantor Desa Namo Bintang.</span>
      <span class="px-8">📋 Musyawarah Desa (Musdes) akan dilaksanakan akhir bulan ini — partisipasi masyarakat sangat diharapkan.</span>
      <span class="px-8">📢 Pendaftaran Program Bantuan Sosial Desa telah dibuka — silakan mengunjungi Kantor Desa.</span>
      <span class="px-8">🗓️ Posyandu Lansia rutin dilaksanakan setiap tanggal 11 dan Posyandu Balita setiap tanggal 12 di Aula Kantor Desa Namo Bintang.</span>
    </div></div>
  </div>
</div>

<!-- NAVBAR -->
<nav id="navbar" class="sticky top-0 z-50 transition-all duration-300">
  <div class="glass-strong border-b border-slate-200/50 dark:border-slate-800/50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16 lg:h-20">
        <a href="#beranda" class="flex items-center gap-3 group">
          <div class="relative w-11 h-11 lg:w-12 lg:h-12" id="navLogo"></div>
          <div>
            <p class="font-display font-bold text-primary dark:text-white text-sm lg:text-base leading-tight tracking-wide">DESA NAMO BINTANG</p>
            <p class="text-[10px] lg:text-xs text-slate-500 dark:text-slate-400 leading-tight">Kabupaten Deli Serdang</p>
          </div>
        </a>
        <div class="hidden xl:flex items-center gap-1">
          <a href="#beranda" class="px-3 py-2 text-sm font-medium hover:text-primary dark:hover:text-gold transition-colors">Beranda</a>
          <div class="relative group">
            <button class="px-3 py-2 text-sm font-medium flex items-center gap-1 hover:text-primary dark:hover:text-gold transition-colors">Profil Desa <i data-lucide="chevron-down" class="w-3.5 h-3.5"></i></button>
            <div class="absolute top-full left-0 mt-2 w-56 opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-300 translate-y-2 group-hover:translate-y-0">
              <div class="glass-strong rounded-2xl p-2 shadow-2xl border border-slate-200/50 dark:border-slate-800/50">
                <a href="#profil" class="block px-4 py-2.5 text-sm rounded-xl hover:bg-primary/10 transition-colors">Tentang Desa</a>
                <a href="#sejarah" class="block px-4 py-2.5 text-sm rounded-xl hover:bg-primary/10 transition-colors">Sejarah</a>
                <a href="#visi-misi" class="block px-4 py-2.5 text-sm rounded-xl hover:bg-primary/10 transition-colors">Visi & Misi</a>
                <a href="#pemerintahan" class="block px-4 py-2.5 text-sm rounded-xl hover:bg-primary/10 transition-colors">Pemerintahan</a>
              </div>
            </div>
          </div>
          <a href="#potensi" class="px-3 py-2 text-sm font-medium hover:text-primary dark:hover:text-gold transition-colors">Potensi Desa</a>
          <a href="#statistik" class="px-3 py-2 text-sm font-medium hover:text-primary dark:hover:text-gold transition-colors">Statistik</a>
          <a href="#galeri" class="px-3 py-2 text-sm font-medium hover:text-primary dark:hover:text-gold transition-colors">Galeri</a>
          <a href="#berita" class="px-3 py-2 text-sm font-medium hover:text-primary dark:hover:text-gold transition-colors">Informasi</a>
          <a href="#kontak" class="px-3 py-2 text-sm font-medium hover:text-primary dark:hover:text-gold transition-colors">Kontak</a>
        </div>
        <div class="flex items-center gap-2">
          <button onclick="toggleSearch()" class="p-2.5 rounded-xl hover:bg-primary/10 transition-colors"><i data-lucide="search" class="w-5 h-5"></i></button>
          <button onclick="toggleDarkMode()" class="p-2.5 rounded-xl hover:bg-primary/10 transition-colors"><i data-lucide="moon" class="w-5 h-5" id="themeIcon"></i></button>
          <a href="#kontak" class="hidden md:inline-flex btn-shimmer items-center gap-2 px-5 py-2.5 bg-gradient-to-r from-primary to-primary-light text-white text-sm font-semibold rounded-xl shadow-md hover:shadow-xl transition-shadow"><i data-lucide="mail" class="w-4 h-4"></i> Hubungi</a>
          <button onclick="toggleMobileMenu()" class="xl:hidden p-2.5 rounded-xl hover:bg-primary/10 transition-colors"><i data-lucide="menu" class="w-5 h-5"></i></button>
        </div>
      </div>
    </div>
  </div>
  <div id="mobileMenu" class="xl:hidden hidden glass-strong border-b border-slate-200/50 dark:border-slate-800/50">
    <div class="px-4 py-4 space-y-1 max-h-[80vh] overflow-y-auto">
      <a href="#beranda" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-primary/10 font-medium transition-colors">Beranda</a>
      <a href="#profil" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-primary/10 font-medium transition-colors">Profil Desa</a>
      <a href="#sejarah" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-primary/10 font-medium transition-colors">Sejarah</a>
      <a href="#visi-misi" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-primary/10 font-medium transition-colors">Visi & Misi</a>
      <a href="#pemerintahan" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-primary/10 font-medium transition-colors">Pemerintahan</a>
      <a href="#potensi" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-primary/10 font-medium transition-colors">Potensi Desa</a>
      <a href="#statistik" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-primary/10 font-medium transition-colors">Statistik</a>
      <a href="#galeri" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-primary/10 font-medium transition-colors">Galeri</a>
      <a href="#berita" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-primary/10 font-medium transition-colors">Informasi</a>
      <a href="#kontak" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-primary/10 font-medium transition-colors">Kontak</a>
    </div>
  </div>
  <div id="searchOverlay" class="hidden fixed inset-0 z-50 bg-black/60 backdrop-blur-md" onclick="toggleSearch(event)">
    <div class="max-w-2xl mx-auto mt-32 px-4" onclick="event.stopPropagation()">
      <div class="glass-strong rounded-2xl p-2 shadow-2xl">
        <div class="flex items-center gap-3 px-4">
          <i data-lucide="search" class="w-5 h-5 text-slate-400"></i>
          <input type="text" id="globalSearch" placeholder="Cari di website desa..." class="flex-1 bg-transparent border-0 outline-none py-3 text-base dark:text-white">
          <button onclick="toggleSearch()" class="p-1.5 rounded-lg hover:bg-slate-200 dark:hover:bg-slate-700 transition-colors"><i data-lucide="x" class="w-5 h-5"></i></button>
        </div>
        <div id="searchResults" class="max-h-80 overflow-y-auto p-2"></div>
      </div>
    </div>
  </div>
</nav>

<!-- HERO -->
<section id="beranda" class="relative min-h-screen flex items-center overflow-hidden hero-gradient">
  <div class="absolute inset-0 flex items-center justify-center pointer-events-none opacity-[0.07]"><div id="heroWatermark" class="w-[800px] h-[800px] max-w-[90vw]"></div></div>
  <div class="absolute top-20 left-10 w-72 h-72 bg-gold/10 rounded-full blur-3xl"></div>
  <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20 w-full">
    <div class="grid lg:grid-cols-2 gap-12 items-center">
      <div data-aos="fade-right">
        <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass border border-white/20 mb-6"><span class="w-2 h-2 bg-accent rounded-full animate-pulse"></span><span class="text-white/90 text-xs font-medium tracking-wider">PEMERINTAH DESA NAMO BINTANG</span></div>
        <p class="text-gold-light text-lg font-medium tracking-widest mb-3 font-display">SELAMAT DATANG DI</p>
        <h1 class="font-display font-black text-4xl sm:text-5xl lg:text-6xl xl:text-7xl text-white leading-[1.05] mb-4">WEBSITE RESMI<br><span class="gradient-text-gold">DESA NAMO BINTANG</span></h1>
        <div class="flex items-center gap-3 mb-8"><div class="h-px w-12 bg-gold"></div><p class="text-white/80 text-base lg:text-lg font-light">Kecamatan Pancur Batu • Kabupaten Deli Serdang<br>Provinsi Sumatera Utara</p></div>
        <div class="flex flex-wrap gap-4">
          <a href="#profil" class="btn-shimmer group inline-flex items-center gap-2 px-7 py-3.5 bg-gradient-to-r from-gold to-gold-light text-primary font-semibold rounded-xl shadow-lg hover:shadow-2xl transition-shadow"><i data-lucide="info" class="w-4 h-4"></i> Profil Desa <i data-lucide="arrow-right" class="w-4 h-4 group-hover:translate-x-1 transition-transform"></i></a>
          <a href="#berita" class="btn-shimmer inline-flex items-center gap-2 px-7 py-3.5 bg-white/10 border border-white/30 text-white font-semibold rounded-xl hover:bg-white/20 transition-colors"><i data-lucide="newspaper" class="w-4 h-4"></i> Berita Desa</a>
        </div>
      </div>
      <div data-aos="fade-left" data-aos-delay="200" class="flex justify-center lg:justify-end">
        <div class="relative">
          <div class="absolute inset-0 rounded-full bg-gold/20 blur-3xl scale-110"></div>
          <div class="absolute inset-0 rounded-full border border-gold/20 animate-ping" style="animation-duration: 3s;"></div>
          <div class="relative float-anim">
            <div class="w-64 h-64 sm:w-80 sm:h-80 lg:w-96 lg:h-96 rounded-full glass-strong border-2 border-gold/30 pulse-glow flex items-center justify-center p-8"><div id="heroLogo" class="w-full h-full"></div></div>
            <div class="absolute -top-4 -left-4 glass-strong rounded-2xl px-4 py-3 border border-gold/30 shadow-xl"><div class="flex items-center gap-2"><div class="w-10 h-10 rounded-xl bg-gradient-to-br from-accent to-accent-light flex items-center justify-center"><i data-lucide="map-pin" class="w-5 h-5 text-white"></i></div><div><p class="text-[10px] text-slate-500">Provinsi</p><p class="text-xs font-bold text-primary dark:text-white">Sumatera Utara</p></div></div></div>
            <div class="absolute -bottom-4 -right-4 glass-strong rounded-2xl px-4 py-3 border border-gold/30 shadow-xl"><div class="flex items-center gap-2"><div class="w-10 h-10 rounded-xl bg-gradient-to-br from-primary to-primary-light flex items-center justify-center"><i data-lucide="building-2" class="w-5 h-5 text-white"></i></div><div><p class="text-[10px] text-slate-500">Kabupaten</p><p class="text-xs font-bold text-primary dark:text-white">Deli Serdang</p></div></div></div>
          </div>
        </div>
      </div>
    </div>
    <div data-aos="fade-up" data-aos-delay="400" class="grid grid-cols-2 lg:grid-cols-4 gap-4 mt-16 lg:mt-24">
      <div class="glass-strong rounded-2xl p-5 border border-white/30 card-hover group"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-primary to-primary-light flex items-center justify-center group-hover:scale-110 transition-transform mb-3"><i data-lucide="users" class="w-6 h-6 text-white"></i></div><p class="text-3xl font-display font-bold text-primary dark:text-white counter-stat" data-target="6545">0</p><p class="text-xs text-slate-500 mt-1">Jumlah Penduduk</p></div>
      <div class="glass-strong rounded-2xl p-5 border border-white/30 card-hover group"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center group-hover:scale-110 transition-transform mb-3"><i data-lucide="home" class="w-6 h-6 text-white"></i></div><p class="text-3xl font-display font-bold text-primary dark:text-white counter-stat" data-target="1803">0</p><p class="text-xs text-slate-500 mt-1">Jumlah KK</p></div>
      <div class="glass-strong rounded-2xl p-5 border border-white/30 card-hover group"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-accent to-accent-light flex items-center justify-center group-hover:scale-110 transition-transform mb-3"><i data-lucide="map" class="w-6 h-6 text-white"></i></div><p class="text-3xl font-display font-bold text-primary dark:text-white counter-stat" data-target="7">0</p><p class="text-xs text-slate-500 mt-1">Jumlah Dusun</p></div>
      <div class="glass-strong rounded-2xl p-5 border border-white/30 card-hover group"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-primary-light to-primary-soft flex items-center justify-center group-hover:scale-110 transition-transform mb-3"><i data-lucide="land-plot" class="w-6 h-6 text-white"></i></div><p class="text-3xl font-display font-bold text-primary dark:text-white">±489<span class="text-lg"> Ha</span></p><p class="text-xs text-slate-500 mt-1">Luas Wilayah</p></div>
    </div>
  </div>
</section>

<!-- PROFIL -->
<section id="profil" class="py-20 lg:py-28 relative">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="text-center mb-16" data-aos="fade-up"><span class="inline-block px-4 py-1.5 rounded-full bg-primary/10 text-primary text-xs font-semibold tracking-widest mb-4">PROFIL DESA</span><h2 class="font-display font-bold text-3xl lg:text-5xl text-primary dark:text-white mb-4">Tentang Desa Namo Bintang</h2><div class="w-20 h-1 bg-gradient-to-r from-primary via-gold to-accent mx-auto rounded-full"></div></div>
    <div class="grid lg:grid-cols-5 gap-8 items-center">
      <div class="lg:col-span-3 space-y-6" data-aos="fade-right">
        <p class="text-base lg:text-lg leading-relaxed text-slate-700 dark:text-slate-300"><span class="text-2xl font-display font-bold text-gold float-left mr-2">D</span>esa Namo Bintang merupakan salah satu desa di Kecamatan Pancur Batu, Kabupaten Deli Serdang, Provinsi Sumatera Utara, Indonesia. Desa ini dikenal sebagai desa yang multikultural dengan keberagaman suku, agama, dan budaya yang hidup berdampingan secara harmonis dalam bingkai Bhinneka Tunggal Ika.</p>
        <p class="text-base lg:text-lg leading-relaxed text-slate-700 dark:text-slate-300">Dengan luas wilayah ±489 Hektar yang terdiri dari 7 dusun, Desa Namo Bintang terus berupaya membangun diri menjadi desa yang mandiri, maju, dan sejahtera melalui partisipasi aktif seluruh komponen masyarakat serta dukungan pemerintahan desa yang profesional dan transparan.</p>
        <div class="grid sm:grid-cols-2 gap-4 pt-4">
          <div class="glass rounded-2xl p-5 border border-white/40 card-hover"><div class="flex items-center gap-3"><div class="w-10 h-10 rounded-xl bg-gradient-to-br from-primary to-primary-light flex items-center justify-center"><i data-lucide="hash" class="w-5 h-5 text-white"></i></div><div><p class="text-xs text-slate-500">Kode Pos</p><p class="font-display font-bold text-lg text-primary dark:text-white">20353</p></div></div></div>
          <div class="glass rounded-2xl p-5 border border-white/40 card-hover"><div class="flex items-center gap-3"><div class="w-10 h-10 rounded-xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center"><i data-lucide="map-pin" class="w-5 h-5 text-white"></i></div><div><p class="text-xs text-slate-500">Alamat</p><p class="text-sm font-medium text-primary dark:text-white leading-tight">FHFW+WRX, Jl. Jamin Ginting, Pancur Batu</p></div></div></div>
        </div>
        <a href="https://www.google.com/maps/search/?api=1&query=FHFW%2BWRX+Jalan+Jamin+Ginting+Pancur+Batu+Deli+Serdang" target="_blank" class="btn-shimmer inline-flex items-center gap-2 px-6 py-3 bg-gradient-to-r from-primary to-primary-light text-white font-semibold rounded-xl shadow-lg hover:shadow-xl transition-shadow"><i data-lucide="navigation" class="w-4 h-4"></i> Lihat Lokasi <i data-lucide="external-link" class="w-3.5 h-3.5"></i></a>
      </div>
      <div class="lg:col-span-2" data-aos="fade-left" data-aos-delay="200">
        <div class="relative"><div class="absolute -inset-4 bg-gradient-to-br from-primary/20 to-gold/20 rounded-3xl blur-2xl"></div><div class="relative glass-strong rounded-3xl p-8 border border-white/40"><div class="flex items-center justify-center mb-6"><div id="profilLogo" class="w-32 h-32"></div></div><div class="text-center space-y-3"><h3 class="font-display font-bold text-xl text-primary dark:text-white">Desa Namo Bintang</h3><div class="flex flex-wrap justify-center gap-2"><span class="px-3 py-1 bg-primary/10 text-primary text-xs rounded-full">7 Dusun</span><span class="px-3 py-1 bg-gold/10 text-gold-deep text-xs rounded-full">Multikultural</span><span class="px-3 py-1 bg-accent/10 text-accent text-xs rounded-full">Mandiri</span></div><p class="text-sm text-slate-500 italic pt-2 border-t border-slate-200">"Menciptakan Desa yang tidak memandang suku agama ras dan antar golongan"</p></div></div></div>
      </div>
    </div>
  </div>
</section>

<!-- SEJARAH -->
<section id="sejarah" class="py-20 lg:py-28 bg-white/60 dark:bg-[#0a0f1f]/60 backdrop-blur-sm">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="text-center mb-16" data-aos="fade-up"><span class="inline-block px-4 py-1.5 rounded-full bg-gold/10 text-gold-deep text-xs font-semibold tracking-widest mb-4">SEJARAH DESA</span><h2 class="font-display font-bold text-3xl lg:text-5xl text-primary dark:text-white mb-4">Perjalanan Desa Namo Bintang</h2><div class="w-20 h-1 bg-gradient-to-r from-gold via-primary to-accent mx-auto rounded-full"></div></div>
    
    <div class="max-w-4xl mx-auto mb-16 p-6 lg:p-8 glass-strong rounded-3xl border border-white/40 shadow-lg" data-aos="fade-up">
      <p class="text-slate-700 dark:text-slate-300 leading-relaxed text-sm lg:text-base mb-4">Desa Namo Bintang adalah salah satu desa dari 59 desa yang ada di Kecamatan Pancur Batu. Pada Tahun 1988 dilaksanakan pencatatan menjadi 25 desa di Kecamatan Pancur Batu, yang mana wilayah Desa Namo Bintang termasuk di dalamnya. Desa ini sebelumnya merupakan bagian dari Desa Rumah Mbacang, Desa Suberingin, Kabupaten Deli Serdang.</p>
      <p class="text-slate-700 dark:text-slate-300 leading-relaxed text-sm lg:text-base">Menurut beberapa tokoh masyarakat, dahulu desa ini banyak ditumbuhi pohon durian. Wilayah tersebut kemudian lambat laun menjadi sebuah desa yang pada saat itu diberi nama Desa Namo Bintang.</p>
    </div>
  </div>
</section>

<!-- VISI MISI -->
<section id="visi-misi" class="py-20 lg:py-28 relative overflow-hidden">
  <div class="absolute inset-0 hero-gradient opacity-95"></div>
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative">
    <div class="text-center mb-16" data-aos="fade-up"><span class="inline-block px-4 py-1.5 rounded-full glass border border-gold/30 text-gold-light text-xs font-semibold tracking-widest mb-4">VISI & MISI</span><h2 class="font-display font-bold text-3xl lg:text-5xl text-white mb-4">Arah Pembangunan Desa</h2><div class="w-20 h-1 bg-gradient-to-r from-gold via-white to-accent mx-auto rounded-full"></div></div>
    <div class="max-w-4xl mx-auto mb-16" data-aos="zoom-in">
      <div class="relative">
        <div class="absolute -inset-1 bg-gradient-to-r from-gold via-white to-accent rounded-3xl blur opacity-40"></div>
        <div class="relative glass-strong rounded-3xl p-8 lg:p-12 border border-gold/30 text-center">
          <div class="w-16 h-16 mx-auto rounded-2xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center shadow-lg mb-6"><i data-lucide="target" class="w-8 h-8 text-white"></i></div>
          <p class="text-xs font-bold tracking-widest text-gold-deep mb-3">VISI DESA NAMO BINTANG</p>
          <h3 class="font-display font-bold text-2xl lg:text-3xl xl:text-4xl text-primary dark:text-white leading-tight mb-6">"Terwujudnya Desa Namo Bintang yang maju, mandiri, tegas, dan sejahtera berbasis potensi lokal serta pelayanan publik yang transparan."</h3>
          <p class="text-slate-600 dark:text-slate-300 text-base lg:text-lg leading-relaxed max-w-3xl mx-auto">Visi ini merupakan komitmen seluruh komponen desa untuk senantiasa bekerja sama dalam membangun desa menuju kemajuan yang berkelanjutan, dengan mengedepankan semangat kebersamaan, partisipasi masyarakat, dan tata kelola pemerintahan yang baik.</p>
        </div>
      </div>
    </div>
    <div class="text-center mb-10" data-aos="fade-up"><h3 class="font-display font-bold text-2xl lg:text-3xl text-white mb-2">Misi Desa</h3><p class="text-white/70">Delapan langkah strategis mewujudkan visi desa</p></div>
    <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
      <div class="glass-strong rounded-2xl p-6 border border-white/40 card-hover group" data-aos="fade-up" data-aos-delay="50"><div class="flex items-start gap-4"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center flex-shrink-0 group-hover:scale-110 shadow-lg transition-transform"><i data-lucide="concierge-bell" class="w-6 h-6 text-white"></i></div><div><div class="flex items-center gap-2 mb-2"><span class="text-2xl font-display font-black gradient-text-gold">01</span><div class="h-px flex-1 bg-gradient-to-r from-gold/40 to-transparent"></div></div><p class="text-sm text-slate-700 dark:text-slate-200 leading-relaxed">Meningkatkan kualitas pelayanan publik yang cepat, adil dan transparan.</p></div></div></div>
      <div class="glass-strong rounded-2xl p-6 border border-white/40 card-hover group" data-aos="fade-up" data-aos-delay="100"><div class="flex items-start gap-4"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center flex-shrink-0 group-hover:scale-110 shadow-lg transition-transform"><i data-lucide="trending-up" class="w-6 h-6 text-white"></i></div><div><div class="flex items-center gap-2 mb-2"><span class="text-2xl font-display font-black gradient-text-gold">02</span><div class="h-px flex-1 bg-gradient-to-r from-gold/40 to-transparent"></div></div><p class="text-sm text-slate-700 dark:text-slate-200 leading-relaxed">Mengembangkan ekonomi desa melalui pertanian, UMKM dan usaha produktif masyarakat.</p></div></div></div>
      <div class="glass-strong rounded-2xl p-6 border border-white/40 card-hover group" data-aos="fade-up" data-aos-delay="150"><div class="flex items-start gap-4"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center flex-shrink-0 group-hover:scale-110 shadow-lg transition-transform"><i data-lucide="heart-pulse" class="w-6 h-6 text-white"></i></div><div><div class="flex items-center gap-2 mb-2"><span class="text-2xl font-display font-black gradient-text-gold">03</span><div class="h-px flex-1 bg-gradient-to-r from-gold/40 to-transparent"></div></div><p class="text-sm text-slate-700 dark:text-slate-200 leading-relaxed">Meningkatkan kualitas pendidikan, kesehatan dan kesejahteraan.</p></div></div></div>
      <div class="glass-strong rounded-2xl p-6 border border-white/40 card-hover group" data-aos="fade-up" data-aos-delay="200"><div class="flex items-start gap-4"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center flex-shrink-0 group-hover:scale-110 shadow-lg transition-transform"><i data-lucide="shield-check" class="w-6 h-6 text-white"></i></div><div><div class="flex items-center gap-2 mb-2"><span class="text-2xl font-display font-black gradient-text-gold">04</span><div class="h-px flex-1 bg-gradient-to-r from-gold/40 to-transparent"></div></div><p class="text-sm text-slate-700 dark:text-slate-200 leading-relaxed">Mewujudkan tata kelola pemerintahan desa yang bersih dan akuntabel.</p></div></div></div>
      <div class="glass-strong rounded-2xl p-6 border border-white/40 card-hover group" data-aos="fade-up" data-aos-delay="250"><div class="flex items-start gap-4"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center flex-shrink-0 group-hover:scale-110 shadow-lg transition-transform"><i data-lucide="land-plot" class="w-6 h-6 text-white"></i></div><div><div class="flex items-center gap-2 mb-2"><span class="text-2xl font-display font-black gradient-text-gold">05</span><div class="h-px flex-1 bg-gradient-to-r from-gold/40 to-transparent"></div></div><p class="text-sm text-slate-700 dark:text-slate-200 leading-relaxed">Meningkatkan PAD desa melalui tanah-tanah desa dan tanah tkd desa dengan cara menertibkan administrasi pengelolaan dari masyarakat dan penertiban pengelolaannya.</p></div></div></div>
      <div class="glass-strong rounded-2xl p-6 border border-white/40 card-hover group" data-aos="fade-up" data-aos-delay="300"><div class="flex items-start gap-4"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center flex-shrink-0 group-hover:scale-110 shadow-lg transition-transform"><i data-lucide="trophy" class="w-6 h-6 text-white"></i></div><div><div class="flex items-center gap-2 mb-2"><span class="text-2xl font-display font-black gradient-text-gold">06</span><div class="h-px flex-1 bg-gradient-to-r from-gold/40 to-transparent"></div></div><p class="text-sm text-slate-700 dark:text-slate-200 leading-relaxed">Mengembangkan bakat pemuda di bidang olahraga dan seni budaya yang sudah ada di Desa Namo Bintang.</p></div></div></div>
      <div class="glass-strong rounded-2xl p-6 border border-white/40 card-hover group" data-aos="fade-up" data-aos-delay="350"><div class="flex items-start gap-4"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center flex-shrink-0 group-hover:scale-110 shadow-lg transition-transform"><i data-lucide="construction" class="w-6 h-6 text-white"></i></div><div><div class="flex items-center gap-2 mb-2"><span class="text-2xl font-display font-black gradient-text-gold">07</span><div class="h-px flex-1 bg-gradient-to-r from-gold/40 to-transparent"></div></div><p class="text-sm text-slate-700 dark:text-slate-200 leading-relaxed">Mendorong pembangunan infrastruktur yang merata dan berkelanjutan.</p></div></div></div>
      <div class="glass-strong rounded-2xl p-6 border border-white/40 card-hover group" data-aos="fade-up" data-aos-delay="400"><div class="flex items-start gap-4"><div class="w-12 h-12 rounded-xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center flex-shrink-0 group-hover:scale-110 shadow-lg transition-transform"><i data-lucide="handshake" class="w-6 h-6 text-white"></i></div><div><div class="flex items-center gap-2 mb-2"><span class="text-2xl font-display font-black gradient-text-gold">08</span><div class="h-px flex-1 bg-gradient-to-r from-gold/40 to-transparent"></div></div><p class="text-sm text-slate-700 dark:text-slate-200 leading-relaxed">Menumbuhkan nilai keagamaan dan budaya gotong royong.</p></div></div></div>
    </div>
  </div>
</section>

<!-- PEMERINTAHAN -->
<section id="pemerintahan" class="py-20 lg:py-28 bg-white/60 dark:bg-[#0a0f1f]/60 backdrop-blur-sm">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="text-center mb-16" data-aos="fade-up"><span class="inline-block px-4 py-1.5 rounded-full bg-primary/10 text-primary text-xs font-semibold tracking-widest mb-4">PEMERINTAHAN DESA</span><h2 class="font-display font-bold text-3xl lg:text-5xl text-primary dark:text-white mb-4">Struktur Organisasi</h2><div class="w-20 h-1 bg-gradient-to-r from-primary via-gold to-accent mx-auto rounded-full"></div></div>
    
    <div class="overflow-x-auto pb-6" data-aos="zoom-in">
      <div class="min-w-[768px] flex flex-col items-center gap-0">
        
        <div class="relative">
          <div class="absolute -inset-2 bg-gradient-to-r from-gold to-primary rounded-3xl blur opacity-30"></div>
          <div class="relative glass-strong rounded-2xl p-6 border-2 border-gold/40 shadow-xl min-w-[280px] text-center card-hover">
            <div class="w-28 h-28 mx-auto rounded-full overflow-hidden border-4 border-gold/40 shadow-lg mb-3">
              <img src="https://z-cdn-media.chatglm.cn/files/14cb606f-5f3f-4407-af48-aa565f51d4cc.jpeg?auth_key=1886632884-f6140ee5eeff4ce6b5e764b522b88375-0-626087442871c00f50fb4d15b5d673d0" alt="JEFRI BRAHMANA" class="w-full h-full object-cover org-img">
            </div>
            <p class="text-xs text-slate-500 font-semibold tracking-widest">KEPALA DESA</p>
            <p class="font-display font-bold text-lg text-primary dark:text-white mt-1">JEFRI BRAHMANA</p>
          </div>
        </div>
        
        <div class="w-1 h-10 org-line rounded-full"></div>
        
        <div class="relative glass-strong rounded-2xl p-5 border border-primary/30 shadow-lg min-w-[260px] text-center card-hover">
          <div class="w-24 h-24 mx-auto rounded-full overflow-hidden border-4 border-primary/30 shadow-md mb-2">
            <img src="https://z-cdn-media.chatglm.cn/files/24f13e9c-d7af-4b09-9c5c-06f745131c68.png?auth_key=1886632884-ea42892230e24129829bed3b47b96f26-0-a8ff0f74d92d25ad9025d8da2d0fa04b" alt="RONALDO" class="w-full h-full object-cover org-img">
          </div>
          <p class="text-xs text-slate-500 font-semibold tracking-widest">SEKRETARIS DESA</p>
          <p class="font-display font-bold text-base text-primary dark:text-white mt-1">RONALDO</p>
        </div>
        
        <div class="w-1 h-10 org-line rounded-full"></div>
        
        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 w-full max-w-5xl mt-2">
          
          <div class="glass-strong rounded-xl p-4 border border-gold/30 text-center card-hover">
            <div class="w-20 h-20 mx-auto rounded-full overflow-hidden border-4 border-gold/30 mb-2 shadow-md">
              <img src="https://z-cdn-media.chatglm.cn/files/94c5a734-8eaa-4ef5-bb8b-b3d55ab745a8.png?auth_key=1886632884-ac983690dedc4d11b42c028a151f1d90-0-a939a1cd9a43a216eeb824651eebbb7a" alt="IMA FITRIANI" class="w-full h-full object-cover org-img">
            </div>
            <p class="text-xs font-semibold text-primary dark:text-white">Kaur Keuangan</p>
            <p class="text-sm font-bold text-primary dark:text-white mt-1">IMA FITRIANI</p>
          </div>
          
          <div class="glass-strong rounded-xl p-4 border border-primary/20 text-center card-hover">
            <div class="w-20 h-20 mx-auto rounded-full overflow-hidden border-4 border-primary/30 mb-2 shadow-md">
              <img src="https://z-cdn-media.chatglm.cn/files/202791a3-d1df-494d-8088-e29bafa66859.png?auth_key=1886635119-d7fa20ee52714225a79f69749147b2ff-0-490f71622d86ccc9806f9ab6644dc86c" alt="MANDELA PURBA" class="w-full h-full object-cover mandela-img">
            </div>
            <p class="text-xs font-semibold text-primary dark:text-white">Kaur Umum & Perencanaan</p>
            <p class="text-sm font-bold text-primary dark:text-white mt-1">MANDELA PURBA</p>
          </div>
          
          <div class="glass-strong rounded-xl p-4 border border-primary/20 text-center card-hover">
            <div class="w-20 h-20 mx-auto rounded-full overflow-hidden border-4 border-primary/30 mb-2 shadow-md">
              <img src="https://z-cdn-media.chatglm.cn/files/a017b77f-43e3-4c88-b1d9-0644ab027035.png?auth_key=1886632884-4a1b8aeabb67446e8aa9ef4776aef06c-0-be1c61ab44c361d6620f08ba8729662b" alt="RIZKY HERDIANTA SINULINGGA" class="w-full h-full object-cover org-img">
            </div>
            <p class="text-xs font-semibold text-primary dark:text-white">Kasi Pemerintahan</p>
            <p class="text-sm font-bold text-primary dark:text-white mt-1">RIZKY HERDIANTA S.</p>
          </div>
          
          <div class="glass-strong rounded-xl p-4 border border-slate-300 text-center card-hover border-dashed">
            <div class="w-20 h-20 mx-auto rounded-full overflow-hidden border-2 border-slate-300 mb-2 bg-slate-100 dark:bg-slate-700 flex items-center justify-center">
              <i data-lucide="user" class="w-10 h-10 text-slate-400"></i>
            </div>
            <p class="text-xs font-semibold text-slate-500 dark:text-slate-400">Kasi Pelayanan & Kesejahteraan</p>
            <p class="text-sm font-bold text-slate-500 dark:text-slate-400 mt-1">EDO IRPAMA</p>
          </div>
          
        </div>
      </div>
    </div>

    <div class="mt-20" data-aos="fade-up">
      <div class="text-center mb-10"><h3 class="font-display font-bold text-2xl lg:text-3xl text-primary dark:text-white mb-2">Kepala Dusun</h3><p class="text-slate-600 dark:text-slate-400">Tujuh kepala dusun yang melayani wilayah Desa Namo Bintang</p></div>
      
      <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-7 gap-4">
        <div class="glass-strong rounded-2xl p-4 border border-white/40 card-hover text-center group" data-aos="fade-up" data-aos-delay="50">
          <div class="relative mx-auto w-24 h-24 mb-3">
            <div class="absolute inset-0 bg-gradient-to-br from-primary to-gold rounded-full blur-md opacity-30 group-hover:opacity-60 transition-opacity"></div>
            <div class="relative w-full h-full rounded-full overflow-hidden border-4 border-white dark:border-white/10 shadow-lg">
              <img src="https://z-cdn-media.chatglm.cn/files/3152a249-2d23-443f-af3c-7226da48f9fc.png?auth_key=1886525381-0dc6640b669f4186a11e72504901c370-0-6c99d13131fa81d9a7a83da3a3ffb1be" alt="MARIHOT TOGI MARITO SITEPU" class="w-full h-full object-cover kadus-img">
            </div>
          </div>
          <p class="font-display font-bold text-xs sm:text-sm text-primary dark:text-white leading-tight min-h-[2.5rem] flex items-center justify-center">MARIHOT TOGI MARITO SITEPU</p>
          <p class="text-xs text-slate-500 mt-1">Kepala Dusun I</p>
        </div>
        
        <div class="glass-strong rounded-2xl p-4 border border-white/40 card-hover text-center group" data-aos="fade-up" data-aos-delay="100">
          <div class="relative mx-auto w-24 h-24 mb-3">
            <div class="absolute inset-0 bg-gradient-to-br from-primary to-gold rounded-full blur-md opacity-30 group-hover:opacity-60 transition-opacity"></div>
            <div class="relative w-full h-full rounded-full overflow-hidden border-4 border-white dark:border-white/10 shadow-lg">
              <img src="https://z-cdn-media.chatglm.cn/files/0ba65579-7d36-4892-8562-614eb46c34ae.png?auth_key=1886525381-88d6328b7823429a8b8cdc00cbc34834-0-9d9a0f65d81394f8c7caf48c17096a07" alt="HARPITRA WAHYUNI" class="w-full h-full object-cover kadus-img">
            </div>
          </div>
          <p class="font-display font-bold text-xs sm:text-sm text-primary dark:text-white leading-tight min-h-[2.5rem] flex items-center justify-center">HARPITRA WAHYUNI</p>
          <p class="text-xs text-slate-500 mt-1">Kepala Dusun II</p>
        </div>
        
        <div class="glass-strong rounded-2xl p-4 border border-white/40 card-hover text-center group" data-aos="fade-up" data-aos-delay="150">
          <div class="relative mx-auto w-24 h-24 mb-3">
            <div class="absolute inset-0 bg-gradient-to-br from-primary to-gold rounded-full blur-md opacity-30 group-hover:opacity-60 transition-opacity"></div>
            <div class="relative w-full h-full rounded-full overflow-hidden border-4 border-white dark:border-white/10 shadow-lg">
              <img src="https://z-cdn-media.chatglm.cn/files/03f1380c-ddab-4cd9-bbe6-f57d0fc9f497.png?auth_key=1886525381-7169cf7ac7f14b59a988daa19897b25d-0-aa00d13817a59297eac6c6c0bc5ae216" alt="HARIS COLIA" class="w-full h-full object-cover kadus-img">
            </div>
          </div>
          <p class="font-display font-bold text-xs sm:text-sm text-primary dark:text-white leading-tight min-h-[2.5rem] flex items-center justify-center">HARIS COLIA</p>
          <p class="text-xs text-slate-500 mt-1">Kepala Dusun III</p>
        </div>
        
        <div class="glass-strong rounded-2xl p-4 border border-white/40 card-hover text-center group" data-aos="fade-up" data-aos-delay="200">
          <div class="relative mx-auto w-24 h-24 mb-3">
            <div class="absolute inset-0 bg-gradient-to-br from-primary to-gold rounded-full blur-md opacity-30 group-hover:opacity-60 transition-opacity"></div>
            <div class="relative w-full h-full rounded-full overflow-hidden border-4 border-white dark:border-white/10 shadow-lg">
              <img src="https://z-cdn-media.chatglm.cn/files/833d1700-be40-405b-a4b0-e6836cfcb149.png?auth_key=1886609765-4dd6fc9f92204def86266678cd93d110-0-39bd6da0e0df930387d3fdb15890ffd5" alt="AMIRUDDIN PINEM" class="w-full h-full object-cover kadus-img">
            </div>
          </div>
          <p class="font-display font-bold text-xs sm:text-sm text-primary dark:text-white leading-tight min-h-[2.5rem] flex items-center justify-center">AMIRUDDIN PINEM</p>
          <p class="text-xs text-slate-500 mt-1">Kepala Dusun IV</p>
        </div>
        
        <div class="glass-strong rounded-2xl p-4 border border-white/40 card-hover text-center group" data-aos="fade-up" data-aos-delay="250">
          <div class="relative mx-auto w-24 h-24 mb-3">
            <div class="absolute inset-0 bg-gradient-to-br from-primary to-gold rounded-full blur-md opacity-30 group-hover:opacity-60 transition-opacity"></div>
            <div class="relative w-full h-full rounded-full overflow-hidden border-4 border-white dark:border-white/10 shadow-lg">
              <img src="https://z-cdn-media.chatglm.cn/files/c639cf13-5e33-4a91-9021-3eef5bf4f52a.png?auth_key=1886525381-5204543fa2af4d9f83c776f08693d082-0-efb00b271ab0874d7b6e5d960ffcbf4b" alt="SAHLAN GINTING" class="w-full h-full object-cover kadus-img">
            </div>
          </div>
          <p class="font-display font-bold text-xs sm:text-sm text-primary dark:text-white leading-tight min-h-[2.5rem] flex items-center justify-center">SAHLAN GINTING</p>
          <p class="text-xs text-slate-500 mt-1">Kepala Dusun V</p>
        </div>
        
        <div class="glass-strong rounded-2xl p-4 border border-white/40 card-hover text-center group" data-aos="fade-up" data-aos-delay="300">
          <div class="relative mx-auto w-24 h-24 mb-3">
            <div class="absolute inset-0 bg-gradient-to-br from-primary to-gold rounded-full blur-md opacity-30 group-hover:opacity-60 transition-opacity"></div>
            <div class="relative w-full h-full rounded-full overflow-hidden border-4 border-white dark:border-white/10 shadow-lg">
              <img src="https://z-cdn-media.chatglm.cn/files/b1d56101-90bc-43b4-b109-bde79317517f.png?auth_key=1886525381-bb4122a7eb644d0a90b4dc0081b3da6c-0-4da0c832f1903bcdedf912b86bd5d669" alt="NASIPTA PINEM" class="w-full h-full object-cover kadus-img">
            </div>
          </div>
          <p class="font-display font-bold text-xs sm:text-sm text-primary dark:text-white leading-tight min-h-[2.5rem] flex items-center justify-center">NASIPTA PINEM</p>
          <p class="text-xs text-slate-500 mt-1">Kepala Dusun VI</p>
        </div>
        
        <div class="glass-strong rounded-2xl p-4 border border-white/40 card-hover text-center group" data-aos="fade-up" data-aos-delay="350">
          <div class="relative mx-auto w-24 h-24 mb-3">
            <div class="absolute inset-0 bg-gradient-to-br from-primary to-gold rounded-full blur-md opacity-30 group-hover:opacity-60 transition-opacity"></div>
            <div class="relative w-full h-full rounded-full overflow-hidden border-4 border-white dark:border-white/10 shadow-lg">
              <img src="https://z-cdn-media.chatglm.cn/files/519ca026-90c5-4d40-acda-4ee5cc9535f9.png?auth_key=1886609765-c6ff75b4f348480d98b70ef5d1d42e40-0-de0660e7a5c233bd058c1bd4f06417c3" alt="ANDRI GINTING" class="w-full h-full object-cover kadus-img">
            </div>
          </div>
          <p class="font-display font-bold text-xs sm:text-sm text-primary dark:text-white leading-tight min-h-[2.5rem] flex items-center justify-center">ANDRI GINTING</p>
          <p class="text-xs text-slate-500 mt-1">Kepala Dusun VII</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PETA & LUAS WILAYAH -->
<section id="peta" class="py-20 lg:py-28 bg-white/60 dark:bg-[#0d1426]/60 backdrop-blur-sm">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="text-center mb-16" data-aos="fade-up">
      <span class="inline-block px-4 py-1.5 rounded-full bg-accent/10 text-accent text-xs font-semibold tracking-widest mb-4">GEOGRAFI & WILAYAH</span>
      <h2 class="font-display font-bold text-3xl lg:text-5xl text-primary dark:text-white mb-4">Letak Geografi Desa</h2>
      <div class="w-20 h-1 bg-gradient-to-r from-accent via-primary to-gold mx-auto rounded-full"></div>
    </div>
    
    <div class="grid lg:grid-cols-2 gap-8 items-stretch mb-12">
      <!-- Google Maps iframe menggantikan placeholder -->
      <div data-aos="fade-right" class="relative rounded-3xl overflow-hidden shadow-2xl min-h-[450px] group">
        <iframe class="map-frame w-full h-full absolute inset-0" src="https://www.google.com/maps?q=Desa%20Namo%20Bintang%2C%20Pancur%20Batu%2C%20Deli%20Serdang&output=embed" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        <div class="absolute top-4 left-4 glass-strong rounded-2xl px-4 py-3 shadow-lg flex items-center gap-2 pointer-events-none">
          <i data-lucide="map-pin" class="w-5 h-5 text-gold"></i>
          <span class="font-display font-bold text-primary text-sm">Desa Namo Bintang</span>
        </div>
      </div>

      <div data-aos="fade-left" data-aos-delay="200" class="glass-strong rounded-3xl p-8 border border-white/40">
        <h3 class="font-display font-bold text-xl text-primary dark:text-white mb-6 flex items-center gap-2"><i data-lucide="compass" class="w-6 h-6 text-gold"></i> Batas Wilayah</h3>
        <div class="grid sm:grid-cols-2 gap-4">
          <div class="relative p-5 rounded-2xl bg-gradient-to-br from-primary/10 to-primary-light/5 border border-primary/20 card-hover">
            <div class="absolute top-3 right-3 w-8 h-8 rounded-full bg-primary/10 flex items-center justify-center"><i data-lucide="arrow-up" class="w-4 h-4 text-primary"></i></div>
            <p class="text-xs text-slate-500 font-semibold tracking-widest mb-1">UTARA</p>
            <p class="font-display font-semibold text-primary dark:text-white">Desa Kota Madya Medan</p>
          </div>
          <div class="relative p-5 rounded-2xl bg-gradient-to-br from-accent/10 to-accent/5 border border-accent/20 card-hover">
            <div class="absolute top-3 right-3 w-8 h-8 rounded-full bg-accent/10 flex items-center justify-center"><i data-lucide="arrow-down" class="w-4 h-4 text-accent"></i></div>
            <p class="text-xs text-slate-500 font-semibold tracking-widest mb-1">SELATAN</p>
            <p class="font-display font-semibold text-primary dark:text-white">Desa Pertampilan</p>
          </div>
          <div class="relative p-5 rounded-2xl bg-gradient-to-br from-gold/10 to-gold/5 border border-gold/20 card-hover">
            <div class="absolute top-3 right-3 w-8 h-8 rounded-full bg-gold/10 flex items-center justify-center"><i data-lucide="arrow-left" class="w-4 h-4 text-gold-deep"></i></div>
            <p class="text-xs text-slate-500 font-semibold tracking-widest mb-1">BARAT</p>
            <p class="font-display font-semibold text-primary dark:text-white">Desa Baru</p>
          </div>
          <div class="relative p-5 rounded-2xl bg-gradient-to-br from-primary-light/10 to-primary-soft/5 border border-primary-light/20 card-hover">
            <div class="absolute top-3 right-3 w-8 h-8 rounded-full bg-primary-light/10 flex items-center justify-center"><i data-lucide="arrow-right" class="w-4 h-4 text-primary-light"></i></div>
            <p class="text-xs text-slate-500 font-semibold tracking-widest mb-1">TIMUR</p>
            <p class="font-display font-semibold text-primary dark:text-white">Desa Durin Tonggal</p>
          </div>
        </div>
      </div>
    </div>

    <div class="grid md:grid-cols-2 gap-6" data-aos="fade-up">
      <div class="glass-strong rounded-3xl p-6 border border-white/40 flex items-center gap-6 card-hover">
        <div class="w-16 h-16 rounded-2xl bg-gradient-to-br from-primary to-primary-light flex items-center justify-center flex-shrink-0 shadow-lg">
          <i data-lucide="map-pinned" class="w-8 h-8 text-white"></i>
        </div>
        <div>
          <p class="text-xs text-slate-500 font-semibold tracking-widest mb-1">ORBITASI KE KECAMATAN</p>
          <p class="font-display font-bold text-2xl text-primary dark:text-white">4 KM <span class="text-base text-slate-500 font-normal">(10 Menit)</span></p>
          <p class="text-sm text-slate-500 mt-1">Jarak ke Ibu Kota Kecamatan Pancur Batu</p>
        </div>
      </div>
      <div class="glass-strong rounded-3xl p-6 border border-white/40 flex items-center gap-6 card-hover">
        <div class="w-16 h-16 rounded-2xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center flex-shrink-0 shadow-lg">
          <i data-lucide="navigation" class="w-8 h-8 text-white"></i>
        </div>
        <div>
          <p class="text-xs text-slate-500 font-semibold tracking-widest mb-1">ORBITASI KE KABUPATEN</p>
          <p class="font-display font-bold text-2xl text-primary dark:text-white">41 KM <span class="text-base text-slate-500 font-normal">(1 Jam)</span></p>
          <p class="text-sm text-slate-500 mt-1">Jarak ke Ibu Kota Kabupaten Deli Serdang</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- STATISTIK -->
<section id="statistik" class="py-20 lg:py-28 relative">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="text-center mb-16" data-aos="fade-up">
      <span class="inline-block px-4 py-1.5 rounded-full bg-primary/10 text-primary text-xs font-semibold tracking-widest mb-4">STATISTIK DESA</span>
      <h2 class="font-display font-bold text-3xl lg:text-5xl text-primary dark:text-white mb-4">Data Demografi & Sosial</h2>
      <div class="w-20 h-1 bg-gradient-to-r from-primary via-gold to-accent mx-auto rounded-full"></div>
    </div>

    <div class="grid lg:grid-cols-3 gap-6 mb-6">
      <div class="glass-strong rounded-3xl p-6 border border-white/40 card-hover" data-aos="fade-up">
        <h3 class="font-display font-bold text-lg text-primary dark:text-white mb-4 flex items-center gap-2"><i data-lucide="users" class="w-5 h-5 text-gold"></i> Jumlah Penduduk</h3>
        <div class="relative h-56">
          <canvas id="genderChart"></canvas>
        </div>
        <div class="mt-4 pt-4 border-t border-slate-200 dark:border-slate-700 flex justify-around text-center">
          <div>
            <p class="text-xs text-slate-500">Total Penduduk</p>
            <p class="font-display font-bold text-xl text-primary dark:text-white">6.545</p>
          </div>
          <div>
            <p class="text-xs text-slate-500">Total KK</p>
            <p class="font-display font-bold text-xl text-primary dark:text-white">1.803</p>
          </div>
        </div>
      </div>

      <div class="glass-strong rounded-3xl p-6 border border-white/40 card-hover" data-aos="fade-up" data-aos-delay="100">
        <h3 class="font-display font-bold text-lg text-primary dark:text-white mb-4 flex items-center gap-2"><i data-lucide="church" class="w-5 h-5 text-gold"></i> Agama</h3>
        <div class="relative h-56">
          <canvas id="religionChart"></canvas>
        </div>
      </div>

      <div class="glass-strong rounded-3xl p-6 border border-white/40 card-hover" data-aos="fade-up" data-aos-delay="200">
        <h3 class="font-display font-bold text-lg text-primary dark:text-white mb-4 flex items-center gap-2"><i data-lucide="graduation-cap" class="w-5 h-5 text-gold"></i> Pendidikan</h3>
        <div class="relative h-56">
          <canvas id="educationChart"></canvas>
        </div>
      </div>
    </div>

    <div class="grid lg:grid-cols-2 gap-6 mb-6">
      <div class="glass-strong rounded-3xl p-6 border border-white/40 card-hover" data-aos="fade-right">
        <h3 class="font-display font-bold text-lg text-primary dark:text-white mb-4 flex items-center gap-2"><i data-lucide="briefcase" class="w-5 h-5 text-gold"></i> Mata Pencaharian</h3>
        <div class="relative h-72">
          <canvas id="professionChart"></canvas>
        </div>
      </div>

      <div class="glass-strong rounded-3xl p-6 border border-white/40 card-hover" data-aos="fade-left">
        <h3 class="font-display font-bold text-lg text-primary dark:text-white mb-4 flex items-center gap-2"><i data-lucide="wheat" class="w-5 h-5 text-gold"></i> Pertanian (Hektar)</h3>
        <div class="relative h-72">
          <canvas id="agricultureChart"></canvas>
        </div>
      </div>
    </div>

    <div class="glass-strong rounded-3xl p-6 lg:p-8 border border-white/40 card-hover mb-6" data-aos="fade-up">
      <h3 class="font-display font-bold text-xl text-primary dark:text-white mb-6 flex items-center gap-2"><i data-lucide="land-plot" class="w-6 h-6 text-gold"></i> Luas Wilayah Desa (Ha)</h3>
      <div class="grid md:grid-cols-2 gap-x-8 gap-y-4">
        <div class="space-y-3">
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Ladang/Tegalan</span><span class="font-bold text-primary dark:text-gold">292 Ha</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-primary to-primary-light" style="width: 100%"></div></div>
          </div>
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Pemukiman</span><span class="font-bold text-primary dark:text-gold">65 Ha</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-accent to-accent-light" style="width: 22%"></div></div>
          </div>
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Prasarana Umum Lainnya</span><span class="font-bold text-primary dark:text-gold">50 Ha</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-gold to-gold-light" style="width: 17%"></div></div>
          </div>
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Pertanian Sawah</span><span class="font-bold text-primary dark:text-gold">29,3 Ha</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-primary to-primary-light" style="width: 10%"></div></div>
          </div>
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Lahan Eks Pembuangan Sampah</span><span class="font-bold text-primary dark:text-gold">27,2 Ha</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-slate-400 to-slate-500" style="width: 9%"></div></div>
          </div>
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Lahan Pekarangan</span><span class="font-bold text-primary dark:text-gold">18,2 Ha</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-accent to-accent-light" style="width: 6%"></div></div>
          </div>
        </div>
        <div class="space-y-3">
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Sekolah</span><span class="font-bold text-primary dark:text-gold">5 Ha</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-gold to-gold-light" style="width: 2%"></div></div>
          </div>
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Jalan</span><span class="font-bold text-primary dark:text-gold">5 Km</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-slate-400 to-slate-500" style="width: 2%"></div></div>
          </div>
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Rawa-rawa</span><span class="font-bold text-primary dark:text-gold">1 Ha</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-primary-soft to-primary-light" style="width: 0.5%"></div></div>
          </div>
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Lapangan Sepak Bola</span><span class="font-bold text-primary dark:text-gold">1 Ha</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-accent to-accent-light" style="width: 0.5%"></div></div>
          </div>
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Tempat Pemakaman</span><span class="font-bold text-primary dark:text-gold">1 Ha</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-slate-400 to-slate-500" style="width: 0.5%"></div></div>
          </div>
          <div>
            <div class="flex justify-between text-sm mb-1"><span class="font-medium text-slate-700 dark:text-slate-200">Perkantoran</span><span class="font-bold text-primary dark:text-gold">0,5 Ha</span></div>
            <div class="progress-bar-track"><div class="progress-bar-fill bg-gradient-to-r from-gold to-gold-light" style="width: 0.2%"></div></div>
          </div>
        </div>
      </div>
    </div>

    <div class="glass-strong rounded-3xl p-6 lg:p-8 border border-white/40 card-hover" data-aos="fade-up">
      <h3 class="font-display font-bold text-xl text-primary dark:text-white mb-6 flex items-center gap-2"><i data-lucide="palette" class="w-6 h-6 text-gold"></i> Struktur Budaya</h3>
      <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
        <div class="p-4 rounded-2xl bg-gradient-to-br from-primary/10 to-transparent border border-primary/20 text-center card-hover">
          <div class="w-12 h-12 mx-auto rounded-xl bg-primary/10 flex items-center justify-center mb-2"><i data-lucide="users" class="w-6 h-6 text-primary"></i></div>
          <p class="font-display font-bold text-slate-700 dark:text-white">Batak Karo</p>
        </div>
        <div class="p-4 rounded-2xl bg-gradient-to-br from-gold/10 to-transparent border border-gold/20 text-center card-hover">
          <div class="w-12 h-12 mx-auto rounded-xl bg-gold/10 flex items-center justify-center mb-2"><i data-lucide="users" class="w-6 h-6 text-gold-deep"></i></div>
          <p class="font-display font-bold text-slate-700 dark:text-white">Batak Toba</p>
        </div>
        <div class="p-4 rounded-2xl bg-gradient-to-br from-accent/10 to-transparent border border-accent/20 text-center card-hover">
          <div class="w-12 h-12 mx-auto rounded-xl bg-accent/10 flex items-center justify-center mb-2"><i data-lucide="users" class="w-6 h-6 text-accent"></i></div>
          <p class="font-display font-bold text-slate-700 dark:text-white">Jawa</p>
        </div>
        <div class="p-4 rounded-2xl bg-gradient-to-br from-primary-light/10 to-transparent border border-primary-light/20 text-center card-hover">
          <div class="w-12 h-12 mx-auto rounded-xl bg-primary-light/10 flex items-center justify-center mb-2"><i data-lucide="users" class="w-6 h-6 text-primary-light"></i></div>
          <p class="font-display font-bold text-slate-700 dark:text-white">Nias</p>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- POTENSI DESA -->
<section id="potensi" class="py-20 lg:py-28 bg-white/60 dark:bg-[#0a0f1f]/60 backdrop-blur-sm">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="text-center mb-16" data-aos="fade-up">
      <span class="inline-block px-4 py-1.5 rounded-full bg-accent/10 text-accent text-xs font-semibold tracking-widest mb-4">POTENSI DESA</span>
      <h2 class="font-display font-bold text-3xl lg:text-5xl text-primary dark:text-white mb-4">Sumber Daya & Potensi</h2>
      <div class="w-20 h-1 bg-gradient-to-r from-accent via-primary to-gold mx-auto rounded-full"></div>
    </div>
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
      <div class="glass-strong rounded-2xl p-6 border border-white/40 card-hover" data-aos="fade-up">
        <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-accent to-accent-light flex items-center justify-center mb-4 shadow-lg"><i data-lucide="sprout" class="w-7 h-7 text-white"></i></div>
        <h3 class="font-display font-bold text-lg text-primary dark:text-white mb-2">Pertanian</h3>
        <p class="text-sm text-slate-600 dark:text-slate-300 leading-relaxed">Lahan pertanian subur yang menghasilkan padi, palawija, dan tanaman hortikultura lainnya.</p>
      </div>
      <div class="glass-strong rounded-2xl p-6 border border-white/40 card-hover" data-aos="fade-up" data-aos-delay="100">
        <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-gold to-gold-light flex items-center justify-center mb-4 shadow-lg"><i data-lucide="store" class="w-7 h-7 text-white"></i></div>
        <h3 class="font-display font-bold text-lg text-primary dark:text-white mb-2">UMKM</h3>
        <p class="text-sm text-slate-600 dark:text-slate-300 leading-relaxed">Beragam usaha mikro dan kecil masyarakat yang terus berkembang menopang ekonomi desa.</p>
      </div>
      <div class="glass-strong rounded-2xl p-6 border border-white/40 card-hover" data-aos="fade-up" data-aos-delay="200">
        <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-primary to-primary-light flex items-center justify-center mb-4 shadow-lg"><i data-lucide="trees" class="w-7 h-7 text-white"></i></div>
        <h3 class="font-display font-bold text-lg text-primary dark:text-white mb-2">Perkebunan</h3>
        <p class="text-sm text-slate-600 dark:text-slate-300 leading-relaxed">Potensi perkebunan karet dan kelapa sawit yang menjadi mata pencaharian utama sebagian warga.</p>
      </div>
    </div>
  </div>
</section>

<!-- GALERI -->
<section id="galeri" class="py-20 lg:py-28 relative">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="text-center mb-16" data-aos="fade-up">
      <span class="inline-block px-4 py-1.5 rounded-full bg-gold/10 text-gold-deep text-xs font-semibold tracking-widest mb-4">GALERI DESA</span>
      <h2 class="font-display font-bold text-3xl lg:text-5xl text-primary dark:text-white mb-4">Momen & Kegiatan</h2>
      <div class="w-20 h-1 bg-gradient-to-r from-gold via-primary to-accent mx-auto rounded-full"></div>
    </div>
    <div class="columns-1 sm:columns-2 lg:columns-3 gap-4">
      
      <div class="masonry-item gallery-item glass-strong rounded-2xl overflow-hidden border border-white/40 card-hover" data-aos="zoom-in-up">
        <img src="https://z-cdn-media.chatglm.cn/files/ec848614-f932-4f34-ab87-43413747253e.jpeg?auth_key=1886641304-9bdf9fb991884c1192ef079650a3a3f5-0-bc85fefc72c7b0195bc66dd30c9288f1" alt="Kantor Kepala Desa Namo Bintang" class="w-full h-auto object-cover">
        <div class="gallery-caption">
          <div class="flex items-center gap-2 text-white font-display font-semibold text-sm tracking-wide">
            <i data-lucide="building-2" class="w-4 h-4 text-gold-light"></i> Gambar Kantor Kepala Desa
          </div>
        </div>
      </div>
      
      <div class="masonry-item gallery-item glass-strong rounded-2xl overflow-hidden border border-white/40 card-hover" data-aos="zoom-in-up" data-aos-delay="50">
        <img src="https://z-cdn-media.chatglm.cn/files/08bfce8b-f782-4c27-af52-a17694342a3d.jpeg?auth_key=1886641304-7f1b2ed7c60e471eb7813042bf451622-0-66dc49ddd46fcfeab0cbe3eadc923c7e" alt="Pelantikan Kepala Desa Yang Baru" class="w-full h-auto object-cover">
        <div class="gallery-caption">
          <div class="flex items-center gap-2 text-white font-display font-semibold text-sm tracking-wide">
            <i data-lucide="award" class="w-4 h-4 text-gold-light"></i> Pelantikan Kepala Desa Yang Baru
          </div>
        </div>
      </div>
      
      <div class="masonry-item gallery-item glass-strong rounded-2xl overflow-hidden border border-white/40 card-hover" data-aos="zoom-in-up" data-aos-delay="100">
        <img src="https://z-cdn-media.chatglm.cn/files/1db9b910-1d2b-4d81-9ebc-5bfcc349562a.jpeg?auth_key=1886641304-ea0f721fed9d49249a774e1a0d375ad9-0-1cee245859f4e416b8d6a3d471a97354" alt="Pengecoran Jalan di Dusun 5" class="w-full h-auto object-cover">
        <div class="gallery-caption">
          <div class="flex items-center gap-2 text-white font-display font-semibold text-sm tracking-wide">
            <i data-lucide="construction" class="w-4 h-4 text-gold-light"></i> Pengecoran Jalan di Dusun 5
          </div>
        </div>
      </div>
      
      <div class="masonry-item gallery-item glass-strong rounded-2xl overflow-hidden border border-white/40 card-hover" data-aos="zoom-in-up" data-aos-delay="150">
        <img src="https://z-cdn-media.chatglm.cn/files/eb117461-c3df-4bed-8bd8-2ce2fd586fa8.jpeg?auth_key=1886641304-2e2dcfb9110645839a6a8b5e21f340fe-0-dda8212bf095900dd4b4647c1d5ae287" alt="Pengecoran di Dusun 5 Dua" class="w-full h-auto object-cover">
        <div class="gallery-caption">
          <div class="flex items-center gap-2 text-white font-display font-semibold text-sm tracking-wide">
            <i data-lucide="construction" class="w-4 h-4 text-gold-light"></i> Pengecoran di Dusun 5 Dua
          </div>
        </div>
      </div>
      
      <div class="masonry-item gallery-item glass-strong rounded-2xl overflow-hidden border border-white/40 card-hover" data-aos="zoom-in-up" data-aos-delay="200">
        <img src="https://z-cdn-media.chatglm.cn/files/e401e20c-0601-426e-8766-fe118b76c38b.jpeg?auth_key=1886641304-65bd1f99c5744ee2ad38e3eb8a0a5fa8-0-45302abc0372f85d69179c333853bad1" alt="Pengecoran Jalan di Dusun 7" class="w-full h-auto object-cover">
        <div class="gallery-caption">
          <div class="flex items-center gap-2 text-white font-display font-semibold text-sm tracking-wide">
            <i data-lucide="construction" class="w-4 h-4 text-gold-light"></i> Pengecoran Jalan di Dusun 7
          </div>
        </div>
      </div>

      <div class="masonry-item gallery-item glass-strong rounded-2xl overflow-hidden border border-white/40 card-hover" data-aos="zoom-in-up" data-aos-delay="250">
        <img src="https://z-cdn-media.chatglm.cn/files/2f80cabd-e892-47d6-97ef-f45dbefd95dc.png?auth_key=1886642941-464d39180cc9465c8ecafa4e141970f6-0-27dd6e82da4c4b0ecc99488d44ac7ccf" alt="Posyandu Rutin Untuk Lansia" class="w-full h-auto object-cover">
        <div class="gallery-caption">
          <div class="flex items-center gap-2 text-white font-display font-semibold text-sm tracking-wide">
            <i data-lucide="heart-pulse" class="w-4 h-4 text-gold-light"></i> Posyandu Rutin Untuk Lansia
          </div>
        </div>
      </div>

      <div class="masonry-item gallery-item glass-strong rounded-2xl overflow-hidden border border-white/40 card-hover" data-aos="zoom-in-up" data-aos-delay="300">
        <img src="https://z-cdn-media.chatglm.cn/files/bd75b5c9-c03c-402a-9d45-162c7a16cb9d.png?auth_key=1886642941-f2905773a1554365a2003949184dd342-0-25b9e00ba45b75995a19f672b735fa64" alt="Posyandu Rutin Untuk Balita" class="w-full h-auto object-cover">
        <div class="gallery-caption">
          <div class="flex items-center gap-2 text-white font-display font-semibold text-sm tracking-wide">
            <i data-lucide="baby" class="w-4 h-4 text-gold-light"></i> Posyandu Rutin Untuk Balita
          </div>
        </div>
      </div>
      
    </div>
  </div>
</section>

<!-- INFORMASI DESA -->
<section id="berita" class="py-20 lg:py-28 bg-white/60 dark:bg-[#0a0f1f]/60 backdrop-blur-sm">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="text-center mb-16" data-aos="fade-up">
      <span class="inline-block px-4 py-1.5 rounded-full bg-primary/10 text-primary text-xs font-semibold tracking-widest mb-4">INFORMASI DESA</span>
      <h2 class="font-display font-bold text-3xl lg:text-5xl text-primary dark:text-white mb-4">Pengumuman & Kabar Desa</h2>
      <div class="w-20 h-1 bg-gradient-to-r from-primary via-gold to-accent mx-auto rounded-full"></div>
    </div>
    
    <div class="text-center text-slate-500 dark:text-slate-400 py-12" data-aos="fade-up">
      <i data-lucide="inbox" class="w-16 h-16 mx-auto mb-4 opacity-50"></i>
      <p class="font-medium">Belum ada informasi terkini.</p>
    </div>
  </div>
</section>

<!-- KONTAK -->
<section id="kontak" class="py-20 lg:py-28 relative overflow-hidden">
  <div class="absolute inset-0 hero-gradient opacity-95"></div>
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative">
    <div class="text-center mb-16" data-aos="fade-up">
      <span class="inline-block px-4 py-1.5 rounded-full glass border border-gold/30 text-gold-light text-xs font-semibold tracking-widest mb-4">KONTAK</span>
      <h2 class="font-display font-bold text-3xl lg:text-5xl text-white mb-4">Hubungi Kami</h2>
      <div class="w-20 h-1 bg-gradient-to-r from-gold via-white to-accent mx-auto rounded-full"></div>
    </div>
    <div class="grid lg:grid-cols-2 gap-8">
      <div class="glass-strong rounded-3xl p-8 border border-white/40" data-aos="fade-right">
        <h3 class="font-display font-bold text-xl text-primary dark:text-white mb-6 flex items-center gap-2"><i data-lucide="map-pin" class="w-6 h-6 text-gold"></i> Alamat Kantor Desa</h3>
        <p class="text-slate-600 dark:text-slate-300 mb-6 leading-relaxed">FHFW+WRX, Jl. Jamin Ginting, Pancur Batu, Kec. Pancur Batu, Kabupaten Deli Serdang, Sumatera Utara 20353</p>
        <div class="space-y-4">
          <div class="flex items-center gap-3">
            <div class="w-10 h-10 rounded-xl bg-primary/10 flex items-center justify-center"><i data-lucide="phone" class="w-5 h-5 text-primary"></i></div>
            <span class="text-slate-700 dark:text-slate-200 font-medium">+62 813-7746-0001</span>
          </div>
          <div class="flex items-center gap-3">
            <div class="w-10 h-10 rounded-xl bg-gold/10 flex items-center justify-center"><i data-lucide="mail" class="w-5 h-5 text-gold-deep"></i></div>
            <span class="text-slate-700 dark:text-slate-200 font-medium">desanamobintang01@gmail.com</span>
          </div>
          <div class="flex items-center gap-3">
            <div class="w-10 h-10 rounded-xl bg-accent/10 flex items-center justify-center"><i data-lucide="clock" class="w-5 h-5 text-accent"></i></div>
            <span class="text-slate-700 dark:text-slate-200 font-medium">Senin - Jumat: 08.00 - 16.00 WIB</span>
          </div>
        </div>
      </div>
      <div class="glass-strong rounded-3xl p-8 border border-white/40" data-aos="fade-left">
        <h3 class="font-display font-bold text-xl text-primary dark:text-white mb-6 flex items-center gap-2"><i data-lucide="send" class="w-6 h-6 text-gold"></i> Kirim Pesan</h3>
        <form class="space-y-4">
          <div class="grid sm:grid-cols-2 gap-4">
            <div>
              <label class="block text-sm font-medium text-slate-700 dark:text-slate-200 mb-1">Nama Lengkap</label>
              <input type="text" class="w-full px-4 py-2.5 rounded-xl border border-slate-200 dark:border-slate-700 bg-transparent focus:outline-none focus:ring-2 focus:ring-primary transition-shadow" placeholder="Nama Anda">
            </div>
            <div>
              <label class="block text-sm font-medium text-slate-700 dark:text-slate-200 mb-1">Nomor Telepon</label>
              <input type="text" class="w-full px-4 py-2.5 rounded-xl border border-slate-200 dark:border-slate-700 bg-transparent focus:outline-none focus:ring-2 focus:ring-primary transition-shadow" placeholder="08xxxxxxxxxx">
            </div>
          </div>
          <div>
            <label class="block text-sm font-medium text-slate-700 dark:text-slate-200 mb-1">Email</label>
            <input type="email" class="w-full px-4 py-2.5 rounded-xl border border-slate-200 dark:border-slate-700 bg-transparent focus:outline-none focus:ring-2 focus:ring-primary transition-shadow" placeholder="email@domain.com">
          </div>
          <div>
            <label class="block text-sm font-medium text-slate-700 dark:text-slate-200 mb-1">Pesan</label>
            <textarea rows="4" class="w-full px-4 py-2.5 rounded-xl border border-slate-200 dark:border-slate-700 bg-transparent focus:outline-none focus:ring-2 focus:ring-primary transition-shadow resize-none" placeholder="Tulis pesan Anda di sini..."></textarea>
          </div>
          <button type="submit" class="btn-shimmer w-full inline-flex justify-center items-center gap-2 px-6 py-3 bg-gradient-to-r from-primary to-primary-light text-white font-semibold rounded-xl shadow-lg hover:shadow-xl transition-shadow">
            Kirim Pesan <i data-lucide="send" class="w-4 h-4"></i>
          </button>
        </form>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer class="bg-[#061b4d] text-white pt-16 pb-8 relative border-t-4 border-gold/20">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="grid md:grid-cols-4 gap-8 mb-12">
      <div class="space-y-4">
        <div class="flex items-center gap-3">
          <div class="w-12 h-12" id="footerLogo"></div>
          <div>
            <p class="font-display font-bold text-lg">DESA NAMO BINTANG</p>
            <p class="text-xs text-slate-400">Kabupaten Deli Serdang</p>
          </div>
        </div>
        <p class="text-sm text-slate-400 leading-relaxed">Website resmi Desa Namo Bintang, Kecamatan Pancur Batu, Kabupaten Deli Serdang, Provinsi Sumatera Utara.</p>
      </div>
      <div>
        <h4 class="font-display font-bold text-base mb-4 text-gold">Tautan Cepat</h4>
        <ul class="space-y-2 text-sm text-slate-400">
          <li><a href="#beranda" class="hover:text-gold transition-colors">Beranda</a></li>
          <li><a href="#profil" class="hover:text-gold transition-colors">Profil Desa</a></li>
          <li><a href="#pemerintahan" class="hover:text-gold transition-colors">Pemerintahan</a></li>
          <li><a href="#statistik" class="hover:text-gold transition-colors">Statistik</a></li>
        </ul>
      </div>
      <div>
        <h4 class="font-display font-bold text-base mb-4 text-gold">Informasi</h4>
        <ul class="space-y-2 text-sm text-slate-400">
          <li><a href="#potensi" class="hover:text-gold transition-colors">Potensi Desa</a></li>
          <li><a href="#galeri" class="hover:text-gold transition-colors">Galeri</a></li>
          <li><a href="#berita" class="hover:text-gold transition-colors">Informasi</a></li>
          <li><a href="#kontak" class="hover:text-gold transition-colors">Kontak</a></li>
        </ul>
      </div>
      <div>
        <h4 class="font-display font-bold text-base mb-4 text-gold">Peta Lokasi</h4>
        <div class="rounded-xl overflow-hidden border border-white/10 h-32 shadow-lg">
          <iframe src="https://www.google.com/maps?q=Desa%20Namo%20Bintang%2C%20Pancur%20Batu%2C%20Deli%20Serdang&output=embed" width="100%" height="100%" style="border:0; filter: grayscale(100%);" allowfullscreen="" loading="lazy"></iframe>
        </div>
      </div>
    </div>
    <div class="pt-8 border-t border-white/10 text-center text-sm text-slate-400 space-y-2">
      <p>&copy; 2024 Desa Namo Bintang. Hak Cipta Dilindungi.</p>
      <p class="flex items-center justify-center gap-1.5 text-slate-300 font-medium">Dibuat dengan cinta oleh Anak KKN Kelompok 1 Desa Namo Bintang untuk Masyarakat Desa Namo Bintang <span class="text-red-500 text-lg">❤️</span></p>
    </div>
  </div>
</footer>

<!-- SCRIPTS -->
<script>
  // Init AOS & Lucide
  AOS.init({ duration: 800, once: true, offset: 50 });
  lucide.createIcons();

  // Render Logos
  const logoUrl = 'https://z-cdn-media.chatglm.cn/files/f09c0a12-a0b5-46ce-a728-c0f583328dc9.png?auth_key=1886614175-a7011d5416d6435995606971fd457f2b-0-ebb113cd6386fc60e927dfefe4a8a37a';
  document.getElementById('navLogo').innerHTML = `<img src="${logoUrl}" alt="Logo Desa" class="w-full h-full object-contain rounded-full">`;
  document.getElementById('footerLogo').innerHTML = `<img src="${logoUrl}" alt="Logo Desa" class="w-full h-full object-contain rounded-full">`;
  document.getElementById('heroLogo').innerHTML = `<img src="${logoUrl}" alt="Logo Desa" class="w-full h-full object-contain">`;
  document.getElementById('profilLogo').innerHTML = `<img src="${logoUrl}" alt="Logo Desa" class="w-full h-full object-contain">`;
  
  const heroWatermark = document.getElementById('heroWatermark');
  heroWatermark.style.backgroundImage = `url('${logoUrl}')`;
  heroWatermark.style.backgroundSize = 'contain';
  heroWatermark.style.backgroundRepeat = 'no-repeat';
  heroWatermark.style.backgroundPosition = 'center';

  // Loader
  window.addEventListener('load', () => {
    setTimeout(() => {
      document.getElementById('loader').style.opacity = '0';
      setTimeout(() => document.getElementById('loader').style.display = 'none', 700);
    }, 500);
  });

  // Dark Mode
  function toggleDarkMode() {
    document.documentElement.classList.toggle('dark');
    const icon = document.getElementById('themeIcon');
    if (document.documentElement.classList.contains('dark')) {
      icon.setAttribute('data-lucide', 'sun');
    } else {
      icon.setAttribute('data-lucide', 'moon');
    }
    lucide.createIcons();
  }

  // Mobile Menu
  function toggleMobileMenu() {
    document.getElementById('mobileMenu').classList.toggle('hidden');
  }

  // Search
  function toggleSearch(e) {
    if (e && e.target.id !== 'searchOverlay' && e.type === 'click') return;
    document.getElementById('searchOverlay').classList.toggle('hidden');
  }

  // Counter
  const counters = document.querySelectorAll('.counter-stat');
  const animateCounter = (counter) => {
    const target = +counter.getAttribute('data-target');
    let current = 0;
    const increment = target / 100;
    const update = () => {
      current += increment;
      if (current < target) {
        counter.innerText = Math.ceil(current).toLocaleString('id-ID');
        requestAnimationFrame(update);
      } else {
        counter.innerText = target.toLocaleString('id-ID');
      }
    };
    update();
  };
  
  const counterObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        animateCounter(entry.target);
        counterObserver.unobserve(entry.target);
      }
    });
  }, { threshold: 0.5 });

  counters.forEach(c => counterObserver.observe(c));

  // Chart.js Global Config
  const chartFontColor = document.documentElement.classList.contains('dark') ? '#cbd5e1' : '#475569';
  const chartGridColor = 'rgba(148, 163, 184, 0.1)';
  Chart.defaults.font.family = 'Inter';
  Chart.defaults.color = chartFontColor;

  // 1. Gender Chart
  new Chart(document.getElementById('genderChart').getContext('2d'), {
    type: 'doughnut',
    data: {
      labels: ['Laki-laki', 'Perempuan'],
      datasets: [{
        data: [3324, 3221],
        backgroundColor: ['#0B3C91', '#D4AF37'],
        borderWidth: 0,
        hoverOffset: 8
      }]
    },
    options: {
      responsive: true,
      maintainAspectRatio: false,
      plugins: {
        legend: { position: 'bottom', labels: { padding: 15, usePointStyle: true } }
      }
    }
  });

  // 2. Religion Chart
  new Chart(document.getElementById('religionChart').getContext('2d'), {
    type: 'doughnut',
    data: {
      labels: ['Islam', 'Kristen', 'Katolik'],
      datasets: [{
        data: [2762, 3214, 569],
        backgroundColor: ['#10B981', '#0B3C91', '#D4AF37'],
        borderWidth: 0,
        hoverOffset: 8
      }]
    },
    options: {
      responsive: true,
      maintainAspectRatio: false,
      plugins: {
        legend: { position: 'bottom', labels: { padding: 15, usePointStyle: true } }
      }
    }
  });

  // 3. Education Chart
  new Chart(document.getElementById('educationChart').getContext('2d'), {
    type: 'bar',
    data: {
      labels: ['SD/MI', 'SLTP/MTs', 'SLTA/MA', 'S1/Diploma', 'Putus Sekolah'],
      datasets: [{
        data: [1266, 856, 1218, 368, 4],
        backgroundColor: ['#0B3C91', '#1E5BB8', '#60A5FA', '#D4AF37', '#94a3b8'],
        borderRadius: 6
      }]
    },
    options: {
      indexAxis: 'y',
      responsive: true,
      maintainAspectRatio: false,
      plugins: { legend: { display: false } },
      scales: {
        x: { grid: { color: chartGridColor }, beginAtZero: true },
        y: { grid: { display: false } }
      }
    }
  });

  // 4. Profession Chart
  new Chart(document.getElementById('professionChart').getContext('2d'), {
    type: 'polarArea',
    data: {
      labels: ['Petani', 'Pedagang', 'PNS', 'Tukang', 'TNI/Polri', 'Pensiunan', 'Sopir', 'Buruh', 'Swasta', 'Lain-lain'],
      datasets: [{
        data: [440, 241, 57, 78, 18, 6, 159, 118, 244, 116],
        backgroundColor: [
          'rgba(11, 60, 145, 0.7)', 'rgba(30, 91, 184, 0.7)', 'rgba(96, 165, 250, 0.7)',
          'rgba(212, 175, 55, 0.7)', 'rgba(245, 197, 66, 0.7)', 'rgba(16, 185, 129, 0.7)',
          'rgba(52, 211, 153, 0.7)', 'rgba(148, 163, 184, 0.7)', 'rgba(184, 148, 31, 0.7)', 'rgba(100, 116, 139, 0.7)'
        ],
        borderWidth: 0
      }]
    },
    options: {
      responsive: true,
      maintainAspectRatio: false,
      plugins: {
        legend: { position: 'right', labels: { padding: 10, usePointStyle: true, font: { size: 10 } } }
      },
      scales: {
        r: { grid: { color: chartGridColor }, ticks: { display: false } }
      }
    }
  });

  // 5. Agriculture Chart
  new Chart(document.getElementById('agricultureChart').getContext('2d'), {
    type: 'bar',
    data: {
      labels: ['Jagung', 'Sawit', 'Singkong', 'Kakao', 'Padi Sawah', 'Karet', 'Kelapa', 'Lain-lain'],
      datasets: [{
        data: [17.3, 11.9, 11, 7.6, 5.2, 3, 1, 1.5],
        backgroundColor: '#10B981',
        borderRadius: 6
      }]
    },
    options: {
      responsive: true,
      maintainAspectRatio: false,
      plugins: { legend: { display: false } },
      scales: {
        y: { grid: { color: chartGridColor }, beginAtZero: true, title: { display: true, text: 'Hektar (Ha)' } },
        x: { grid: { display: false } }
      }
    }
  });
</script>
</body>
</html>
