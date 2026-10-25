<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>من محمد إلى أميرة قلبي ❤️ | من أول دقيقة</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Cairo & Tajawal & Amiri -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400&family=Cairo:wght@400;600;700;900&family=Tajawal:wght@400;500;700;800&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Canvas Confetti Library -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        roseGold: '#B76E79',
                        crimsonSoft: '#9E1B32',
                        romanticRed: '#E63946',
                        blush: '#FFB7C5',
                        goldGlow: '#FFD700'
                    },
                    fontFamily: {
                        cairo: ['Cairo', 'sans-serif'],
                        tajawal: ['Tajawal', 'sans-serif'],
                        amiri: ['Amiri', 'serif']
                    }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Tajawal', 'Cairo', sans-serif;
            background: linear-gradient(135deg, #180308 0%, #3a0816 35%, #5c0d23 70%, #1f0209 100%);
            background-attachment: fixed;
            color: #fff;
            overflow-x: hidden;
        }

        .font-amiri { font-family: 'Amiri', serif; }

        /* Glassmorphism Styling */
        .glass-card {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 183, 197, 0.25);
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.4);
        }

        .glass-card-glow {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(18px);
            border: 1px solid rgba(255, 105, 180, 0.4);
            box-shadow: 0 0 30px rgba(230, 57, 70, 0.35);
        }

        /* Animated Floating Balloons */
        .balloon-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 20;
            overflow: hidden;
        }

        .balloon {
            position: absolute;
            bottom: -130px;
            width: 65px;
            height: 80px;
            border-radius: 50% 50% 50% 50% / 40% 40% 60% 60%;
            pointer-events: auto;
            cursor: pointer;
            animation: floatUp 11s linear infinite;
            filter: drop-shadow(0 10px 15px rgba(0,0,0,0.4));
            transition: transform 0.2s ease;
        }

        .balloon:hover {
            transform: scale(1.2) rotate(6deg);
        }

        .balloon::after {
            content: "";
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            border-left: 6px solid transparent;
            border-right: 6px solid transparent;
            border-bottom: 9px solid inherit;
        }

        .balloon-string {
            position: absolute;
            bottom: -38px;
            left: 50%;
            width: 2px;
            height: 38px;
            background: rgba(255,255,255,0.6);
            transform: translateX(-50%);
        }

        @keyframes floatUp {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 0.95;
            }
            50% {
                transform: translateY(-50vh) rotate(10deg);
            }
            100% {
                transform: translateY(-115vh) rotate(-10deg);
                opacity: 0;
            }
        }

        /* Glow effects */
        .glow-text {
            text-shadow: 0 0 15px rgba(255, 182, 193, 0.8), 0 0 30px rgba(230, 57, 70, 0.6);
        }

        /* Pulse Heart Animation */
        @keyframes heartPulse {
            0% { transform: scale(1); }
            14% { transform: scale(1.18); }
            28% { transform: scale(1); }
            42% { transform: scale(1.18); }
            70% { transform: scale(1); }
        }

        .pulse-heart {
            animation: heartPulse 1.6s infinite;
        }

        /* Range Slider Styling */
        input[type=range] {
            -webkit-appearance: none;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 9999px;
            height: 6px;
        }
        input[type=range]::-webkit-slider-thumb {
            -webkit-appearance: none;
            height: 16px;
            width: 16px;
            border-radius: 50%;
            background: #ff4d6d;
            cursor: pointer;
            box-shadow: 0 0 10px rgba(255, 77, 109, 0.8);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #180308;
        }
        ::-webkit-scrollbar-thumb {
            background: #9E1B32;
            border-radius: 4px;
        }
    </style>
</head>
<body class="relative min-h-screen pb-16 selection:bg-roseGold selection:text-white">

    <!-- Canvas background for heart interactive particles -->
    <canvas id="bgCanvas" class="fixed inset-0 pointer-events-none z-0"></canvas>

    <!-- Floating Balloons Layer -->
    <div id="balloonLayer" class="balloon-container"></div>

    <!-- Main Audio Tag with MP3 Stream of "من أول دقيقة" -->
    <audio id="mainAudio" preload="metadata" loop>
        <!-- ضع ملف man_awel_daqiqa.mp3 في نفس مجلد ملف HTML -->
        <source src="man_awel_daqiqa.mp3" type="audio/mpeg">
        متصفحك لا يدعم تشغيل الصوتيات.
    </audio>

    <!-- Sticky Romantic Audio Player Header Container -->
    <div class="sticky top-4 z-50 px-4 max-w-3xl mx-auto my-3">
        <div class="glass-card-glow rounded-3xl p-4 shadow-2xl border border-pink-500/40">
            <div class="flex flex-col md:flex-row items-center justify-between gap-3">
                
                <!-- Song info & play toggle button -->
                <div class="flex items-center space-x-3 space-x-reverse w-full md:w-auto">
                    <button id="playPauseBtn" onclick="togglePlay()" class="w-13 h-13 min-w-[52px] rounded-full bg-gradient-to-r from-pink-500 via-rose-600 to-red-600 flex items-center justify-center text-white shadow-lg transition-transform hover:scale-110 active:scale-95 focus:outline-none border-2 border-pink-300">
                        <i id="playIcon" class="fas fa-play text-xl ml-0.5"></i>
                    </button>
                    <div>
                        <div class="flex items-center gap-2">
                            <span class="text-xs font-bold text-pink-300 bg-pink-950/60 px-2.5 py-0.5 rounded-full border border-pink-500/30">أغنيتنا الخاصة 🎵</span>
                            <span class="text-xs text-rose-200/70 font-amiri">محمد & أميرة</span>
                        </div>
                        <h3 class="text-base font-bold text-white mt-0.5">من أول دقيقة — إليسا & سعد لمجرد</h3>
                    </div>
                </div>

                <!-- Progress bar and Audio Control -->
                <div class="w-full md:w-72 flex flex-col gap-1">
                    <div class="flex items-center justify-between text-xs text-rose-200/80 font-mono">
                        <span id="currentTime">00:00</span>
                        <span id="durationTime">04:30</span>
                    </div>
                    <input type="range" id="seekSlider" value="0" min="0" max="100" class="w-full cursor-pointer" oninput="seekAudio()">
                </div>

                <!-- Volume and Mute Toggle -->
                <div class="hidden sm:flex items-center space-x-2 space-x-reverse">
                    <button onclick="toggleMute()" class="text-rose-200 hover:text-white transition-colors">
                        <i id="volumeIcon" class="fas fa-volume-up text-lg"></i>
                    </button>
                    <input type="range" id="volumeSlider" value="80" min="0" max="100" class="w-20 cursor-pointer" oninput="setVolume()">
                </div>

            </div>
        </div>
    </div>

    <!-- Main Page Content -->
    <main class="relative z-10 max-w-4xl mx-auto px-4 pt-4">

        <!-- Hero Header -->
        <header class="text-center my-8 relative">
            <div class="inline-block p-4 rounded-full bg-red-500/10 border border-red-500/30 mb-4 animate-bounce">
                <span class="text-4xl">👑</span>
            </div>
            
            <h1 class="text-4xl md:text-6xl font-extrabold font-cairo text-transparent bg-clip-text bg-gradient-to-r from-rose-200 via-pink-300 to-amber-200 glow-text mb-4 leading-tight">
                من محمد إلى أميرة قلبي ❤️
            </h1>
            
            <p class="text-xl md:text-2xl font-amiri text-rose-200 italic max-w-2xl mx-auto leading-relaxed">
                "بغير من عيني وأنا شايفك.. وده اللي وصلت ليه، من أول دقيقة لو أسمع اسمي بشفايفك بقولك كرريه"
            </p>

            <!-- Main Action Buttons -->
            <div class="mt-8 flex flex-wrap justify-center gap-4">
                <button onclick="popRandomLoveNote()" class="px-7 py-3 rounded-full bg-gradient-to-r from-pink-600 to-crimsonSoft hover:from-pink-500 hover:to-red-600 text-white font-bold text-base shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex items-center gap-2 border border-pink-400/30">
                    <i class="fas fa-balloon text-lg"></i>
                    فرقع بالونة الحب 🎈
                </button>
                <button onclick="openLetterModal()" class="px-7 py-3 rounded-full glass-card hover:bg-white/15 text-rose-100 font-bold text-base border border-rose-300/40 transition-all duration-300 transform hover:-translate-y-1 flex items-center gap-2">
                    <i class="fas fa-envelope-open-text text-lg text-rose-300"></i>
                    رسالة محمد السرية لأميرة ✉️
                </button>
            </div>
        </header>

        <!-- Big Hero Interactive Romantic Banner (Replaces Countdown) -->
        <section class="my-10">
            <div class="glass-card-glow rounded-3xl p-8 text-center relative overflow-hidden border border-pink-500/40 shadow-2xl">
                <div class="absolute -top-12 -right-12 w-48 h-48 bg-pink-600/20 rounded-full blur-3xl pointer-events-none"></div>
                <div class="absolute -bottom-12 -left-12 w-48 h-48 bg-rose-600/20 rounded-full blur-3xl pointer-events-none"></div>

                <div class="relative z-10">
                    <span class="inline-block px-4 py-1.5 rounded-full bg-pink-500/20 text-rose-200 border border-pink-400/30 text-xs font-bold mb-4">
                        حكاية حبنا الخالدة ✨
                    </span>
                    <h2 class="text-2xl md:text-4xl font-extrabold text-white mb-4 leading-snug">
                        "أميرة.. انتِ مش بس حبيبتي، انتِ كل دنيتي وحياتي"
                    </h2>
                    <p class="text-base md:text-lg font-amiri text-rose-200/90 max-w-xl mx-auto mb-6 leading-relaxed">
                        الموقع ده إهداء بسيط من حبيبك محمد عشان يفكرك دايماً إنك أغلى وأحلى حاجة حصلت في حياتي كلها، وإن حبي ليكي بيكبر مع كل دقيقة بتعدي!
                    </p>

                    <div class="flex justify-center items-center gap-4">
                        <button onclick="triggerConfetti()" class="px-6 py-2.5 rounded-full bg-gradient-to-r from-rose-500 to-pink-500 hover:opacity-90 text-white font-bold text-sm shadow-md transition-all">
                            احتفال بحب محمد وأميرة 🎉
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Dynamic Reasons Carousel / Love Cards -->
        <section class="my-14">
            <div class="text-center mb-8">
                <h2 class="text-2xl md:text-4xl font-bold text-rose-100">ليه محمد بيحب أميرة؟ ❤️</h2>
                <p class="text-sm text-rose-300/80 mt-2">قلبي في الكروت عشان تشوفي الأسباب يا أميرتي</p>
            </div>

            <div class="relative max-w-2xl mx-auto">
                <!-- Card -->
                <div id="quoteCard" class="glass-card-glow rounded-3xl p-8 md:p-10 text-center min-h-[240px] flex flex-col items-center justify-center transition-all duration-500 transform relative overflow-hidden">
                    <i class="fas fa-quote-right text-4xl text-rose-400/25 absolute top-4 right-6"></i>
                    <i class="fas fa-quote-left text-4xl text-rose-400/25 absolute bottom-4 left-6"></i>
                    
                    <p id="quoteText" class="text-xl md:text-2xl font-amiri leading-relaxed text-rose-100 font-bold px-6">
                        "ضحكتك بالنسبة لمحمد هي أجمل وأرق حاجة في الدنيا دي كلها."
                    </p>
                    <span id="quoteNumber" class="mt-6 inline-block text-xs font-bold text-pink-300 bg-pink-950/70 px-4 py-1.5 rounded-full border border-pink-500/40">
                        سبب 1 من 8
                    </span>
                </div>

                <!-- Navigation Controls -->
                <div class="flex justify-between items-center mt-6 px-4">
                    <button onclick="prevQuote()" class="w-12 h-12 rounded-full glass-card hover:bg-rose-600/40 flex items-center justify-center text-rose-200 transition-all text-lg shadow-lg">
                        <i class="fas fa-chevron-right"></i>
                    </button>
                    <button onclick="triggerConfetti()" class="px-5 py-2 rounded-full bg-pink-500/20 hover:bg-pink-500/30 border border-pink-500/40 text-xs font-bold text-rose-200 transition-all">
                        ارمي قلوب 💕
                    </button>
                    <button onclick="nextQuote()" class="w-12 h-12 rounded-full glass-card hover:bg-rose-600/40 flex items-center justify-center text-rose-200 transition-all text-lg shadow-lg">
                        <i class="fas fa-chevron-left"></i>
                    </button>
                </div>
            </div>
        </section>

        <!-- Interactive Love Meter & Wishes Section -->
        <section class="my-14 grid md:grid-cols-2 gap-6">
            
            <!-- Love Meter Card -->
            <div class="glass-card rounded-3xl p-6 md:p-8 text-center flex flex-col justify-between border border-pink-500/30 shadow-xl">
                <div>
                    <div class="w-14 h-14 rounded-2xl bg-pink-500/20 text-pink-300 flex items-center justify-center mx-auto mb-4 border border-pink-400/30">
                        <i class="fas fa-heart-pulse text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold text-rose-100 mb-1">مقياس حب محمد لأميرة</h3>
                    <p class="text-xs text-rose-300/80 mb-6">قيسي نسبة حب محمد ليكي النهاردة!</p>
                </div>

                <div class="my-4">
                    <div class="w-full bg-black/40 rounded-full h-6 p-1 border border-rose-500/40 overflow-hidden shadow-inner">
                        <div id="loveMeterBar" class="bg-gradient-to-r from-pink-500 via-rose-500 to-red-600 h-full rounded-full transition-all duration-1000 ease-out" style="width: 100%;"></div>
                    </div>
                    <span id="loveMeterText" class="block text-2xl font-bold text-pink-300 mt-3 font-mono">1000% (حب غير محدود)</span>
                </div>

                <button onclick="calculateLove()" class="w-full py-3 rounded-2xl bg-gradient-to-r from-rose-600 to-pink-600 hover:opacity-90 text-white font-bold text-sm shadow-lg transition-all mt-4">
                    إعادة قياس الحب 💖
                </button>
            </div>

            <!-- Wish Box Card -->
            <div class="glass-card rounded-3xl p-6 md:p-8 text-center flex flex-col justify-between border border-pink-500/30 shadow-xl">
                <div>
                    <div class="w-14 h-14 rounded-2xl bg-rose-500/20 text-rose-300 flex items-center justify-center mx-auto mb-4 border border-rose-400/30">
                        <i class="fas fa-magic text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold text-rose-100 mb-1">صندوق أمنيات أميرة</h3>
                    <p class="text-xs text-rose-300/80 mb-6">اكتبي أمنيتك ونفسك محمد ينفذها ليكي 🪄</p>
                </div>

                <div class="my-2">
                    <input type="text" id="wishInput" placeholder="اكتبي أي حاجة نفسك فيها يا أميرتي..." class="w-full px-5 py-3 rounded-2xl bg-black/40 border border-rose-500/40 text-white text-sm placeholder-rose-300/40 focus:outline-none focus:border-pink-400 transition-all text-center font-medium">
                </div>

                <button onclick="sendWish()" class="w-full py-3 rounded-2xl bg-gradient-to-r from-pink-600 to-purple-600 hover:opacity-90 text-white font-bold text-sm shadow-lg transition-all mt-4">
                    إرسال الأمنية لمحمد 💌
                </button>
            </div>

        </section>

        <!-- Interactive Big Love Button -->
        <section class="text-center my-16">
            <button id="mainLoveBtn" onclick="popHeartExplosion(event)" class="relative group px-10 py-6 rounded-full bg-gradient-to-r from-pink-600 via-rose-600 to-red-600 text-white font-extrabold text-xl md:text-2xl shadow-2xl transition-all duration-300 hover:scale-105 active:scale-95 border-2 border-rose-300/60">
                <span class="flex items-center gap-3">
                    <i class="fas fa-heart pulse-heart text-2xl text-rose-200"></i>
                    اضغطي هنا: محمد بيحبك يا أميرة!
                    <i class="fas fa-heart pulse-heart text-2xl text-rose-200"></i>
                </span>
            </button>
        </section>

        <!-- Footer -->
        <footer class="text-center py-8 border-t border-rose-500/20 text-sm text-rose-300/70 font-amiri">
            صُنِع بكل شَغَف وحُب من <span class="text-pink-300 font-bold">محمد</span> إلى <span class="text-pink-300 font-bold">أميرة</span> ❤️
        </footer>

    </main>

    <!-- Modal: Secret Love Letter -->
    <div id="letterModal" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/80 backdrop-blur-md opacity-0 pointer-events-none transition-all duration-300">
        <div class="glass-card-glow max-w-lg w-full rounded-3xl p-6 md:p-8 relative border border-rose-400/50 shadow-2xl transform scale-90 transition-all duration-300" id="letterContent">
            
            <button onclick="closeLetterModal()" class="absolute top-4 left-4 w-10 h-10 rounded-full bg-white/10 hover:bg-white/20 flex items-center justify-center text-rose-200">
                <i class="fas fa-times"></i>
            </button>

            <div class="text-center mb-6">
                <div class="w-16 h-16 rounded-full bg-pink-600/30 border border-pink-400/40 flex items-center justify-center mx-auto mb-3">
                    <i class="fas fa-heart text-3xl text-pink-400"></i>
                </div>
                <h3 class="text-2xl font-bold text-rose-100">جواب حب خاص من محمد لأميرة 📜</h3>
            </div>

            <div class="font-amiri text-lg text-rose-100/90 leading-relaxed space-y-4 max-h-[60vh] overflow-y-auto pl-2">
                <p>أميرتي الغالية والمفضلة دايماً.. ❤️</p>
                <p>
                    أول حاجة عايز أقولهالك إنك أجمل نِعمة ربنا رزقني بيها في دنيايا. وجودك جمبي بيخلي كل حاجة حلوة وبيدي كل حاجة معنى.
                </p>
                <p>
                    زي ما الأغنية بتقول بالضبط: "من أول دقيقة لو أسمع اسمي بشفايفك بقولك كرريه".. أنا فعلاً بحب كل تفصيلة فيكي، صوتك، طيبة قلبك، وضحكتك اللي بتنورلي الدنيا.
                </p>
                <p>
                    أوعدك إني هفضل جمبك وسند ليكي ودايماً هعمل كل اللي اقدر عليه عشان أشوف الضحكة دي على وشك.
                </p>
                <p class="text-left font-bold text-pink-300 pt-3">
                    ~ حبيبك للأبد: محمد 🌹
                </p>
            </div>

            <div class="mt-6 text-center">
                <button onclick="closeLetterModal()" class="px-8 py-2.5 rounded-full bg-gradient-to-r from-rose-600 to-pink-600 text-white font-bold text-sm">
                    إغلاق بحُب 💖
                </button>
            </div>
        </div>
    </div>

    <!-- Modal: Balloon Pop Love Note Popup -->
    <div id="balloonNoteModal" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/70 backdrop-blur-sm opacity-0 pointer-events-none transition-all duration-200">
        <div class="glass-card rounded-3xl p-6 text-center max-w-sm w-full border border-pink-400/40 transform scale-90 transition-all duration-200" id="balloonNoteContent">
            <div class="text-5xl mb-3 animate-bounce">🎈</div>
            <h4 class="text-lg font-bold text-rose-200 mb-2">رسالة بالونة الحب ✨</h4>
            <p id="balloonNoteText" class="text-lg font-amiri text-white font-bold mb-6">...</p>
            <button onclick="closeBalloonNote()" class="px-6 py-2.5 rounded-full bg-pink-600 hover:bg-pink-500 text-white text-xs font-bold shadow-md">
                بحبك يا محمد 🥰
            </button>
        </div>
    </div>

    <!-- Scripts Logic -->
    <script>
        // --- 1. Audio Player Logic for "من أول دقيقة" ---
        const audio = document.getElementById('mainAudio');
        const playPauseBtn = document.getElementById('playPauseBtn');
        const playIcon = document.getElementById('playIcon');
        const seekSlider = document.getElementById('seekSlider');
        const currentTimeEl = document.getElementById('currentTime');
        const durationTimeEl = document.getElementById('durationTime');
        const volumeSlider = document.getElementById('volumeSlider');
        const volumeIcon = document.getElementById('volumeIcon');

        let isPlaying = false;

        function togglePlay() {
            if (isPlaying) {
                audio.pause();
                playIcon.className = 'fas fa-play text-xl ml-0.5';
                isPlaying = false;
            } else {
                audio.play().then(() => {
                    playIcon.className = 'fas fa-pause text-xl';
                    isPlaying = true;
                }).catch(err => {
                    console.log("Autoplay restriction prevented audio start:", err);
                });
            }
        }

        audio.addEventListener('timeupdate', () => {
            if (audio.duration) {
                const progress = (audio.currentTime / audio.duration) * 100;
                seekSlider.value = progress;
                currentTimeEl.textContent = formatTime(audio.currentTime);
                durationTimeEl.textContent = formatTime(audio.duration);
            }
        });

        function seekAudio() {
            if (audio.duration) {
                const seekTo = (seekSlider.value / 100) * audio.duration;
                audio.currentTime = seekTo;
            }
        }

        function setVolume() {
            audio.volume = volumeSlider.value / 100;
            if (audio.volume === 0) {
                volumeIcon.className = 'fas fa-volume-mute text-lg';
            } else {
                volumeIcon.className = 'fas fa-volume-up text-lg';
            }
        }

        function toggleMute() {
            if (audio.volume > 0) {
                audio.volume = 0;
                volumeSlider.value = 0;
                volumeIcon.className = 'fas fa-volume-mute text-lg';
            } else {
                audio.volume = 0.8;
                volumeSlider.value = 80;
                volumeIcon.className = 'fas fa-volume-up text-lg';
            }
        }

        function formatTime(seconds) {
            const min = Math.floor(seconds / 60);
            const sec = Math.floor(seconds % 60);
            return `${min < 10 ? '0' : ''}${min}:${sec < 10 ? '0' : ''}${sec}`;
        }

        // Auto-play attempt on user click anywhere on body first time
        document.body.addEventListener('click', function startOnFirstInteraction() {
            if (!isPlaying) {
                togglePlay();
            }
            document.body.removeEventListener('click', startOnFirstInteraction);
        }, { once: true });


        // --- 2. Floating Balloons Logic ---
        const balloonLayer = document.getElementById('balloonLayer');
        const balloonColors = ['#ff4d6d', '#ff758f', '#c77dff', '#e63946', '#ffb7c5', '#b76e79', '#ffd1dc'];

        const loveNotes = [
            "ضحكتك بالدنيا كلها يا أميرة ❤️",
            "أجمل حاجة حصلت لمحمد في حياته ✨",
            "ربنا يديمك ليا يا أحلى وأرق أميرة 🌹",
            "محمد بيحبك أكتر من أي حاجة في الكون! 💕",
            "انتي سر السعادة والبهجة في أيامي 🌟",
            "كل يوم معاكي هو بداية لحلم جميل 🌸",
            "عيونك يا أميرة فيها كل الأمان والجمال 🥰",
            "من أول دقيقة ومحمد بيعشق تفاصيلك 💖"
        ];

        function createBalloon() {
            const balloon = document.createElement('div');
            balloon.className = 'balloon';
            
            const randomColor = balloonColors[Math.floor(Math.random() * balloonColors.length)];
            balloon.style.backgroundColor = randomColor;
            balloon.style.left = Math.random() * 85 + 5 + 'vw';
            balloon.style.animationDuration = (Math.random() * 5 + 7) + 's';

            const string = document.createElement('div');
            string.className = 'balloon-string';
            balloon.appendChild(string);

            balloon.addEventListener('click', (e) => {
                e.stopPropagation();
                popSoundEffect();
                showBalloonNote(loveNotes[Math.floor(Math.random() * loveNotes.length)]);
                balloon.remove();
                createBalloon();
            });

            balloonLayer.appendChild(balloon);

            setTimeout(() => {
                if (balloon.parentNode) {
                    balloon.remove();
                    createBalloon();
                }
            }, 12000);
        }

        for (let i = 0; i < 8; i++) {
            setTimeout(createBalloon, i * 1200);
        }

        // Sound effect on balloon click
        function popSoundEffect() {
            try {
                const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();
                osc.frequency.setValueAtTime(450, audioCtx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(90, audioCtx.currentTime + 0.1);
                gain.gain.setValueAtTime(0.3, audioCtx.currentTime);
                gain.gain.linearRampToValueAtTime(0.01, audioCtx.currentTime + 0.1);
                osc.connect(gain);
                gain.connect(audioCtx.destination);
                osc.start();
                osc.stop(audioCtx.currentTime + 0.1);
            } catch(e) {}
        }

        function showBalloonNote(text) {
            const modal = document.getElementById('balloonNoteModal');
            const modalContent = document.getElementById('balloonNoteContent');
            document.getElementById('balloonNoteText').textContent = text;
            
            modal.classList.remove('opacity-0', 'pointer-events-none');
            modalContent.classList.remove('scale-90');
            modalContent.classList.add('scale-100');

            confetti({
                particleCount: 35,
                spread: 70,
                origin: { y: 0.6 }
            });
        }

        function closeBalloonNote() {
            const modal = document.getElementById('balloonNoteModal');
            const modalContent = document.getElementById('balloonNoteContent');
            modal.classList.add('opacity-0', 'pointer-events-none');
            modalContent.classList.remove('scale-100');
            modalContent.classList.add('scale-90');
        }

        function popRandomLoveNote() {
            showBalloonNote(loveNotes[Math.floor(Math.random() * loveNotes.length)]);
        }


        // --- 3. Reasons Carousel ---
        const quotes = [
            "ضحكتك بالنسبة لمحمد هي أجمل وأرق حاجة في الدنيا دي كلها. 😊",
            "طيبة قلبك ورقتك بتخليني أحبك كل يوم أكتر من اليوم اللي قبله. 💖",
            "وجودك معايا بيطمني وبيخليني أحس إن الدنيا لسه فيها جمال وخير. 🌸",
            "أميرة مش مجرد اسم، انتِ فعلاً أميرة عُريش قلبي. 👑",
            "كل تفصيلة فيكي من كلامك لملامحك بتخطف قلبي من جديد. 🌹",
            "معاكي بحس إن الزمن بيقف ومش محتاج أي حاجة تانية غيرك. ⏳",
            "حبك هو الصدفة الحلوة اللي غيّرت حياتي لأحلى وأجمل أيام. ❤️",
            "من أول دقيقة شفتك فيها وعرفت إنك انتِ الشخص المناسب لقلبي. ✨"
        ];

        let currentQuote = 0;

        function updateQuote() {
            const quoteText = document.getElementById('quoteText');
            const quoteNumber = document.getElementById('quoteNumber');
            const card = document.getElementById('quoteCard');

            card.style.opacity = '0';
            card.style.transform = 'scale(0.95)';

            setTimeout(() => {
                quoteText.textContent = `"${quotes[currentQuote]}"`;
                quoteNumber.textContent = `سبب ${currentQuote + 1} من ${quotes.length}`;
                card.style.opacity = '1';
                card.style.transform = 'scale(1)';
            }, 250);
        }

        function nextQuote() {
            currentQuote = (currentQuote + 1) % quotes.length;
            updateQuote();
        }

        function prevQuote() {
            currentQuote = (currentQuote - 1 + quotes.length) % quotes.length;
            updateQuote();
        }


        // --- 4. Interactive Meter & Wish Box ---
        function calculateLove() {
            const bar = document.getElementById('loveMeterBar');
            const text = document.getElementById('loveMeterText');
            
            bar.style.width = '0%';
            text.textContent = 'جاري الحساب... 💓';

            setTimeout(() => {
                const percentage = Math.floor(Math.random() * 200) + 950;
                bar.style.width = '100%';
                text.textContent = `${percentage}% (حب محمد لأميرة فوق الخيال! ∞)`;
                triggerConfetti();
            }, 750);
        }

        function sendWish() {
            const wish = document.getElementById('wishInput').value.trim();
            if (!wish) {
                alert('اكتبي أمنية الأول يا أميرتي 🌹');
                return;
            }
            alert(`وصلت أمنيتك يا أميرة: "${wish}" ✨\nمحمد بيوعدك إنه هيحققها ليكي قريب جداً! ❤️`);
            document.getElementById('wishInput').value = '';
            triggerConfetti();
        }


        // --- 5. Letter Modals & Confetti ---
        function openLetterModal() {
            const modal = document.getElementById('letterModal');
            const content = document.getElementById('letterContent');
            modal.classList.remove('opacity-0', 'pointer-events-none');
            content.classList.remove('scale-90');
            content.classList.add('scale-100');
            triggerConfetti();
        }

        function closeLetterModal() {
            const modal = document.getElementById('letterModal');
            const content = document.getElementById('letterContent');
            modal.classList.add('opacity-0', 'pointer-events-none');
            content.classList.remove('scale-100');
            content.classList.add('scale-90');
        }

        function triggerConfetti() {
            confetti({
                particleCount: 75,
                spread: 85,
                origin: { y: 0.6 },
                colors: ['#ff4d6d', '#ff758f', '#ffffff', '#ffd700']
            });
        }

        function popHeartExplosion(e) {
            triggerConfetti();
            
            for (let i = 0; i < 12; i++) {
                const heart = document.createElement('div');
                heart.innerHTML = '❤️';
                heart.className = 'fixed text-2xl pointer-events-none z-50 transition-all duration-1000 ease-out';
                heart.style.left = (e.clientX + (Math.random() * 100 - 50)) + 'px';
                heart.style.top = (e.clientY + (Math.random() * 100 - 50)) + 'px';
                heart.style.opacity = '1';
                heart.style.transform = 'scale(1)';

                document.body.appendChild(heart);

                setTimeout(() => {
                    heart.style.transform = `translate(${(Math.random() - 0.5) * 200}px, -160px) scale(0)`;
                    heart.style.opacity = '0';
                }, 50);

                setTimeout(() => heart.remove(), 1050);
            }
        }

        // Background Hearts Canvas
        const canvas = document.getElementById('bgCanvas');
        const ctx = canvas.getContext('2d');
        let particles = [];

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = canvas.height + Math.random() * 100;
                this.size = Math.random() * 12 + 6;
                this.speedY = Math.random() * 1.5 + 0.5;
                this.opacity = Math.random() * 0.5 + 0.2;
            }
            update() {
                this.y -= this.speedY;
                if (this.y < -20) {
                    this.y = canvas.height + 20;
                    this.x = Math.random() * canvas.width;
                }
            }
            draw() {
                ctx.fillStyle = `rgba(255, 182, 193, ${this.opacity})`;
                ctx.font = `${this.size}px serif`;
                ctx.fillText('♥', this.x, this.y);
            }
        }

        for (let i = 0; i < 25; i++) {
            particles.push(new Particle());
        }

        function animateCanvas() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                p.update();
                p.draw();
            });
            requestAnimationFrame(animateCanvas);
        }

        window.onload = function() {
            animateCanvas();
        };
    </script>
</body>
</html>
