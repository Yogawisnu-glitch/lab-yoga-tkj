```html
<!DOCTYPE html>
<html lang="id" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lab Yoga Wisnu TKJ - Modul Simulasi CLI Ping & Packet Traceroute</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        mono: ['JetBrains Mono', 'monospace'],
                    },
                    colors: {
                        cyber: {
                            bg: '#070b14',
                            panel: '#0f172a',
                            border: '#1e293b',
                            accent: '#06b6d4', // cyan
                            success: '#10b981', // emerald
                            danger: '#ef4444', // red
                            warning: '#f59e0b' // amber
                        }
                    },
                    animation: {
                        'pulse-fast': 'pulse 1s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                    }
                }
            }
        }
    </script>
    <style>
        /* Custom Scrollbar untuk Terminal dan Log */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #070b14;
        }
        ::-webkit-scrollbar-thumb {
            background: #1e293b;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #334155;
        }

        /* Efek Glowing untuk Node Aktif */
        .node-active-req {
            filter: drop-shadow(0 0 12px rgba(6, 182, 212, 0.85));
            border-color: #06b6d4 !important;
        }
        .node-active-rep {
            filter: drop-shadow(0 0 12px rgba(16, 185, 129, 0.85));
            border-color: #10b981 !important;
        }
        .node-error {
            filter: drop-shadow(0 0 12px rgba(239, 68, 68, 0.85));
            border-color: #ef4444 !important;
        }

        /* Animasi Garis Putus-putus Jaringan */
        @keyframes dashFlow {
            to {
                stroke-dashoffset: -24;
            }
        }
        .link-active {
            stroke-dasharray: 6, 6;
            animation: dashFlow 0.8s linear infinite;
        }

        /* Efek Explosion / Ping Loss */
        @keyframes pingBurst {
            0% { transform: scale(0.5); opacity: 1; }
            100% { transform: scale(2.2); opacity: 0; }
        }
        .burst-anim {
            transform-origin: center;
            animation: pingBurst 0.6s ease-out forwards;
        }
    </style>
</head>
<body class="bg-cyber-bg text-slate-200 font-sans min-h-screen flex flex-col selection:bg-cyan-500/30 selection:text-cyan-200">

    <!-- HEADER APLIKASI -->
    <header class="bg-cyber-panel/90 backdrop-blur-md border-b border-cyber-border px-4 py-3 sticky top-0 z-30 shadow-lg">
        <div class="max-w-[1600px] mx-auto flex flex-col lg:flex-row lg:items-center lg:justify-between gap-3">
            
            <!-- Brand & Judul -->
            <div class="flex items-center gap-3">
                <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-cyan-500 to-blue-600 flex items-center justify-center shadow-lg shadow-cyan-500/20 shrink-0">
                    <!-- Icon Network Terminal SVG -->
                    <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 9l3 3-3 3m5 0h3M5 20h14a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"></path>
                    </svg>
                </div>
                <div>
                    <div class="flex items-center gap-2">
                        <h1 class="text-base sm:text-lg font-bold tracking-tight text-white">Lab Yoga Wisnu TKJ</h1>
                        <span class="px-2 py-0.5 text-[10px] font-mono font-semibold uppercase tracking-wider bg-cyan-500/10 text-cyan-400 border border-cyan-500/30 rounded-full">v2.4 NetSim</span>
                    </div>
                    <p class="text-xs text-slate-400">Modul Simulasi CLI Ping & Packet Traceroute (3-Hop Topology)</p>
                </div>
            </div>

            <!-- Preset IP & Kontrol Cepat -->
            <div class="flex flex-wrap items-center gap-2">
                <span class="text-xs font-medium text-slate-400 mr-1 hidden sm:inline">Preset Uji:</span>
                
                <button onclick="runPreset('ping', '8.8.8.8')" class="px-2.5 py-1.5 text-xs font-mono bg-slate-800/80 hover:bg-cyan-950/80 text-cyan-300 border border-slate-700 hover:border-cyan-500/50 rounded-lg transition flex items-center gap-1.5" title="Ping ke Server Google DNS">
                    <span class="w-2 h-2 rounded-full bg-emerald-400"></span>
                    8.8.8.8 <span class="text-slate-400 font-sans hidden md:inline">[Server]</span>
                </button>

                <button onclick="runPreset('ping', '192.168.1.1')" class="px-2.5 py-1.5 text-xs font-mono bg-slate-800/80 hover:bg-cyan-950/80 text-cyan-300 border border-slate-700 hover:border-cyan-500/50 rounded-lg transition flex items-center gap-1.5" title="Ping ke Router Gateway">
                    <span class="w-2 h-2 rounded-full bg-emerald-400"></span>
                    192.168.1.1 <span class="text-slate-400 font-sans hidden md:inline">[Router]</span>
                </button>

                <button onclick="runPreset('ping', '192.168.1.254')" class="px-2.5 py-1.5 text-xs font-mono bg-slate-800/80 hover:bg-cyan-950/80 text-cyan-300 border border-slate-700 hover:border-cyan-500/50 rounded-lg transition flex items-center gap-1.5" title="Ping ke Switch Lokal">
                    <span class="w-2 h-2 rounded-full bg-emerald-400"></span>
                    192.168.1.254 <span class="text-slate-400 font-sans hidden md:inline">[Switch]</span>
                </button>

                <button onclick="runPreset('ping', '10.10.10.99')" class="px-2.5 py-1.5 text-xs font-mono bg-slate-800/80 hover:bg-red-950/60 text-rose-300 border border-slate-700 hover:border-rose-500/50 rounded-lg transition flex items-center gap-1.5" title="Uji Host Tidak Dikenal / RTO">
                    <span class="w-2 h-2 rounded-full bg-rose-500"></span>
                    10.10.10.99 <span class="text-slate-400 font-sans hidden md:inline">[RTO]</span>
                </button>

                <button onclick="runPreset('tracert', '8.8.8.8')" class="px-2.5 py-1.5 text-xs font-mono bg-indigo-950/70 hover:bg-indigo-900/80 text-indigo-300 border border-indigo-700/50 hover:border-indigo-400 rounded-lg transition flex items-center gap-1.5" title="Lacak Rute ke 8.8.8.8">
                    <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6"></path></svg>
                    Tracert 8.8.8.8
                </button>

                <div class="h-5 w-[1px] bg-slate-700 mx-0.5 hidden sm:block"></div>

                <button onclick="resetAll()" class="px-3 py-1.5 text-xs font-medium bg-rose-500/10 hover:bg-rose-500/20 text-rose-400 border border-rose-500/30 rounded-lg transition flex items-center gap-1.5">
                    <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15"></path></svg>
                    Reset
                </button>
            </div>
        </div>
    </header>

    <!-- MAIN 3-PANEL WORKSPACE -->
    <main class="flex-1 max-w-[1600px] w-full mx-auto p-3 sm:p-4 grid grid-cols-1 lg:grid-cols-12 gap-4 items-stretch">

        <!-- ============================================================== -->
        <!-- PANEL KIRI: TERMINAL CLI INTERAKTIF (4 Kolom di Desktop)       -->
        <!-- ============================================================== -->
        <section class="lg:col-span-4 bg-cyber-panel border border-cyber-border rounded-2xl flex flex-col overflow-hidden shadow-xl min-h-[420px] lg:h-[calc(100vh-105px)]">
            <!-- Header Terminal -->
            <div class="bg-slate-900/90 border-b border-cyber-border px-4 py-2.5 flex items-center justify-between">
                <div class="flex items-center gap-2">
                    <div class="flex gap-1.5">
                        <span class="w-3 h-3 rounded-full bg-rose-500/80"></span>
                        <span class="w-3 h-3 rounded-full bg-amber-500/80"></span>
                        <span class="w-3 h-3 rounded-full bg-emerald-500/80"></span>
                    </div>
                    <span class="text-xs font-mono text-slate-400 ml-2">bash — yoga-tkj@client</span>
                </div>
                <span id="cli-status-badge" class="text-[10px] font-mono px-2 py-0.5 rounded bg-slate-800 text-slate-400">READY</span>
            </div>

            <!-- Area Output Terminal -->
            <div id="terminal-output" onclick="document.getElementById('cli-input').focus()" class="flex-1 p-4 font-mono text-xs sm:text-[13px] leading-relaxed overflow-y-auto bg-[#05080f] text-slate-300 space-y-1.5 cursor-text">
                <div class="text-cyan-400 font-bold">==================================================</div>
                <div class="text-white font-semibold">  SISTEM OPERASI LAB JARINGAN - SMK TKJ v2.4</div>
                <div class="text-slate-400">  Host: PC-Client-01 (IP: 192.168.1.10/24)</div>
                <div class="text-cyan-400 font-bold">==================================================</div>
                <div class="text-slate-400 pt-1">Ketik <span class="text-amber-400 font-semibold">help</span> untuk melihat daftar perintah yang tersedia.</div>
                <div class="text-slate-400 pb-2">Contoh: <span class="text-emerald-400">ping 8.8.8.8</span> atau <span class="text-emerald-400">tracert 8.8.8.8</span></div>
            </div>

            <!-- Baris Input Perintah -->
            <div class="bg-[#080d1a] border-t border-cyber-border p-3 flex items-center gap-2 font-mono text-xs sm:text-[13px]">
                <span class="text-emerald-400 font-semibold shrink-0 select-none">yoga-tkj@client:~$</span>
                <input 
                    type="text" 
                    id="cli-input" 
                    autocomplete="off" 
                    spellcheck="false"
                    placeholder="Ketik perintah (misal: ping 8.8.8.8)..."
                    class="w-full bg-transparent text-white focus:outline-none placeholder-slate-600 caret-cyan-400"
                >
                <button onclick="handleCommandSubmit()" class="px-2.5 py-1 bg-cyan-600 hover:bg-cyan-500 text-white text-xs font-sans font-medium rounded-lg transition shrink-0">
                    Run
                </button>
            </div>
        </section>

        <!-- ============================================================== -->
        <!-- PANEL TENGAH: VISUALISASI TOPOLOGI 3-HOP (5 Kolom di Desktop)  -->
        <!-- ============================================================== -->
        <section class="lg:col-span-5 bg-cyber-panel border border-cyber-border rounded-2xl flex flex-col justify-between overflow-hidden shadow-xl min-h-[460px] lg:h-[calc(100vh-105px)]">
            <!-- Header Topologi -->
            <div class="bg-slate-900/90 border-b border-cyber-border px-4 py-2.5 flex items-center justify-between">
                <div class="flex items-center gap-2">
                    <svg class="w-4 h-4 text-cyan-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"></path></svg>
                    <h2 class="text-xs sm:text-sm font-semibold text-white">Topologi Jaringan (3-Hop Architecture)</h2>
                </div>
                <div class="flex items-center gap-3 text-[11px]">
                    <span class="flex items-center gap-1 text-cyan-400"><span class="w-2.5 h-2.5 rounded-full bg-cyan-400 inline-block shadow shadow-cyan-400"></span> Request</span>
                    <span class="flex items-center gap-1 text-emerald-400"><span class="w-2.5 h-2.5 rounded-full bg-emerald-400 inline-block shadow shadow-emerald-400"></span> Reply</span>
                </div>
            </div>

            <!-- Kanvas Visualisasi Interaktif -->
            <div class="relative flex-1 flex flex-col items-center justify-center p-4 bg-[radial-gradient(#1e293b_1px,transparent_1px)] [background-size:20px_20px] overflow-hidden">
                
                <!-- Banner Info Paket Berjalan -->
                <div id="topology-banner" class="mb-4 px-3 py-1.5 rounded-full bg-slate-900/90 border border-slate-700/80 text-xs font-mono text-slate-300 flex items-center gap-2 shadow-md transition-all">
                    <span id="banner-dot" class="w-2 h-2 rounded-full bg-slate-500"></span>
                    <span id="banner-text">Menunggu instruksi transmisi paket...</span>
                </div>

                <!-- Container SVG & Nodes -->
                <div class="w-full max-w-[540px] relative my-auto">
                    <!-- SVG Layer untuk Jalur Kabel & Animasi Paket -->
                    <svg id="network-svg" viewBox="0 0 600 220" class="w-full h-auto overflow-visible select-none">
                        <defs>
                            <filter id="glow-cyan" x="-30%" y="-30%" width="160%" height="160%">
                                <feGaussianBlur stdDeviation="4" result="blur" />
                                <feComposite in="SourceGraphic" in2="blur" operator="over" />
                            </filter>
                            <filter id="glow-emerald" x="-30%" y="-30%" width="160%" height="160%">
                                <feGaussianBlur stdDeviation="4" result="blur" />
                                <feComposite in="SourceGraphic" in2="blur" operator="over" />
                            </filter>
                            <filter id="glow-red" x="-30%" y="-30%" width="160%" height="160%">
                                <feGaussianBlur stdDeviation="5" result="blur" />
                                <feComposite in="SourceGraphic" in2="blur" operator="over" />
                            </filter>
                        </defs>

                        <!-- JALUR KABEL (LINKS) -->
                        <!-- Link 0-1: Client -> Switch -->
                        <line id="link-0-1-bg" x1="75" y1="90" x2="225" y2="90" stroke="#1e293b" stroke-width="4" stroke-linecap="round" />
                        <line id="link-0-1" x1="75" y1="90" x2="225" y2="90" stroke="#334155" stroke-width="3" stroke-linecap="round" />
                        <text x="150" y="78" text-anchor="middle" fill="#64748b" font-size="10" font-family="JetBrains Mono">LAN UTP</text>
                        <g id="cut-0-1" class="hidden">
                            <circle cx="150" cy="90" r="11" fill="#450a0a" stroke="#ef4444" stroke-width="2"/>
                            <path d="M145 85 L155 95 M155 85 L145 95" stroke="#ef4444" stroke-width="2.5" stroke-linecap="round"/>
                        </g>

                        <!-- Link 1-2: Switch -> Router -->
                        <line id="link-1-2-bg" x1="225" y1="90" x2="375" y2="90" stroke="#1e293b" stroke-width="4" stroke-linecap="round" />
                        <line id="link-1-2" x1="225" y1="90" x2="375" y2="90" stroke="#334155" stroke-width="3" stroke-linecap="round" />
                        <text x="300" y="78" text-anchor="middle" fill="#64748b" font-size="10" font-family="JetBrains Mono">Trunk/Gw</text>
                        <g id="cut-1-2" class="hidden">
                            <circle cx="300" cy="90" r="11" fill="#450a0a" stroke="#ef4444" stroke-width="2"/>
                            <path d="M295 85 L305 95 M305 85 L295 95" stroke="#ef4444" stroke-width="2.5" stroke-linecap="round"/>
                        </g>

                        <!-- Link 2-3: Router -> Server -->
                        <line id="link-2-3-bg" x1="375" y1="90" x2="525" y2="90" stroke="#1e293b" stroke-width="4" stroke-linecap="round" />
                        <line id="link-2-3" x1="375" y1="90" x2="525" y2="90" stroke="#334155" stroke-width="3" stroke-linecap="round" />
                        <text x="450" y="78" text-anchor="middle" fill="#64748b" font-size="10" font-family="JetBrains Mono">WAN Fiber</text>
                        <g id="cut-2-3" class="hidden">
                            <circle cx="450" cy="90" r="11" fill="#450a0a" stroke="#ef4444" stroke-width="2"/>
                            <path d="M445 85 L455 95 M455 85 L445 95" stroke="#ef4444" stroke-width="2.5" stroke-linecap="round"/>
                        </g>

                        <!-- ============================================ -->
                        <!-- NODE 0: PC CLIENT (X: 75, Y: 90)             -->
                        <!-- ============================================ -->
                        <g id="node-0" transform="translate(75, 90)">
                            <rect id="box-0" x="-34" y="-34" width="68" height="68" rx="14" fill="#0f172a" stroke="#334155" stroke-width="2.5" class="transition-all duration-200"/>
                            <!-- Icon Monitor PC -->
                            <rect x="-16" y="-16" width="32" height="22" rx="3" fill="none" stroke="#38bdf8" stroke-width="2"/>
                            <path d="M-8 12 L8 12 M0 6 L0 12" stroke="#38bdf8" stroke-width="2" stroke-linecap="round"/>
                            <circle cx="0" cy="-5" r="2" fill="#38bdf8"/>
                            <!-- Label -->
                            <text x="0" y="50" text-anchor="middle" fill="#f8fafc" font-size="11" font-weight="700">PC Client</text>
                            <text x="0" y="64" text-anchor="middle" fill="#38bdf8" font-size="10" font-family="JetBrains Mono">192.168.1.10</text>
                            <text x="0" y="77" text-anchor="middle" fill="#64748b" font-size="9">Source (Node 0)</text>
                        </g>

                        <!-- ============================================ -->
                        <!-- NODE 1: SWITCH L2/L3 (X: 225, Y: 90)         -->
                        <!-- ============================================ -->
                        <g id="node-1" transform="translate(225, 90)">
                            <rect id="box-1" x="-34" y="-34" width="68" height="68" rx="14" fill="#0f172a" stroke="#334155" stroke-width="2.5" class="transition-all duration-200"/>
                            <!-- Icon Switch -->
                            <rect x="-18" y="-10" width="36" height="20" rx="3" fill="none" stroke="#a78bfa" stroke-width="2"/>
                            <path d="M-11 -3 L-4 -3 M4 -3 L11 -3 M-11 3 L-4 3 M4 3 L11 3" stroke="#a78bfa" stroke-width="2" stroke-linecap="round"/>
                            <!-- Label -->
                            <text x="0" y="50" text-anchor="middle" fill="#f8fafc" font-size="11" font-weight="700">Switch L2/L3</text>
                            <text x="0" y="64" text-anchor="middle" fill="#a78bfa" font-size="10" font-family="JetBrains Mono">192.168.1.254</text>
                            <text x="0" y="77" text-anchor="middle" fill="#64748b" font-size="9">Hop 1</text>
                        </g>

                        <!-- ============================================ -->
                        <!-- NODE 2: ROUTER GATEWAY (X: 375, Y: 90)       -->
                        <!-- ============================================ -->
                        <g id="node-2" transform="translate(375, 90)">
                            <rect id="box-2" x="-34" y="-34" width="68" height="68" rx="14" fill="#0f172a" stroke="#334155" stroke-width="2.5" class="transition-all duration-200"/>
                            <!-- Icon Router -->
                            <circle cx="0" cy="0" r="16" fill="none" stroke="#fbbf24" stroke-width="2"/>
                            <path d="M-7 -7 L7 7 M7 -7 L-7 7" stroke="#fbbf24" stroke-width="2" stroke-linecap="round"/>
                            <!-- Label -->
                            <text x="0" y="50" text-anchor="middle" fill="#f8fafc" font-size="11" font-weight="700">Router Gw</text>
                            <text x="0" y="64" text-anchor="middle" fill="#fbbf24" font-size="10" font-family="JetBrains Mono">192.168.1.1</text>
                            <text x="0" y="77" text-anchor="middle" fill="#64748b" font-size="9">Hop 2</text>
                        </g>

                        <!-- ============================================ -->
                        <!-- NODE 3: SERVER TUJUAN (X: 525, Y: 90)        -->
                        <!-- ============================================ -->
                        <g id="node-3" transform="translate(525, 90)">
                            <rect id="box-3" x="-34" y="-34" width="68" height="68" rx="14" fill="#0f172a" stroke="#334155" stroke-width="2.5" class="transition-all duration-200"/>
                            <!-- Icon Server Rack -->
                            <rect x="-14" y="-17" width="28" height="10" rx="2" fill="none" stroke="#34d399" stroke-width="2"/>
                            <rect x="-14" y="-4" width="28" height="10" rx="2" fill="none" stroke="#34d399" stroke-width="2"/>
                            <rect x="-14" y="9" width="28" height="8" rx="2" fill="none" stroke="#34d399" stroke-width="2"/>
                            <circle cx="-8" cy="-12" r="1.5" fill="#34d399"/>
                            <circle cx="-8" cy="1" r="1.5" fill="#34d399"/>
                            <!-- Label -->
                            <text x="0" y="50" text-anchor="middle" fill="#f8fafc" font-size="11" font-weight="700">Server DNS</text>
                            <text x="0" y="64" text-anchor="middle" fill="#34d399" font-size="10" font-family="JetBrains Mono">8.8.8.8</text>
                            <text x="0" y="77" text-anchor="middle" fill="#64748b" font-size="9">Hop 3 (Target)</text>
                        </g>

                        <!-- ============================================ -->
                        <!-- BOLA ANIMASI PAKET DATA                      -->
                        <!-- ============================================ -->
                        <g id="packet-orb" class="hidden" transform="translate(75, 90)">
                            <circle id="packet-halo" r="13" fill="#06b6d4" opacity="0.25" />
                            <circle id="packet-core" r="7" fill="#06b6d4" stroke="#ffffff" stroke-width="2" filter="url(#glow-cyan)" />
                            <text id="packet-label" x="0" y="-16" text-anchor="middle" fill="#22d3ee" font-size="9" font-weight="bold" font-family="JetBrains Mono">ICMP</text>
                        </g>

                        <!-- EFEK ERROR / RTO DI LOKASI GAGAL -->
                        <g id="error-marker" class="hidden" transform="translate(300, 90)">
                            <circle id="error-ring" r="14" fill="none" stroke="#ef4444" stroke-width="2.5" />
                            <path d="M-8 -8 L8 8 M8 -8 L-8 8" stroke="#ef4444" stroke-width="3.5" stroke-linecap="round" filter="url(#glow-red)"/>
                            <text x="0" y="-18" text-anchor="middle" fill="#f87171" font-size="10" font-weight="bold" font-family="JetBrains Mono">TIMEOUT!</text>
                        </g>
                    </svg>
                </div>

                <!-- Legenda Singkat Bawah Kanvas -->
                <div class="mt-2 text-[11px] text-slate-400 text-center max-w-md">
                    Paket bergerak dari <span class="text-slate-200 font-medium">Client</span> melewati <span class="text-slate-200 font-medium">Switch (Hop 1)</span> &amp; <span class="text-slate-200 font-medium">Router (Hop 2)</span> menuju <span class="text-slate-200 font-medium">Server (Hop 3)</span>.
                </div>
            </div>

            <!-- Panel Simulasi Gangguan Jaringan (Troubleshooting Lab) -->
            <div class="bg-slate-900/95 border-t border-cyber-border p-3.5">
                <div class="flex items-center justify-between mb-2.5">
                    <span class="text-xs font-semibold text-amber-400 flex items-center gap-1.5">
                        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"></path></svg>
                        Simulasi Gangguan Kabel / Perangkat (Lab Troubleshooting)
                    </span>
                    <span class="text-[10px] text-slate-400">Klik untuk putus/sambung</span>
                </div>
                
                <div class="grid grid-cols-3 gap-2">
                    <!-- Toggle Switch -->
                    <button id="fault-btn-1" onclick="toggleFault(1)" class="p-2 rounded-xl border border-slate-700 bg-slate-800/60 hover:bg-slate-800 transition flex flex-col items-center gap-1 text-center">
                        <div class="flex items-center gap-1.5">
                            <span id="fault-dot-1" class="w-2 h-2 rounded-full bg-emerald-400"></span>
                            <span class="text-xs font-semibold text-slate-200">Hop 1: Switch</span>
                        </div>
                        <span id="fault-text-1" class="text-[10px] font-mono text-emerald-400">ONLINE</span>
                    </button>

                    <!-- Toggle Router -->
                    <button id="fault-btn-2" onclick="toggleFault(2)" class="p-2 rounded-xl border border-slate-700 bg-slate-800/60 hover:bg-slate-800 transition flex flex-col items-center gap-1 text-center">
                        <div class="flex items-center gap-1.5">
                            <span id="fault-dot-2" class="w-2 h-2 rounded-full bg-emerald-400"></span>
                            <span class="text-xs font-semibold text-slate-200">Hop 2: Router</span>
                        </div>
                        <span id="fault-text-2" class="text-[10px] font-mono text-emerald-400">ONLINE</span>
                    </button>

                    <!-- Toggle Server -->
                    <button id="fault-btn-3" onclick="toggleFault(3)" class="p-2 rounded-xl border border-slate-700 bg-slate-800/60 hover:bg-slate-800 transition flex flex-col items-center gap-1 text-center">
                        <div class="flex items-center gap-1.5">
                            <span id="fault-dot-3" class="w-2 h-2 rounded-full bg-emerald-400"></span>
                            <span class="text-xs font-semibold text-slate-200">Hop 3: Server</span>
                        </div>
                        <span id="fault-text-3" class="text-[10px] font-mono text-emerald-400">ONLINE</span>
                    </button>
                </div>
            </div>
        </section>

        <!-- ============================================================== -->
        <!-- PANEL KANAN: LOG RESPON ICMP & STATISTIK (3 Kolom di Desktop)  -->
        <!-- ============================================================== -->
        <section class="lg:col-span-3 bg-cyber-panel border border-cyber-border rounded-2xl flex flex-col overflow-hidden shadow-xl min-h-[420px] lg:h-[calc(100vh-105px)]">
            <!-- Header Log -->
            <div class="bg-slate-900/90 border-b border-cyber-border px-4 py-2.5 flex items-center justify-between">
                <div class="flex items-center gap-2">
                    <svg class="w-4 h-4 text-emerald-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 17v-2m3 2v-4m3 4v-6m2 10H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"></path></svg>
                    <h2 class="text-xs sm:text-sm font-semibold text-white">Inspeksi Paket ICMP</h2>
                </div>
                <button onclick="clearLogs()" class="text-[11px] text-slate-400 hover:text-white transition">Bersihkan</button>
            </div>

            <!-- Kartu Status Koneksi Real-time -->
            <div class="p-3 border-b border-cyber-border bg-slate-900/40">
                <div id="status-card" class="p-3 rounded-xl border border-slate-700/80 bg-slate-800/50 flex items-center justify-between transition-all">
                    <div>
                        <div class="text-[10px] uppercase tracking-wider text-slate-400 font-semibold">Status Jalur Saat Ini</div>
                        <div id="conn-status-title" class="text-sm font-bold text-slate-200 mt-0.5">IDLE / STANDBY</div>
                        <div id="conn-status-desc" class="text-[11px] text-slate-400 mt-0.5">Siap mengirim paket ICMP</div>
                    </div>
                    <div id="conn-status-icon" class="w-10 h-10 rounded-xl bg-slate-700/50 flex items-center justify-center text-slate-400 shrink-0">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path></svg>
                    </div>
                </div>
            </div>

            <!-- Daftar Log Paket Terstruktur -->
            <div class="flex-1 overflow-y-auto p-3 space-y-2" id="icmp-log-container">
                <div id="empty-log-msg" class="h-full flex flex-col items-center justify-center text-center p-4 text-slate-500">
                    <svg class="w-8 h-8 mb-2 opacity-40" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"></path></svg>
                    <p class="text-xs">Belum ada log paket ICMP.<br>Jalankan perintah <span class="font-mono text-cyan-400">ping</span> atau <span class="font-mono text-cyan-400">tracert</span>.</p>
                </div>
            </div>

            <!-- Ringkasan Statistik Otomatis -->
            <div class="bg-slate-900/95 border-t border-cyber-border p-3">
                <div class="text-[11px] font-semibold text-slate-300 mb-2 flex items-center justify-between">
                    <span>Statistik Transmisi Sesi</span>
                    <span id="stat-target" class="font-mono text-[10px] text-cyan-400">-</span>
                </div>
                
                <!-- Grid Sent / Received / Loss -->
                <div class="grid grid-cols-3 gap-1.5 mb-2 text-center">
                    <div class="bg-slate-800/70 border border-slate-700/60 rounded-lg p-1.5">
                        <div class="text-[10px] text-slate-400">Sent</div>
                        <div id="stat-sent" class="text-sm font-mono font-bold text-white">0</div>
                    </div>
                    <div class="bg-slate-800/70 border border-slate-700/60 rounded-lg p-1.5">
                        <div class="text-[10px] text-slate-400">Received</div>
                        <div id="stat-recv" class="text-sm font-mono font-bold text-emerald-400">0</div>
                    </div>
                    <div class="bg-slate-800/70 border border-slate-700/60 rounded-lg p-1.5">
                        <div class="text-[10px] text-slate-400">Loss</div>
                        <div id="stat-loss" class="text-sm font-mono font-bold text-rose-400">0%</div>
                    </div>
                </div>

                <!-- Grid Min / Avg / Max RTT -->
                <div class="grid grid-cols-3 gap-1.5 text-center">
                    <div class="bg-slate-950/60 border border-slate-800 rounded-lg p-1.5">
                        <div class="text-[9px] text-slate-500 uppercase">Min RTT</div>
                        <div id="stat-min" class="text-xs font-mono font-semibold text-cyan-300">- ms</div>
                    </div>
                    <div class="bg-slate-950/60 border border-slate-800 rounded-lg p-1.5">
                        <div class="text-[9px] text-slate-500 uppercase">Avg RTT</div>
                        <div id="stat-avg" class="text-xs font-mono font-semibold text-cyan-300">- ms</div>
                    </div>
                    <div class="bg-slate-950/60 border border-slate-800 rounded-lg p-1.5">
                        <div class="text-[9px] text-slate-500 uppercase">Max RTT</div>
                        <div id="stat-max" class="text-xs font-mono font-semibold text-cyan-300">- ms</div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- SCRIPT LOGIKA SIMULASI JARINGAN -->
    <script>
        // =========================================================================
        // 1. KONFIGURASI TOPOLOGI & STATE GLOBAL
        // =========================================================================
        const NODES = [
            { id: 0, name: 'PC Client', ip: '192.168.1.10', x: 75, y: 90, baseRtt: 0, ttl: 128 },
            { id: 1, name: 'Switch L2/L3', ip: '192.168.1.254', x: 225, y: 90, baseRtt: 2, ttl: 255 },
            { id: 2, name: 'Router Gateway', ip: '192.168.1.1', x: 375, y: 90, baseRtt: 8, ttl: 64 },
            { id: 3, name: 'Server DNS', ip: '8.8.8.8', x: 525, y: 90, baseRtt: 24, ttl: 56 }
        ];

        // Status gangguan (false = normal/online, true = terputus/offline)
        const faults = {
            1: false, // Switch
            2: false, // Router
            3: false  // Server
        };

        let isRunning = false;
        let abortController = null;
        let commandHistory = [];
        let historyIndex = -1;

        // Statistik sesi saat ini
        let stats = {
            target: '-',
            sent: 0,
            recv: 0,
            rtts: []
        };

        // Elemen DOM Utama
        const terminalOutput = document.getElementById('terminal-output');
        const cliInput = document.getElementById('cli-input');
        const logContainer = document.getElementById('icmp-log-container');
        const packetOrb = document.getElementById('packet-orb');
        const packetCore = document.getElementById('packet-core');
        const packetHalo = document.getElementById('packet-halo');
        const packetLabel = document.getElementById('packet-label');
        const errorMarker = document.getElementById('error-marker');

        // =========================================================================
        // 2. EVENT LISTENER TERMINAL & KEYBOARD
        // =========================================================================
        cliInput.addEventListener('keydown', (e) => {
            if (e.key === 'Enter') {
                e.preventDefault();
                handleCommandSubmit();
            } else if (e.key === 'ArrowUp') {
                e.preventDefault();
                if (commandHistory.length > 0 && historyIndex < commandHistory.length - 1) {
                    historyIndex++;
                    cliInput.value = commandHistory[commandHistory.length - 1 - historyIndex];
                }
            } else if (e.key === 'ArrowDown') {
                e.preventDefault();
                if (historyIndex > 0) {
                    historyIndex--;
                    cliInput.value = commandHistory[commandHistory.length - 1 - historyIndex];
                } else {
                    historyIndex = -1;
                    cliInput.value = '';
                }
            }
        });

        // Fungsi menjalankan perintah dari tombol preset di header
        function runPreset(cmd, ip) {
            if (isRunning) {
                stopCurrentSimulation();
            }
            setTimeout(() => {
                cliInput.value = `${cmd} ${ip}`;
                handleCommandSubmit();
            }, 100);
        }

        // Fungsi utama memproses input perintah CLI
        function handleCommandSubmit() {
            const rawCmd = cliInput.value.trim();
            if (!rawCmd) return;

            // Simpan ke riwayat perintah
            commandHistory.push(rawCmd);
            historyIndex = -1;
            cliInput.value = '';

            // Cetak prompt dan perintah ke terminal
            printTerminal(`<span class="text-emerald-400 font-semibold">yoga-tkj@client:~$</span> <span class="text-white">${escapeHtml(rawCmd)}</span>`);

            if (isRunning) {
                printTerminal(`<span class="text-amber-400">[!] Proses jaringan masih berjalan. Tunggu selesai atau klik Reset.</span>`);
                return;
            }

            const parts = rawCmd.toLowerCase().split(/\s+/);
            const command = parts[0];
            const arg = parts[1];

            switch (command) {
                case 'help':
                    showHelp();
                    break;
                case 'cls':
                case 'clear':
                    terminalOutput.innerHTML = '';
                    break;
                case 'ipconfig':
                case 'ifconfig':
                    showIpConfig();
                    break;
                case 'ping':
                    if (!arg) {
                        printTerminal(`<span class="text-rose-400">Error: Alamat IP tujuan harus disertakan. Contoh: ping 8.8.8.8</span>`);
                    } else if (!isValidIPv4(arg)) {
                        printTerminal(`<span class="text-rose-400">Ping request could not find host '${escapeHtml(arg)}'. Format IPv4 tidak valid.</span>`);
                    } else {
                        executePing(arg);
                    }
                    break;
                case 'tracert':
                case 'traceroute':
                    if (!arg) {
                        printTerminal(`<span class="text-rose-400">Error: Alamat IP tujuan harus disertakan. Contoh: tracert 8.8.8.8</span>`);
                    } else if (!isValidIPv4(arg)) {
                        printTerminal(`<span class="text-rose-400">Unable to resolve target system name '${escapeHtml(arg)}'. Format IPv4 tidak valid.</span>`);
                    } else {
                        executeTracert(arg);
                    }
                    break;
                default:
                    printTerminal(`<span class="text-rose-400">'${escapeHtml(command)}' tidak dikenali sebagai perintah internal maupun eksternal.</span>`);
                    printTerminal(`<span class="text-slate-400">Ketik <span class="text-amber-400">help</span> untuk bantuan.</span>`);
            }
        }

        // =========================================================================
        // 3. PERINTAH INFORMASI (HELP & IPCONFIG)
        // =========================================================================
        function showHelp() {
            const helpText = `
<div class="my-1 p-2.5 rounded-lg bg-slate-900/90 border border-slate-800 space-y-1 text-xs">
  <div class="text-cyan-400 font-bold mb-1">DAFTAR PERINTAH LAB YOGA WISNU TKJ:</div>
  <div><span class="text-emerald-400 font-semibold w-32 inline-block">ping [ip]</span> : Mengirim 4 paket ICMP Echo Request ke IP tujuan</div>
  <div><span class="text-emerald-400 font-semibold w-32 inline-block">tracert [ip]</span> : Melacak rute hop-by-hop (TTL 1..3) ke tujuan</div>
  <div><span class="text-emerald-400 font-semibold w-32 inline-block">ipconfig</span> : Menampilkan konfigurasi IP lokal PC Client</div>
  <div><span class="text-emerald-400 font-semibold w-32 inline-block">cls / clear</span> : Membersihkan layar terminal</div>
  <div class="pt-1 text-slate-400 border-t border-slate-800/80 mt-1">
    <span class="text-amber-400">Daftar IP Lab:</span> 192.168.1.10 (Client) | 192.168.1.254 (Switch) | 192.168.1.1 (Router) | 8.8.8.8 (Server)
  </div>
</div>`;
            printTerminal(helpText);
        }

        function showIpConfig() {
            const info = `
<div class="my-1 pl-2 border-l-2 border-cyan-500 text-xs space-y-0.5 text-slate-300">
  <div class="text-white font-semibold">Ethernet adapter Local Area Connection:</div>
  <div>   Connection-specific DNS Suffix  . : lab.yogawisnu.tkj</div>
  <div>   IPv4 Address. . . . . . . . . . . : <span class="text-cyan-400">192.168.1.10</span></div>
  <div>   Subnet Mask . . . . . . . . . . . : 255.255.255.0</div>
  <div>   Default Gateway . . . . . . . . . : <span class="text-amber-400">192.168.1.1</span></div>
  <div>   DNS Server  . . . . . . . . . . . : <span class="text-emerald-400">8.8.8.8</span></div>
</div>`;
            printTerminal(info);
        }

        // =========================================================================
        // 4. LOGIKA ROUTING & PENENTUAN JALUR PAKET
        // =========================================================================
        function evaluateTarget(targetIp) {
            // Cek apakah IP adalah salah satu perangkat di topologi kita
            const matchedNode = NODES.find(n => n.ip === targetIp);
            
            if (!matchedNode) {
                // IP tidak dikenal di lab (misal 10.10.10.99) -> paket berjalan sampai Router lalu RTO
                // Namun jika Switch/Router putus lebih dulu, gagal di titik putus tersebut
                if (faults[1]) return { reachNode: 0, failNode: 1, success: false, reason: 'RTO_AT_SWITCH' };
                if (faults[2]) return { reachNode: 1, failNode: 2, success: false, reason: 'RTO_AT_ROUTER' };
                return { reachNode: 2, failNode: 3, success: false, reason: 'RTO_UNKNOWN_HOST' };
            }

            // Jika target adalah PC Client sendiri (192.168.1.10)
            if (matchedNode.id === 0) {
                return { reachNode: 0, failNode: null, success: true, targetNode: matchedNode, reason: 'LOCALHOST' };
            }

            // Cek apakah ada perangkat yang dimatikan (fault) di sepanjang jalur menuju matchedNode
            for (let hop = 1; hop <= matchedNode.id; hop++) {
                if (faults[hop]) {
                    return {
                        reachNode: hop - 1,
                        failNode: hop,
                        success: false,
                        targetNode: matchedNode,
                        reason: `LINK_DOWN_HOP_${hop}`
                    };
                }
            }

            // Jalur bersih menuju target!
            return {
                reachNode: matchedNode.id,
                failNode: null,
                success: true,
                targetNode: matchedNode,
                reason: 'CONNECTED'
            };
        }

        // =========================================================================
        // 5. SIMULASI PERINTAH PING (4 PAKET ICMP ECHO)
        // =========================================================================
        async function executePing(targetIp) {
            isRunning = true;
            abortController = new AbortController();
            const signal = abortController.signal;

            setCliStatus('RUNNING', 'bg-cyan-500/20 text-cyan-300 border border-cyan-500/40');
            resetStats(targetIp);
            clearLogs();

            printTerminal(`<div class="text-slate-300 mt-1">Pinging <span class="text-white font-semibold">${targetIp}</span> with 32 bytes of data:</div>`);

            const routeInfo = evaluateTarget(targetIp);

            try {
                for (let seq = 1; seq <= 4; seq++) {
                    if (signal.aborted) return;

                    stats.sent++;
                    updateStatsUI();

                    // Update status kartu kanan
                    updateConnectionCard('SENDING', `Mengirim Paket #${seq}`, `ICMP Echo Request -> ${targetIp}`);
                    updateBanner('req', `Mengirim ICMP Echo Request #${seq} ke ${targetIp}...`);

                    // Kasus Khusus: Ping Localhost (192.168.1.10)
                    if (routeInfo.reason === 'LOCALHOST') {
                        highlightNode(0, 'rep');
                        await sleep(350, signal);
                        const rtt = 1;
                        stats.recv++;
                        stats.rtts.push(rtt);
                        updateStatsUI();
                        printTerminal(`<span class="text-emerald-400">Reply from 192.168.1.10: bytes=32 time&lt;1ms TTL=128</span>`);
                        addIcmpLog({
                            seq: `Seq #${seq}`,
                            ip: '192.168.1.10',
                            proto: 'ICMP Echo Reply (Loopback)',
                            ttl: 128,
                            rtt: '<1 ms',
                            status: 'SUCCESS'
                        });
                        highlightNode(0, 'none');
                        await sleep(500, signal);
                        continue;
                    }

                    // 1. Animasi Paket Berangkat (Request) dari Node 0 sampai reachNode
                    await animateForwardPath(0, routeInfo.reachNode, 'ICMP REQ', signal);

                    if (routeInfo.success) {
                        // 2A. BERHASIL MENCAPAI TARGET
                        const targetNode = routeInfo.targetNode;
                        highlightNode(targetNode.id, 'rep');
                        updateConnectionCard('REPLY', `Menerima Balasan #${seq}`, `ICMP Echo Reply dari ${targetIp}`);
                        updateBanner('rep', `ICMP Echo Reply diterima dari ${targetIp}!`);

                        // Animasi Paket Kembali (Reply) dari targetNode ke Node 0
                        await animateBackwardPath(targetNode.id, 0, 'ICMP REP', signal);

                        // Hitung RTT realistis dengan sedikit variasi acak
                        const jitter = Math.floor(Math.random() * 5) - 2;
                        const rtt = Math.max(1, targetNode.baseRtt + jitter);
                        const ttl = targetNode.ttl;

                        stats.recv++;
                        stats.rtts.push(rtt);
                        updateStatsUI();

                        printTerminal(`<span class="text-emerald-400">Reply from ${targetIp}: bytes=32 time=${rtt}ms TTL=${ttl}</span>`);
                        addIcmpLog({
                            seq: `Seq #${seq}`,
                            ip: targetIp,
                            proto: 'ICMP Echo Reply',
                            ttl: ttl,
                            rtt: `${rtt} ms`,
                            status: 'SUCCESS'
                        });
                    } else {
                        // 2B. GAGAL / REQUEST TIMED OUT (RTO)
                        const failHop = routeInfo.failNode;
                        updateConnectionCard('TIMEOUT', `Request Timed Out (#${seq})`, `Paket terhenti di ${NODES[failHop].name}`);
                        updateBanner('err', `Paket #${seq} gagal! Timeout menuju ${NODES[failHop].name} (${NODES[failHop].ip})`);

                        await showTimeoutAtNode(routeInfo.reachNode, failHop, signal);
                        updateStatsUI();

                        printTerminal(`<span class="text-rose-400">Request timed out.</span>`);
                        addIcmpLog({
                            seq: `Seq #${seq}`,
                            ip: targetIp,
                            proto: 'ICMP Echo Request',
                            ttl: '-',
                            rtt: 'Timeout',
                            status: 'TIMEOUT'
                        });
                    }

                    resetVisualHighlights();
                    if (seq < 4) await sleep(550, signal);
                }

                // Tampilkan Ringkasan Ping di Terminal
                const lossCount = stats.sent - stats.recv;
                const lossPct = Math.round((lossCount / stats.sent) * 100);
                let summaryHtml = `
<div class="mt-2 pt-1.5 border-t border-slate-800/80 text-slate-300 text-xs">
  <div>Ping statistics for <span class="text-white font-semibold">${targetIp}</span>:</div>
  <div>    Packets: Sent = ${stats.sent}, Received = ${stats.recv}, Lost = ${lossCount} (<span class="${lossPct > 0 ? 'text-rose-400' : 'text-emerald-400'}">${lossPct}% loss</span>),</div>`;

                if (stats.rtts.length > 0) {
                    const min = Math.min(...stats.rtts);
                    const max = Math.max(...stats.rtts);
                    const avg = Math.round(stats.rtts.reduce((a, b) => a + b, 0) / stats.rtts.length);
                    summaryHtml += `
  <div>Approximate round trip times in milli-seconds:</div>
  <div>    Minimum = ${min}ms, Maximum = ${max}ms, Average = ${avg}ms</div>`;
                }
                summaryHtml += `</div>`;
                printTerminal(summaryHtml);

                // Update Status Akhir Kartu Kanan
                if (stats.recv === stats.sent) {
                    updateConnectionCard('CONNECTED', 'KONEKSI STABIL (100%)', `Semua paket ke ${targetIp} berhasil`);
                    updateBanner('rep', `Simulasi Ping ke ${targetIp} selesai — Koneksi Berhasil.`);
                } else if (stats.recv > 0) {
                    updateConnectionCard('WARNING', 'KONEKSI TIDAK STABIL', `${lossPct}% paket mengalami packet loss`);
                    updateBanner('err', `Simulasi selesai dengan ${lossPct}% packet loss.`);
                } else {
                    updateConnectionCard('FAILED', 'HOST UNREACHABLE / RTO', `100% paket gagal mencapai ${targetIp}`);
                    updateBanner('err', `Koneksi ke ${targetIp} gagal (100% Request Timed Out).`);
                }

            } catch (err) {
                if (err.name !== 'AbortError') console.error(err);
            } finally {
                isRunning = false;
                setCliStatus('READY', 'bg-slate-800 text-slate-400');
                hidePacketOrb();
            }
        }

        // =========================================================================
        // 6. SIMULASI PERINTAH TRACERT (3 HOP BERURUTAN DENGAN TTL INCREMENT)
        // =========================================================================
        async function executeTracert(targetIp) {
            isRunning = true;
            abortController = new AbortController();
            const signal = abortController.signal;

            setCliStatus('TRACING', 'bg-indigo-500/20 text-indigo-300 border border-indigo-500/40');
            resetStats(targetIp);
            clearLogs();

            printTerminal(`<div class="text-slate-300 mt-1">Tracing route to <span class="text-white font-semibold">${targetIp}</span> over a maximum of 30 hops:</div><div class="h-1"></div>`);

            const routeInfo = evaluateTarget(targetIp);
            // Tentukan berapa hop maksimal yang perlu ditelusuri
            let maxHopsToTrace = 3;
            if (routeInfo.targetNode && routeInfo.targetNode.id > 0) {
                maxHopsToTrace = routeInfo.targetNode.id;
            }

            try {
                for (let hop = 1; hop <= maxHopsToTrace; hop++) {
                    if (signal.aborted) return;

                    const hopNode = NODES[hop];
                    const isHopOnline = !faults[hop] && (hop <= routeInfo.reachNode);

                    stats.sent++;
                    updateStatsUI();

                    updateConnectionCard('SENDING', `Tracing Hop ${hop} (TTL=${hop})`, `Menguji perangkat ${hopNode.name}`);
                    updateBanner('req', `Tracert Hop ${hop}: Mengirim probe dengan TTL=${hop}...`);

                    if (isHopOnline) {
                        // Animasi maju sampai hop saat ini
                        await animateForwardPath(0, hop, `TTL=${hop}`, signal);
                        highlightNode(hop, 'rep');

                        // Animasi balik dari hop saat ini ke client
                        const isFinalDestination = (routeInfo.success && routeInfo.targetNode.id === hop);
                        const replyLabel = isFinalDestination ? 'ECHO REP' : 'TTL EXP';
                        await animateBackwardPath(hop, 0, replyLabel, signal);

                        // Hitung 3 sampel RTT ala perintah tracert Windows/Linux
                        const base = hopNode.baseRtt;
                        const r1 = Math.max(1, base + Math.floor(Math.random() * 3) - 1);
                        const r2 = Math.max(1, base + Math.floor(Math.random() * 3) - 1);
                        const r3 = Math.max(1, base + Math.floor(Math.random() * 3) - 1);
                        const avgRtt = Math.round((r1 + r2 + r3) / 3);

                        stats.recv++;
                        stats.rtts.push(avgRtt);
                        updateStatsUI();

                        const padHop = String(hop).padStart(2, ' ');
                        const padR1 = `${r1} ms`.padStart(6, ' ');
                        const padR2 = `${r2} ms`.padStart(6, ' ');
                        const padR3 = `${r3} ms`.padStart(6, ' ');

                        printTerminal(`<span class="text-cyan-300">${padHop}  ${padR1}  ${padR2}  ${padR3}  <span class="text-white font-semibold">${hopNode.ip}</span> <span class="text-slate-400">[${hopNode.name}]</span></span>`);

                        addIcmpLog({
                            seq: `Hop ${hop}`,
                            ip: hopNode.ip,
                            proto: isFinalDestination ? 'ICMP Echo Reply' : 'ICMP Time Exceeded',
                            ttl: hop,
                            rtt: `${avgRtt} ms`,
                            status: 'SUCCESS'
                        });

                        resetVisualHighlights();

                        // Jika sudah sampai tujuan akhir, hentikan loop
                        if (isFinalDestination) {
                            break;
                        }
                    } else {
                        // Hop ini mengalami gangguan / tidak merespon
                        const prevReachable = Math.max(0, hop - 1);
                        updateConnectionCard('TIMEOUT', `Hop ${hop} Timeout (*)`, `${hopNode.name} (${hopNode.ip}) tidak merespon`);
                        updateBanner('err', `Tracert terhenti di Hop ${hop} (${hopNode.name}) — Request Timed Out!`);

                        await showTimeoutAtNode(prevReachable, hop, signal);
                        updateStatsUI();

                        const padHop = String(hop).padStart(2, ' ');
                        printTerminal(`<span class="text-rose-400">${padHop}     *        *        *     Request timed out. (${hopNode.name} Unreachable)</span>`);

                        addIcmpLog({
                            seq: `Hop ${hop}`,
                            ip: hopNode.ip,
                            proto: `ICMP Probe (TTL=${hop})`,
                            ttl: hop,
                            rtt: '* * *',
                            status: 'TIMEOUT'
                        });

                        resetVisualHighlights();
                        break; // Hentikan tracert jika jalur terputus
                    }

                    await sleep(450, signal);
                }

                printTerminal(`<div class="text-slate-400 mt-2">Trace complete.</div>`);

                if (routeInfo.success) {
                    updateConnectionCard('CONNECTED', 'TRACE ROUTE SELESAI', `Jalur ke ${targetIp} terverifikasi (${maxHopsToTrace} Hop)`);
                    updateBanner('rep', `Pelacakan rute ke ${targetIp} selesai dengan sukses.`);
                } else {
                    updateConnectionCard('FAILED', 'JALUR TERPUTUS', `Paket gagal melewati Hop ${routeInfo.failNode}`);
                    updateBanner('err', `Pelacakan rute terhenti karena gangguan pada Hop ${routeInfo.failNode}.`);
                }

            } catch (err) {
                if (err.name !== 'AbortError') console.error(err);
            } finally {
                isRunning = false;
                setCliStatus('READY', 'bg-slate-800 text-slate-400');
                hidePacketOrb();
            }
        }

        // =========================================================================
        // 7. ENGINE ANIMASI SVG TOPOLOGI JARINGAN
        // =========================================================================
        async function animateForwardPath(startIdx, endIdx, labelText, signal) {
            errorMarker.classList.add('hidden');
            packetOrb.classList.remove('hidden');
            
            // Warna Biru/Cyan untuk Request
            packetCore.setAttribute('fill', '#06b6d4');
            packetCore.setAttribute('filter', 'url(#glow-cyan)');
            packetHalo.setAttribute('fill', '#06b6d4');
            packetLabel.setAttribute('fill', '#22d3ee');
            packetLabel.textContent = labelText;

            highlightNode(startIdx, 'req');

            for (let i = startIdx; i < endIdx; i++) {
                if (signal.aborted) return;
                const fromNode = NODES[i];
                const toNode = NODES[i + 1];
                const linkEl = document.getElementById(`link-${i}-${i+1}`);
                
                if (linkEl) {
                    linkEl.setAttribute('stroke', '#06b6d4');
                    linkEl.classList.add('link-active');
                }

                await moveOrb(fromNode.x, fromNode.y, toNode.x, toNode.y, 340, signal);

                if (linkEl) {
                    linkEl.setAttribute('stroke', '#334155');
                    linkEl.classList.remove('link-active');
                }
                highlightNode(i, 'none');
                highlightNode(i + 1, 'req');
            }
        }

        async function animateBackwardPath(startIdx, endIdx, labelText, signal) {
            packetOrb.classList.remove('hidden');
            
            // Warna Hijau/Emerald untuk Reply
            packetCore.setAttribute('fill', '#10b981');
            packetCore.setAttribute('filter', 'url(#glow-emerald)');
            packetHalo.setAttribute('fill', '#10b981');
            packetLabel.setAttribute('fill', '#34d399');
            packetLabel.textContent = labelText;

            highlightNode(startIdx, 'rep');

            for (let i = startIdx; i > endIdx; i--) {
                if (signal.aborted) return;
                const fromNode = NODES[i];
                const toNode = NODES[i - 1];
                const linkEl = document.getElementById(`link-${i-1}-${i}`);

                if (linkEl) {
                    linkEl.setAttribute('stroke', '#10b981');
                    linkEl.classList.add('link-active');
                }

                await moveOrb(fromNode.x, fromNode.y, toNode.x, toNode.y, 340, signal);

                if (linkEl) {
                    linkEl.setAttribute('stroke', '#334155');
                    linkEl.classList.remove('link-active');
                }
                highlightNode(i, 'none');
                highlightNode(i - 1, 'rep');
            }
        }

        async function showTimeoutAtNode(lastGoodIdx, failIdx, signal) {
            // Jika masih bisa jalan sampai lastGoodIdx, gerakkan dulu ke sana
            if (lastGoodIdx > 0) {
                await animateForwardPath(0, lastGoodIdx, 'ICMP REQ', signal);
            }

            const fromNode = NODES[lastGoodIdx];
            const failNode = NODES[failIdx];
            
            // Gerakkan setengah jalan menuju node yang rusak lalu meledak/timeout
            const midX = (fromNode.x + failNode.x) / 2;
            const midY = fromNode.y;

            packetOrb.classList.remove('hidden');
            packetCore.setAttribute('fill', '#06b6d4');
            packetLabel.textContent = 'ICMP REQ';

            await moveOrb(fromNode.x, fromNode.y, midX, midY, 260, signal);
            hidePacketOrb();

            // Tampilkan tanda silang merah di titik kegagalan
            highlightNode(failIdx, 'err');
            errorMarker.setAttribute('transform', `translate(${midX}, ${midY})`);
            errorMarker.classList.remove('hidden');
            
            const ring = document.getElementById('error-ring');
            ring.classList.remove('burst-anim');
            void ring.offsetWidth; // trigger reflow
            ring.classList.add('burst-anim');

            await sleep(650, signal);
            errorMarker.classList.add('hidden');
        }

        function moveOrb(x1, y1, x2, y2, duration, signal) {
            return new Promise((resolve, reject) => {
                const startTime = performance.now();

                function frame(now) {
                    if (signal.aborted) {
                        reject(new DOMException('Aborted', 'AbortError'));
                        return;
                    }
                    const elapsed = now - startTime;
                    const progress = Math.min(elapsed / duration, 1);
                    // Ease in-out cubic
                    const ease = progress < 0.5 
                        ? 2 * progress * progress 
                        : 1 - Math.pow(-2 * progress + 2, 2) / 2;

                    const currX = x1 + (x2 - x1) * ease;
                    const currY = y1 + (y2 - y1) * ease;
                    packetOrb.setAttribute('transform', `translate(${currX}, ${currY})`);

                    if (progress < 1) {
                        requestAnimationFrame(frame);
                    } else {
                        resolve();
                    }
                }
                requestAnimationFrame(frame);
            });
        }

        function hidePacketOrb() {
            packetOrb.classList.add('hidden');
        }

        function highlightNode(nodeId, state) {
            const box = document.getElementById(`box-${nodeId}`);
            if (!box) return;

            box.classList.remove('node-active-req', 'node-active-rep', 'node-error');
            box.setAttribute('stroke', faults[nodeId] ? '#ef4444' : '#334155');

            if (state === 'req') {
                box.classList.add('node-active-req');
                box.setAttribute('stroke', '#06b6d4');
            } else if (state === 'rep') {
                box.classList.add('node-active-rep');
                box.setAttribute('stroke', '#10b981');
            } else if (state === 'err') {
                box.classList.add('node-error');
                box.setAttribute('stroke', '#ef4444');
            }
        }

        function resetVisualHighlights() {
            for (let i = 0; i <= 3; i++) {
                highlightNode(i, 'none');
            }
            for (let i = 0; i < 3; i++) {
                const link = document.getElementById(`link-${i}-${i+1}`);
                if (link) {
                    link.classList.remove('link-active');
                    link.setAttribute('stroke', faults[i+1] ? '#7f1d1d' : '#334155');
                }
            }
        }

        // =========================================================================
        // 8. TOGGLE SIMULASI GANGGUAN JARINGAN (FAULT INJECTION)
        // =========================================================================
        function toggleFault(hopId) {
            faults[hopId] = !faults[hopId];
            const isDown = faults[hopId];

            const btn = document.getElementById(`fault-btn-${hopId}`);
            const dot = document.getElementById(`fault-dot-${hopId}`);
            const txt = document.getElementById(`fault-text-${hopId}`);
            const cutIcon = document.getElementById(`cut-${hopId-1}-${hopId}`);
            const linkLine = document.getElementById(`link-${hopId-1}-${hopId}`);
            const box = document.getElementById(`box-${hopId}`);

            if (isDown) {
                btn.classList.remove('border-slate-700', 'bg-slate-800/60');
                btn.classList.add('border-rose-500/60', 'bg-rose-950/40');
                dot.classList.remove('bg-emerald-400');
                dot.classList.add('bg-rose-500', 'animate-pulse');
                txt.textContent = 'OFFLINE / PUTUS';
                txt.classList.remove('text-emerald-400');
                txt.classList.add('text-rose-400');

                if (cutIcon) cutIcon.classList.remove('hidden');
                if (linkLine) linkLine.setAttribute('stroke', '#7f1d1d');
                if (box) box.setAttribute('stroke', '#ef4444');
            } else {
                btn.classList.add('border-slate-700', 'bg-slate-800/60');
                btn.classList.remove('border-rose-500/60', 'bg-rose-950/40');
                dot.classList.add('bg-emerald-400');
                dot.classList.remove('bg-rose-500', 'animate-pulse');
                txt.textContent = 'ONLINE';
                txt.classList.add('text-emerald-400');
                txt.classList.remove('text-rose-400');

                if (cutIcon) cutIcon.classList.add('hidden');
                if (linkLine) linkLine.setAttribute('stroke', '#334155');
                if (box) box.setAttribute('stroke', '#334155');
            }
        }

        // =========================================================================
        // 9. MANAJEMEN LOG PANEL KANAN & STATISTIK
        // =========================================================================
        function addIcmpLog({ seq, ip, proto, ttl, rtt, status }) {
            const emptyMsg = document.getElementById('empty-log-msg');
            if (emptyMsg) emptyMsg.remove();

            const isSuccess = status === 'SUCCESS';
            const borderClass = isSuccess ? 'border-emerald-500/30 bg-emerald-950/15' : 'border-rose-500/40 bg-rose-950/20';
            const badgeClass = isSuccess ? 'bg-emerald-500/20 text-emerald-400' : 'bg-rose-500/20 text-rose-400';

            const item = document.createElement('div');
            item.className = `p-2.5 rounded-xl border ${borderClass} text-xs transition-all`;
            item.innerHTML = `
                <div class="flex items-center justify-between mb-1">
                    <span class="font-mono font-bold text-white">${seq} <span class="text-slate-400 font-normal">→ ${ip}</span></span>
                    <span class="px-1.5 py-0.5 rounded text-[10px] font-mono font-semibold ${badgeClass}">${status}</span>
                </div>
                <div class="flex items-center justify-between text-[11px] text-slate-400 font-mono">
                    <span>${proto}</span>
                    <span>TTL:${ttl} | <strong class="${isSuccess ? 'text-cyan-300' : 'text-rose-400'}">${rtt}</strong></span>
                </div>
            `;
            logContainer.appendChild(item);
            logContainer.scrollTop = logContainer.scrollHeight;
        }

        function clearLogs() {
            logContainer.innerHTML = `
                <div id="empty-log-msg" class="h-full flex flex-col items-center justify-center text-center p-4 text-slate-500">
                    <svg class="w-8 h-8 mb-2 opacity-40" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"></path></svg>
                    <p class="text-xs">Belum ada log paket ICMP.<br>Jalankan perintah <span class="font-mono text-cyan-400">ping</span> atau <span class="font-mono text-cyan-400">tracert</span>.</p>
                </div>`;
        }

        function resetStats(target = '-') {
            stats = { target, sent: 0, recv: 0, rtts: [] };
            updateStatsUI();
        }

        function updateStatsUI() {
            document.getElementById('stat-target').textContent = stats.target;
            document.getElementById('stat-sent').textContent = stats.sent;
            document.getElementById('stat-recv').textContent = stats.recv;

            const lossPct = stats.sent === 0 ? 0 : Math.round(((stats.sent - stats.recv) / stats.sent) * 100);
            document.getElementById('stat-loss').textContent = `${lossPct}%`;

            if (stats.rtts.length > 0) {
                const min = Math.min(...stats.rtts);
                const max = Math.max(...stats.rtts);
                const avg = Math.round(stats.rtts.reduce((a, b) => a + b, 0) / stats.rtts.length);
                document.getElementById('stat-min').textContent = `${min} ms`;
                document.getElementById('stat-avg').textContent = `${avg} ms`;
                document.getElementById('stat-max').textContent = `${max} ms`;
            } else {
                document.getElementById('stat-min').textContent = '- ms';
                document.getElementById('stat-avg').textContent = '- ms';
                document.getElementById('stat-max').textContent = '- ms';
            }
        }

        function updateConnectionCard(type, title, desc) {
            const card = document.getElementById('status-card');
            const titleEl = document.getElementById('conn-status-title');
            const descEl = document.getElementById('conn-status-desc');
            const iconBox = document.getElementById('conn-status-icon');

            titleEl.textContent = title;
            descEl.textContent = desc;

            // Reset classes
            card.className = 'p-3 rounded-xl border flex items-center justify-between transition-all';
            iconBox.className = 'w-10 h-10 rounded-xl flex items-center justify-center shrink-0';

            if (type === 'SENDING') {
                card.classList.add('border-cyan-500/40', 'bg-cyan-950/20');
                titleEl.className = 'text-sm font-bold text-cyan-300 mt-0.5';
                iconBox.classList.add('bg-cyan-500/20', 'text-cyan-400', 'animate-pulse');
            } else if (type === 'REPLY' || type === 'CONNECTED') {
                card.classList.add('border-emerald-500/40', 'bg-emerald-950/20');
                titleEl.className = 'text-sm font-bold text-emerald-400 mt-0.5';
                iconBox.classList.add('bg-emerald-500/20', 'text-emerald-400');
            } else if (type === 'TIMEOUT' || type === 'FAILED') {
                card.classList.add('border-rose-500/40', 'bg-rose-950/20');
                titleEl.className = 'text-sm font-bold text-rose-400 mt-0.5';
                iconBox.classList.add('bg-rose-500/20', 'text-rose-400');
            } else if (type === 'WARNING') {
                card.classList.add('border-amber-500/40', 'bg-amber-950/20');
                titleEl.className = 'text-sm font-bold text-amber-400 mt-0.5';
                iconBox.classList.add('bg-amber-500/20', 'text-amber-400');
            } else {
                card.classList.add('border-slate-700/80', 'bg-slate-800/50');
                titleEl.className = 'text-sm font-bold text-slate-200 mt-0.5';
                iconBox.classList.add('bg-slate-700/50', 'text-slate-400');
            }
        }

        function updateBanner(mode, text) {
            const dot = document.getElementById('banner-dot');
            const txt = document.getElementById('banner-text');
            txt.textContent = text;

            dot.className = 'w-2 h-2 rounded-full';
            if (mode === 'req') dot.classList.add('bg-cyan-400', 'animate-ping');
            else if (mode === 'rep') dot.classList.add('bg-emerald-400');
            else if (mode === 'err') dot.classList.add('bg-rose-500');
            else dot.classList.add('bg-slate-500');
        }

        // =========================================================================
        // 10. FUNGSI UTILITAS & RESET GLOBAL
        // =========================================================================
        function printTerminal(html) {
            const line = document.createElement('div');
            line.innerHTML = html;
            terminalOutput.appendChild(line);
            terminalOutput.scrollTop = terminalOutput.scrollHeight;
        }

        function setCliStatus(text, classes) {
            const badge = document.getElementById('cli-status-badge');
            badge.textContent = text;
            badge.className = `text-[10px] font-mono px-2 py-0.5 rounded ${classes}`;
        }

        function isValidIPv4(ip) {
            const regex = /^(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}$/;
            return regex.test(ip);
        }

        function escapeHtml(str) {
            return str.replace(/[&<>"']/g, (m) => ({
                '&': '&amp;', '<': '&lt;', '>': '&gt;', '"': '&quot;', "'": '&#39;'
            }[m]));
        }

        function sleep(ms, signal) {
            return new Promise((resolve, reject) => {
                const timer = setTimeout(resolve, ms);
                if (signal) {
                    signal.addEventListener('abort', () => {
                        clearTimeout(timer);
                        reject(new DOMException('Aborted', 'AbortError'));
                    });
                }
            });
        }

        function stopCurrentSimulation() {
            if (abortController) {
                abortController.abort();
            }
            isRunning = false;
            hidePacketOrb();
            errorMarker.classList.add('hidden');
            resetVisualHighlights();
        }

        function resetAll() {
            stopCurrentSimulation();
            
            // Pulihkan semua gangguan perangkat jika aktif
            [1, 2, 3].forEach(hop => {
                if (faults[hop]) toggleFault(hop);
            });

            // Bersihkan terminal ke pesan awal
            terminalOutput.innerHTML = `
                <div class="text-cyan-400 font-bold">==================================================</div>
                <div class="text-white font-semibold">  SISTEM OPERASI LAB JARINGAN - SMK TKJ v2.4</div>
                <div class="text-slate-400">  Host: PC-Client-01 (IP: 192.168.1.10/24)</div>
                <div class="text-cyan-400 font-bold">==================================================</div>
                <div class="text-emerald-400 pt-1">[OK] Sistem dan topologi berhasil di-reset ke kondisi awal.</div>
            `;

            clearLogs();
            resetStats('-');
            updateConnectionCard('IDLE', 'IDLE / STANDBY', 'Siap mengirim paket ICMP');
            updateBanner('idle', 'Menunggu instruksi transmisi paket...');
            setCliStatus('READY', 'bg-slate-800 text-slate-400');
            cliInput.focus();
        }
    </script>
</body>
</html>
```
