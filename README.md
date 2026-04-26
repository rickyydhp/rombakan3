<!DOCTYPE html>
<html lang="id" class="scroll-smooth">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PT RITS NUSA KENARI - Integrated Facility Service & Parking Management</title>

    <!-- Framework & Fonts -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <link
        href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=Playfair+Display:ital,wght@0,700;1,700&display=swap"
        rel="stylesheet">

    <style>
        :root {
            --maroon: #800000;
            --carbon: #1a1a1a;
            --gold: #D4AF37;
            --deep-brown: #3E2723;
            --cream-light: #FCFAEE;
            --cream-dark: #F5E6D3;
        }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: var(--cream-light);
            color: var(--deep-brown);
        }

        .font-serif {
            font-family: 'Playfair Display', serif;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: var(--cream-dark);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--maroon);
            border-radius: 5px;
        }

        /* SPA Mechanism */
        .page-section {
            display: none;
            opacity: 0;
            transform: scale(0.98);
            transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .page-section.active {
            display: block;
            opacity: 1;
            transform: scale(1);
        }

        /* Running Text */
        .marquee {
            background: var(--carbon);
            color: white;
            padding: 10px 0;
            overflow: hidden;
            white-space: nowrap;
        }

        .marquee-inner {
            display: inline-block;
            animation: slide 30s linear infinite;
        }

        @keyframes slide {
            from {
                transform: translateX(0);
            }

            to {
                transform: translateX(-50%);
            }
        }

        /* Floating Animation */
        @keyframes float {

            0%,
            100% {
                transform: translateY(0px);
            }

            50% {
                transform: translateY(-10px);
            }
        }

        .animate-float {
            animation: float 3s ease-in-out infinite;
        }

        /* Glassmorphism */
        .glass {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px);
            border-bottom: 2px solid var(--maroon);
        }

        /* Zoom Container */
        .zoom-container {
            overflow: hidden;
            position: relative;
            border-radius: 1.5rem;
            transition: all 0.4s ease;
        }

        .zoom-container img {
            transition: transform 0.8s ease;
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .zoom-container:hover img {
            transform: scale(1.1);
        }

        .hover-card:hover {
            transform: translateY(-12px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        /* Photo Overlay */
        .photo-text {
            position: absolute;
            inset: 0;
            background: linear-gradient(to top, rgba(62, 39, 35, 0.9) 0%, transparent 70%);
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            padding: 20px;
        }

        /* Mobile Menu Overlay */
        #mobileMenu {
            transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            transform: translateX(100%);
        }

        #mobileMenu.open {
            transform: translateX(0);
        }
    </style>
</head>

<body class="antialiased">

    <!-- TOP BAR RUNNING TEXT -->
    <div class="marquee border-b border-[#D4AF37]">
        <div class="marquee-inner">
            <span class="mx-10 font-bold text-[10px] uppercase tracking-[0.3em]">
                <i class="fas fa-shield-alt text-[#D4AF37] mr-2"></i> PT RITS NUSA KENARI — INTEGRATED PARKING SYSTEM —
                MANLESS SMART GATE 2026 — REAL-TIME MONITORING — SECURITY & INTEGRITY FIRST —
            </span>
            <span class="mx-10 font-bold text-[10px] uppercase tracking-[0.3em]">
                <i class="fas fa-shield-alt text-[#D4AF37] mr-2"></i> PT RITS NUSA KENARI — INTEGRATED PARKING SYSTEM —
                MANLESS SMART GATE 2026 — REAL-TIME MONITORING — SECURITY & INTEGRITY FIRST —
            </span>
        </div>
    </div>

    <!-- NAVIGATION -->
    <nav class="glass sticky top-0 z-50 py-4 px-6">
        <div class="max-w-7xl mx-auto flex justify-between items-center">
            <div class="flex items-center gap-4 cursor-pointer group" onclick="showPage('home')">
                <div
                    class="w-12 h-12 md:w-14 md:h-14 bg-[#800000] rounded-xl flex items-center justify-center shadow-lg group-hover:rotate-6 transition-transform">
                    <img src="foto/logo_rits1" class="w-8 h-8 md:w-10 md:h-10 object-contain">
                </div>
                <div>
                    <h1 class="font-extrabold text-lg md:text-xl leading-none tracking-tighter text-[#3E2723]">RITS NUSA
                        <span class="text-[#800000]">KENARI</span>
                    </h1>
                    <p class="text-[8px] md:text-[9px] font-bold text-gray-500 tracking-[0.3em] uppercase italic">
                        Facility & Parking Management</p>
                </div>
            </div>

            <!-- Desktop Menu -->
            <div
                class="hidden lg:flex items-center gap-8 font-bold text-[11px] uppercase tracking-widest text-[#3E2723]">
                <button onclick="showPage('home')"
                    class="hover:text-[#800000] transition-colors relative after:content-[''] after:absolute after:-bottom-1 after:left-0 after:w-0 after:h-0.5 after:bg-[#800000] hover:after:w-full after:transition-all">Home</button>
                <button onclick="showPage('about')" class="hover:text-[#800000] transition-colors">Directors</button>
                <button onclick="showPage('services')" class="hover:text-[#800000] transition-colors">Services</button>
                <button onclick="showPage('portfolio')"
                    class="hover:text-[#800000] transition-colors">Portfolio</button>
                <button onclick="showPage('career')" class="hover:text-[#800000] transition-colors">Career</button>
                <button onclick="showPage('contact')"
                    class="bg-[#800000] text-white px-6 py-2.5 rounded-full hover:bg-black transition-all shadow-md">Get
                    in Touch</button>
            </div>

            <button class="lg:hidden text-2xl text-[#800000]" id="menuBtn"><i class="fas fa-bars"></i></button>
        </div>
    </nav>

    <!-- MOBILE MENU OVERLAY -->
    <div id="mobileMenu" class="fixed inset-0 z-[60] bg-[#FCFAEE] flex flex-col p-8 lg:hidden">
        <div class="flex justify-end mb-12">
            <button id="closeBtn" class="text-4xl text-[#800000]">&times;</button>
        </div>
        <div class="flex flex-col gap-8 text-center text-xl font-bold uppercase tracking-[0.2em]">
            <button onclick="showPage('home'); toggleMenu()" class="hover:text-[#800000]">Home</button>
            <button onclick="showPage('about'); toggleMenu()" class="hover:text-[#800000]">Directors</button>
            <button onclick="showPage('services'); toggleMenu()" class="hover:text-[#800000]">Services</button>
            <button onclick="showPage('portfolio'); toggleMenu()" class="hover:text-[#800000]">Portfolio</button>
            <button onclick="showPage('career'); toggleMenu()" class="hover:text-[#800000]">Career</button>
            <button onclick="showPage('contact'); toggleMenu()"
                class="bg-[#800000] text-white py-4 rounded-2xl shadow-xl">Contact Us</button>
        </div>
    </div>

    <main>
        <!-- HOME SECTION -->
        <section id="home" class="page-section active">
            <div class="relative min-h-[85vh] flex items-center bg-[#1A1A1A] overflow-hidden">
                <div
                    class="absolute inset-0 opacity-40 bg-[url('https://images.unsplash.com/photo-1506521781263-d8422e82f27a?q=80&w=2000')] bg-cover">
                </div>
                <div class="absolute inset-0 bg-gradient-to-r from-black to-transparent"></div>
                <div class="max-w-7xl mx-auto px-6 relative z-10 grid lg:grid-cols-2 gap-12 items-center">
                    <div class="text-center lg:text-left">
                        <h2
                            class="text-[#D4AF37] font-black uppercase tracking-[0.5em] mb-4 text-[10px] md:text-xs animate-bounce">
                            Premium Quality Solution</h2>
                        <h1 class="text-5xl md:text-8xl font-serif text-white leading-tight mb-8">Elevating <br><span
                                class="italic text-[#D4AF37]">Parking</span> Experience.</h1>
                        <p class="text-base md:text-lg text-gray-300 mb-10 max-w-lg mx-auto lg:mx-0">Sistem parkir
                            terintegrasi yang menggabungkan transparansi data, keamanan berlapis, dan teknologi Manless
                            terkini.</p>

                        <!-- ACTION BUTTONS -->
                        <div class="flex flex-wrap justify-center lg:justify-start gap-4">
                            <button onclick="showPage('services')"
                                class="bg-[#800000] text-white px-8 md:px-10 py-5 rounded-2xl font-black text-xs uppercase tracking-widest shadow-2xl hover:scale-105 transition-all">Mulai
                                Kerjasama</button>

                            <!-- FITUR BARU: DOWNLOAD COM-PRO -->
                            <a href="files/company-profile.pdf" download
                                class="bg-transparent border-2 border-[#D4AF37] text-[#D4AF37] px-8 md:px-10 py-5 rounded-2xl font-black text-xs uppercase tracking-widest hover:bg-[#D4AF37] hover:text-black transition-all flex items-center gap-3 shadow-xl">
                                <i class="fas fa-file-download"></i> Company Profile
                            </a>
                        </div>

                        <div class="flex items-center justify-center lg:justify-start gap-4 text-white px-6 mt-10">
                            <span class="w-12 h-[2px] bg-[#800000]"></span>
                            <span class="font-bold text-xs uppercase tracking-widest italic">Since 2025</span>
                        </div>
                    </div>
                    <div class="hidden lg:block">
                        <div class="zoom-container border-4 border-white/10 animate-float p-2">
                            <img src="https://images.unsplash.com/photo-1590674899484-13da0d1b58f5?q=80&w=1000"
                                alt="Smart Gate" class="rounded-[2rem]">
                        </div>
                    </div>
                </div>
            </div>

            <!-- TECH SPECIFICATION GRID -->
            <div class="max-w-7xl mx-auto px-6 -mt-16 relative z-20 pb-20">
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                    <div class="bg-white p-8 rounded-[2.5rem] shadow-xl border-b-8 border-[#800000] hover-card">
                        <i class="fas fa-barcode text-3xl text-[#800000] mb-6"></i>
                        <h4 class="font-bold text-lg mb-2">Smart Dispenser</h4>
                        <p class="text-xs text-gray-500">Thermal ticket system dengan panduan suara & QR ready.</p>
                    </div>
                    <div class="bg-white p-8 rounded-[2.5rem] shadow-xl border-b-8 border-[#1a1a1a] hover-card">
                        <i class="fas fa-video text-3xl text-[#800000] mb-6"></i>
                        <h4 class="font-bold text-lg mb-2">AI Surveillance</h4>
                        <p class="text-xs text-gray-500">IP Camera ANPR untuk deteksi plat nomor otomatis 24/7.</p>
                    </div>
                    <div class="bg-white p-8 rounded-[2.5rem] shadow-xl border-b-8 border-[#800000] hover-card">
                        <i class="fas fa-microchip text-3xl text-[#800000] mb-6"></i>
                        <h4 class="font-bold text-lg mb-2">Barrier Gate</h4>
                        <p class="text-xs text-gray-500">High-speed engine 1.8 detik dengan fitur anti-collision.</p>
                    </div>
                    <div class="bg-white p-8 rounded-[2.5rem] shadow-xl border-b-8 border-[#1a1a1a] hover-card">
                        <i class="fas fa-cloud-upload-alt text-3xl text-[#800000] mb-6"></i>
                        <h4 class="font-bold text-lg mb-2">Cloud Report</h4>
                        <p class="text-xs text-gray-500">Dashboard pendapatan real-time yang dapat diakses via HP.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- ABOUT & DIRECTORS -->
        <section id="about" class="page-section py-24 px-6 bg-white">
            <div class="max-w-7xl mx-auto">
                <div class="flex flex-col lg:flex-row gap-20 mb-32 items-center">
                    <div class="lg:w-1/2">
                        <span class="text-[#800000] font-black uppercase tracking-widest text-xs">Visi Kami</span>
                        <h2 class="text-4xl md:text-5xl font-serif mt-4 mb-8 leading-tight italic">Menjadi Pemimpin
                            Dalam <span class="bg-[#800000] text-white px-4 not-italic">Integrated</span> Facility
                            Service.</h2>
                        <div class="space-y-6 text-[#4E342E] leading-relaxed">
                            <p>PT RITS NUSA KENARI didirikan dengan misi membawa standar baru dalam manajemen properti.
                                Kami percaya bahwa lahan parkir adalah aset strategis yang memerlukan pengelolaan
                                cerdas.</p>
                            <div class="bg-[#FDF5E6] p-6 border-l-8 border-[#800000] rounded-r-2xl italic font-medium">
                                "Mewujudkan perusahaan yang aman, handal, dan terpercaya dengan fokus pada kepuasan
                                pelanggan dan efisiensi teknologi."
                            </div>
                        </div>
                    </div>
                    <div class="lg:w-1/2 grid grid-cols-2 gap-4">
                        <div class="space-y-4 pt-12">
                            <div class="zoom-container h-48 md:h-64"><img
                                    src="https://images.unsplash.com/photo-1573164713988-8665fc963095?q=80&w=400"></div>
                            <div class="bg-[#3E2723] p-8 rounded-3xl text-white text-center">
                                <h5 class="text-2xl md:text-3xl font-bold">10+</h5>
                                <p class="text-[8px] md:text-[10px] uppercase font-bold tracking-widest">Tahun
                                    Pengalaman</p>
                            </div>
                        </div>
                        <div class="space-y-4">
                            <div class="bg-[#800000] p-8 rounded-3xl text-white text-center">
                                <h5 class="text-2xl md:text-3xl font-bold">50+</h5>
                                <p class="text-[8px] md:text-[10px] uppercase font-bold tracking-widest">Profesional
                                    Staff</p>
                            </div>
                            <div class="zoom-container h-64 md:h-80"><img
                                    src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?q=80&w=400"></div>
                        </div>
                    </div>
                </div>

                <div class="text-center mb-20">
                    <h2 class="text-4xl md:text-5xl font-serif italic mb-4 leading-none">Board of Directors</h2>
                    <div class="w-24 h-1.5 bg-[#800000] mx-auto rounded-full"></div>
                </div>

                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-10">
                    <div class="group text-center">
                        <div
                            class="zoom-container h-96 mb-6 shadow-2xl border-b-8 border-transparent group-hover:border-[#800000]">
                            <img src="foto/ruben.jpeg" class="grayscale group-hover:grayscale-0">
                            <div class="photo-text">
                                <h4 class="text-xl font-black italic text-white">Ruben Etidena</h4>
                                <p class="text-[10px] uppercase font-bold text-[#D4AF37]">Komisaris</p>
                            </div>
                        </div>
                    </div>
                    <div class="group text-center lg:-mt-12">
                        <div
                            class="zoom-container h-[450px] mb-6 shadow-2xl border-b-8 border-transparent group-hover:border-[#800000]">
                            <img src="foto/john.jpeg" class="grayscale group-hover:grayscale-0">
                            <div class="photo-text">
                                <h4 class="text-xl font-black italic text-white">Jhon Sius Langkola</h4>
                                <p class="text-[10px] uppercase font-bold text-[#D4AF37]">Direktur Utama</p>
                            </div>
                        </div>
                    </div>
                    <div class="group text-center">
                        <div
                            class="zoom-container h-96 mb-6 shadow-2xl border-b-8 border-transparent group-hover:border-[#800000]">
                            <img src="foto/tius.jpeg" class="grayscale group-hover:grayscale-0">
                            <div class="photo-text">
                                <h4 class="text-xl font-black italic text-white">Ignatius Etidena</h4>
                                <p class="text-[10px] uppercase font-bold text-[#D4AF37]">Direktur Keuangan</p>
                            </div>
                        </div>
                    </div>
                    <div class="group text-center lg:-mt-12">
                        <div
                            class="zoom-container h-[450px] mb-6 shadow-2xl border-b-8 border-transparent group-hover:border-[#800000]">
                            <img src="foto/toni.jpeg" class="grayscale group-hover:grayscale-0">
                            <div class="photo-text">
                                <h4 class="text-xl font-black italic text-white">Tony BBH.</h4>
                                <p class="text-[10px] uppercase font-bold text-[#D4AF37]">Direktur Umum</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- SERVICES SECTION (Full 6 Models) -->
        <section id="services" class="page-section py-24 px-6 bg-[#F5E6D3]">
            <div class="max-w-7xl mx-auto">
                <div class="text-center mb-20">
                    <h2 class="text-4xl md:text-5xl font-serif italic mb-6">Model Kerja Sama Strategis</h2>
                    <p class="text-[#800000] font-bold tracking-widest uppercase text-xs">Pilihan Fleksibel Untuk Bisnis
                        Anda</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <div onclick="openModal('management')"
                        class="bg-white p-12 rounded-[3rem] shadow-xl hover-card border-l-[12px] border-[#800000] cursor-pointer">
                        <i class="fas fa-users-cog text-4xl text-[#3E2723] mb-8"></i>
                        <h3 class="text-2xl font-bold mb-4 italic">Management Fee</h3>
                        <p class="text-sm text-gray-500 mb-8">Pengelolaan operasional penuh oleh RITS dengan imbal jasa
                            tetap (Fixed Fee).</p>
                        <span class="text-[#800000] font-black text-[10px] uppercase tracking-widest">Read Detail <i
                                class="fas fa-arrow-right"></i></span>
                    </div>

                    <div onclick="openModal('profit')"
                        class="bg-[#1A1A1A] p-12 rounded-[3rem] shadow-xl hover-card border-l-[12px] border-[#D4AF37] cursor-pointer text-white">
                        <i class="fas fa-chart-pie text-4xl text-[#D4AF37] mb-8"></i>
                        <h3 class="text-2xl font-bold mb-4 italic text-[#D4AF37]">Profit Sharing</h3>
                        <p class="text-sm opacity-70 mb-8">Bagi hasil dari laba operasional (Net Profit) setelah
                            dikurangi biaya.</p>
                        <span
                            class="text-[#D4AF37] font-black text-[10px] uppercase tracking-widest flex items-center gap-2 underline">Read
                            Detail <i class="fas fa-arrow-right"></i></span>
                    </div>

                    <div onclick="openModal('revenue')"
                        class="bg-white p-12 rounded-[3rem] shadow-xl hover-card border-l-[12px] border-[#800000] cursor-pointer">
                        <i class="fas fa-money-bill-wave text-4xl text-[#3E2723] mb-8"></i>
                        <h3 class="text-2xl font-bold mb-4 italic">Revenue Sharing</h3>
                        <p class="text-sm text-gray-500 mb-8">Bagi hasil dari pendapatan bruto (Gross Revenue) dikurangi
                            pajak daerah.</p>
                        <span
                            class="text-[#800000] font-black text-[10px] uppercase tracking-widest flex items-center gap-2">Read
                            Detail <i class="fas fa-arrow-right"></i></span>
                    </div>

                    <div onclick="openModal('guaranteed')"
                        class="bg-[#800000] p-12 rounded-[3rem] shadow-xl hover-card border-l-[12px] border-[#1A1A1A] cursor-pointer text-white">
                        <i class="fas fa-handshake-alt text-4xl text-white mb-8"></i>
                        <h3 class="text-2xl font-bold mb-4 italic">Guaranteed Income</h3>
                        <p class="text-sm opacity-90 mb-8 leading-relaxed">Kami menyewa lahan parkir Anda dengan harga
                            tetap tiap bulan tanpa risiko.</p>
                        <span
                            class="text-white font-black text-[10px] uppercase tracking-widest flex items-center gap-2 underline">Read
                            Detail <i class="fas fa-arrow-right"></i></span>
                    </div>

                    <div onclick="openModal('technical')"
                        class="bg-white p-12 rounded-[3rem] shadow-xl hover-card border-l-[12px] border-[#800000] cursor-pointer">
                        <i class="fas fa-tools text-4xl text-[#3E2723] mb-8"></i>
                        <h3 class="text-2xl font-bold mb-4 italic">Technical Asst.</h3>
                        <p class="text-sm text-gray-500 mb-8 leading-relaxed">Kami bertindak sebagai konsultan
                            teknologi. SDM dari Anda, sistem dari kami.</p>
                        <span
                            class="text-[#800000] font-black text-[10px] uppercase tracking-widest flex items-center gap-2">Read
                            Detail <i class="fas fa-arrow-right"></i></span>
                    </div>

                    <div onclick="openModal('combination')"
                        class="bg-[#3E2723] p-12 rounded-[3rem] shadow-xl hover-card border-l-[12px] border-[#800000] cursor-pointer text-white">
                        <i class="fas fa-puzzle-piece text-4xl text-[#D4AF37] mb-8"></i>
                        <h3 class="text-2xl font-bold mb-4 italic">Combination Fee</h3>
                        <p class="text-sm opacity-80 mb-8 leading-relaxed">Penggabungan elemen model lainnya untuk
                            saling menguntungkan secara optimal.</p>
                        <span
                            class="text-[#D4AF37] font-black text-[10px] uppercase tracking-widest flex items-center gap-2 underline">Read
                            Detail <i class="fas fa-arrow-right"></i></span>
                    </div>
                </div>

                <!-- Strategic Features Grid -->
                <div class="mt-32 p-8 md:p-16 glass rounded-[3rem] md:rounded-[4rem] border-2 border-[#800000]">
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 text-center">
                        <div class="space-y-4">
                            <div
                                class="w-16 h-16 md:w-20 md:h-20 bg-[#800000] rounded-full mx-auto flex items-center justify-center text-white text-2xl shadow-lg">
                                <i class="fas fa-headset"></i>
                            </div>
                            <h5 class="font-bold text-lg italic tracking-tighter">SDM & Training</h5>
                        </div>
                        <div class="space-y-4">
                            <div
                                class="w-16 h-16 md:w-20 md:h-20 bg-[#1A1A1A] rounded-full mx-auto flex items-center justify-center text-white text-2xl shadow-lg">
                                <i class="fas fa-sync"></i>
                            </div>
                            <h5 class="font-bold text-lg italic tracking-tighter">Maintenance</h5>
                        </div>
                        <div class="space-y-4">
                            <div
                                class="w-16 h-16 md:w-20 md:h-20 bg-[#800000] rounded-full mx-auto flex items-center justify-center text-white text-2xl shadow-lg">
                                <i class="fas fa-file-invoice"></i>
                            </div>
                            <h5 class="font-bold text-lg italic tracking-tighter">Legal & Tax</h5>
                        </div>
                        <div class="space-y-4">
                            <div
                                class="w-16 h-16 md:w-20 md:h-20 bg-[#1A1A1A] rounded-full mx-auto flex items-center justify-center text-white text-2xl shadow-lg">
                                <i class="fas fa-network-wired"></i>
                            </div>
                            <h5 class="font-bold text-lg italic tracking-tighter">IT Dashboard</h5>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- PORTFOLIO SECTION (Full 6 Locations) -->
        <section id="portfolio" class="page-section py-24 px-6 bg-white">
            <div class="max-w-7xl mx-auto">
                <div class="flex flex-col md:flex-row justify-between items-end mb-16 gap-6">
                    <h2 class="text-4xl md:text-5xl font-serif italic mb-6 leading-tight">Jejak Langkah <br><span
                            class="bg-[#800000] text-white px-3">Operasional</span> Kami.</h2>
                    <span
                        class="text-6xl font-black text-[#F5E6D3] select-none hidden md:block uppercase">Portfolio</span>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">
                    <div class="group">
                        <div
                            class="zoom-container h-[400px] shadow-2xl rounded-[2.5rem] mb-6 border-b-8 border-[#800000]">
                            <img src="foto/bimoli.jpeg" class="grayscale group-hover:grayscale-0">
                            <div class="photo-text">
                                <h4 class="text-2xl font-black text-white italic">KAWASAN BIMOLI</h4>
                                <p class="text-xs font-bold text-gray-300">Jakarta Utara</p>
                            </div>
                        </div>
                    </div>
                    <div class="group md:mt-12">
                        <div
                            class="zoom-container h-[400px] shadow-2xl rounded-[2.5rem] mb-6 border-b-8 border-[#1A1A1A]">
                            <img src="foto/rs_mery.jpeg" class="grayscale group-hover:grayscale-0">
                            <div class="photo-text">
                                <h4 class="text-2xl font-black text-white italic">RS MARY CILEUNGSI</h4>
                                <p class="text-xs font-bold text-gray-300">Bogor, Jawa Barat</p>
                            </div>
                        </div>
                    </div>
                    <div class="group">
                        <div
                            class="zoom-container h-[400px] shadow-2xl rounded-[2.5rem] mb-6 border-b-8 border-[#800000]">
                            <img src="foto/jababeka.jpeg" class="grayscale group-hover:grayscale-0">
                            <div class="photo-text">
                                <h4 class="text-2xl font-black text-white italic">HOLLYWOOD JUNCTION</h4>
                                <p class="text-xs font-bold text-gray-300">Cikarang</p>
                            </div>
                        </div>
                    </div>
                    <!-- Row 2 Portfolio -->
                    <div class="group">
                        <div
                            class="zoom-container h-[400px] shadow-2xl rounded-[2.5rem] mb-6 border-b-8 border-[#1A1A1A]">
                            <img src="https://images.unsplash.com/photo-1573164713988-8665fc963095?q=80&w=800"
                                class="grayscale group-hover:grayscale-0">
                            <div class="photo-text">
                                <h4 class="text-2xl font-black text-white italic">GADING CENTER</h4>
                                <p class="text-xs font-bold text-gray-300">Jakarta Utara</p>
                            </div>
                        </div>
                    </div>
                    <div class="group md:mt-12">
                        <div
                            class="zoom-container h-[400px] shadow-2xl rounded-[2.5rem] mb-6 border-b-8 border-[#800000]">
                            <img src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?q=80&w=800"
                                class="grayscale group-hover:grayscale-0">
                            <div class="photo-text">
                                <h4 class="text-2xl font-black text-white italic">KANTOR CABANG BEKASI</h4>
                                <p class="text-xs font-bold text-gray-300">Bekasi Town Square</p>
                            </div>
                        </div>
                    </div>
                    <div class="group">
                        <div
                            class="zoom-container h-[400px] shadow-2xl rounded-[2.5rem] mb-6 border-b-8 border-[#1A1A1A]">
                            <img src="https://images.unsplash.com/photo-1590674899484-13da0d1b58f5?q=80&w=800"
                                class="grayscale group-hover:grayscale-0">
                            <div class="photo-text">
                                <h4 class="text-2xl font-black text-white italic">SIAK LOGISTIC HUB</h4>
                                <p class="text-xs font-bold text-gray-300">Tanjung Priok</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- CAREER SECTION -->
        <section id="career" class="page-section py-24 px-6 bg-[#3E2723] text-[#F5E6D3]">
            <div class="max-w-7xl mx-auto">
                <div class="grid lg:grid-cols-2 gap-20 items-center">
                    <div>
                        <h2 class="text-4xl md:text-5xl font-serif italic mb-8">Bergabung Bersama Kami.</h2>
                        <p class="text-lg opacity-80 leading-relaxed mb-10 italic font-light">"Kami mencari individu
                            berdedikasi untuk mengisi posisi operasional lapangan maupun kantor pusat."</p>
                        <div class="space-y-4">
                            <div
                                class="bg-black/20 p-8 rounded-3xl border border-white/10 flex justify-between items-center group hover:bg-[#800000] transition-all cursor-pointer">
                                <div>
                                    <h4 class="text-xl font-bold italic">Staff Operasional</h4>
                                    <p class="text-xs opacity-60">Jabodetabek</p>
                                </div>
                                <i class="fas fa-arrow-right group-hover:translate-x-3 transition-transform"></i>
                            </div>
                            <div
                                class="bg-black/20 p-8 rounded-3xl border border-white/10 flex justify-between items-center group hover:bg-[#800000] transition-all cursor-pointer">
                                <div>
                                    <h4 class="text-xl font-bold italic">IT Support</h4>
                                    <p class="text-xs opacity-60">Head Office</p>
                                </div>
                                <i class="fas fa-arrow-right group-hover:translate-x-3 transition-transform"></i>
                            </div>
                        </div>
                    </div>
                    <div class="bg-white p-8 md:p-12 rounded-[3rem] text-[#3E2723] shadow-2xl">
                        <h3 class="text-2xl font-black mb-6 uppercase italic">Kirim Lamaran</h3>
                        <form class="space-y-4">
                            <input type="text" placeholder="Nama Lengkap"
                                class="w-full bg-[#F5E6D3] rounded-2xl py-4 px-6 border-none focus:ring-2 focus:ring-[#800000]">
                            <input type="email" placeholder="Email Anda"
                                class="w-full bg-[#F5E6D3] rounded-2xl py-4 px-6 border-none focus:ring-2 focus:ring-[#800000]">
                            <button type="button"
                                class="w-full bg-[#800000] text-white py-4 rounded-2xl font-black uppercase text-xs shadow-xl">Kirim
                                Sekarang</button>
                        </form>
                    </div>
                </div>
            </div>
        </section>

        <!-- CONTACT SECTION -->
        <section id="contact" class="page-section py-24 px-6">
            <div class="max-w-7xl mx-auto grid lg:grid-cols-2 gap-20">
                <div>
                    <h2 class="text-4xl md:text-5xl font-serif italic mb-8">Let's Talk <br><span
                            class="text-[#800000]">Business.</span></h2>
                    <div class="space-y-12">
                        <div class="flex gap-8">
                            <div
                                class="w-16 h-16 bg-[#800000] text-white rounded-2xl flex items-center justify-center text-2xl shadow-lg">
                                <i class="fas fa-map-marked-alt"></i>
                            </div>
                            <div>
                                <h5 class="font-bold text-lg uppercase">Kantor Pusat</h5>
                                <p class="text-gray-500">Jl. Siak No. 9 Ruko Gading Center, Jakarta Utara.</p>
                            </div>
                        </div>
                        <div class="flex gap-8">
                            <div
                                class="w-16 h-16 bg-[#1A1A1A] text-white rounded-2xl flex items-center justify-center text-2xl shadow-lg">
                                <i class="fas fa-phone-alt"></i>
                            </div>
                            <div>
                                <h5 class="font-bold text-lg uppercase">Hubungi Kami</h5>
                                <p class="text-gray-500">Phone: +62 21 1234 5678<br>Email: info@ritsnusakenari.com</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="h-[400px] md:h-[500px] rounded-[3rem] overflow-hidden shadow-2xl border-4 border-white">
                    <iframe
                        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3967.1030232501655!2d106.9022416!3d-6.116812!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e6a1f3377519391%3A0x6a6d6f2c68f9a263!2sGading%20Center!5e0!3m2!1sid!2sid!4v1700000000000!5m2!1sid!2sid"
                        width="100%" height="100%" style="border:0;" loading="lazy"></iframe>
                </div>
            </div>
        </section>
    </main>

    <!-- FOOTER -->
    <footer class="bg-[#1A1A1A] text-white pt-24 pb-12 px-6">
        <div class="max-w-7xl mx-auto text-center">
            <div class="flex items-center justify-center gap-4 mb-8">
                <div class="w-12 h-12 bg-[#800000] rounded-xl flex items-center justify-center font-black">R</div>
                <h4 class="text-2xl font-black tracking-tighter uppercase">PT RITS NUSA KENARI</h4>
            </div>
            <div class="border-t border-white/10 pt-10 text-[10px] text-gray-600 font-bold tracking-[0.4em]">
                © 2026 PT RITS NUSA KENARI. INTEGRATED MANAGEMENT SYSTEM.
            </div>
        </div>
    </footer>

    <!-- MODAL SYSTEM -->
    <div id="modalOverlay" class="fixed inset-0 bg-black/95 hidden z-[100] flex items-center justify-center p-6"
        onclick="closeModal()">
        <div class="bg-[#FCFAEE] max-w-2xl w-full rounded-[3rem] p-8 md:p-12 relative shadow-2xl border-t-[12px] border-[#800000]"
            onclick="event.stopPropagation()">
            <button onclick="closeModal()"
                class="absolute top-6 right-8 text-4xl text-[#3E2723] hover:text-[#800000] transition-colors">&times;</button>
            <div id="modalIcon"
                class="w-20 h-20 bg-[#1A1A1A] rounded-3xl flex items-center justify-center text-[#D4AF37] text-3xl mb-8 shadow-lg">
                <i class="fas fa-handshake"></i>
            </div>
            <h2 id="modalTitle" class="text-3xl md:text-4xl font-serif italic text-[#3E2723] mb-6"></h2>
            <div
                class="bg-white p-6 md:p-8 rounded-[2rem] border-l-[10px] border-[#800000] shadow-inner leading-relaxed italic">
                <p id="modalContent"></p>
            </div>
        </div>
    </div>

    <!-- WHATSAPP -->
    <a href="https://wa.me/628123456789"
        class="fixed bottom-6 right-6 z-[60] w-14 h-14 bg-[#25d366] rounded-full flex items-center justify-center text-white text-3xl shadow-2xl hover:scale-110 transition-transform">
        <i class="fab fa-whatsapp"></i>
    </a>

    <script>
        const details = {
            management: { title: "Management Fee", desc: "Kami mengelola penuh operasional dengan imbal jasa tetap. Investasi perangkat keras sepenuhnya menjadi tanggung jawab kami. Owner menerima pendapatan bersih setelah biaya operasional." },
            profit: { title: "Profit Sharing", desc: "Sistem bagi hasil berdasarkan Laba Bersih Operasional. Pendapatan dikurangi pajak daerah dan biaya operasional langsung, kemudian laba bersih dibagi sesuai persentase kesepakatan." },
            revenue: { title: "Revenue Sharing", desc: "Bagi hasil yang dihitung langsung dari Pendapatan Kotor setelah dikurangi pajak daerah. Seluruh biaya operasional harian (Gaji SDM, Maintenance) menjadi tanggung jawab RITS Parking." },
            guaranteed: { title: "Guaranteed Income", desc: "Kami menyewa lahan parkir Anda dengan harga tetap tiap bulan. Anda menerima pendapatan pasti tanpa risiko fluktuasi jumlah kendaraan. Upgrade sistem berkala gratis." },
            technical: { title: "Technical Assistance", desc: "Kami bertindak sebagai konsultan teknologi dan sistem. SDM disediakan pemilik lahan, namun dilatih dan diawasi oleh standar sistem RITS Parking." },
            combination: { title: "Combination Fee", desc: "Bentuk kerjasama fleksibel yang menggabungkan elemen model lainnya (Misal: Guaranteed + Profit Sharing) untuk mengoptimalkan keuntungan kedua pihak." }
        };

        function showPage(pageId) {
            document.querySelectorAll('.page-section').forEach(sec => {
                sec.classList.remove('active');
                sec.style.display = 'none';
            });
            const target = document.getElementById(pageId);
            if (target) {
                target.style.display = 'block';
                setTimeout(() => target.classList.add('active'), 50);
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }
        }

        function toggleMenu() {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('open');
            document.body.style.overflow = menu.classList.contains('open') ? 'hidden' : 'auto';
        }

        function openModal(type) {
            document.getElementById('modalTitle').innerText = details[type].title;
            document.getElementById('modalContent').innerText = details[type].desc;
            document.getElementById('modalOverlay').classList.remove('hidden');
        }

        function closeModal() { document.getElementById('modalOverlay').classList.add('hidden'); }

        document.getElementById('menuBtn').onclick = toggleMenu;
        document.getElementById('closeBtn').onclick = toggleMenu;
        document.addEventListener('keydown', (e) => { if (e.key === "Escape") closeModal(); });

        window.onload = () => showPage('home');
    </script>
</body>

</html>
