# Learn-nahwu-
Pembelajaran nahwu berdasarkan kitab Al jurumiyyah 
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="theme-color" content="#1f7a4c">
    <title>Nahwu Jurumiyah Pro</title>
    <link rel="manifest" href="manifest.json">
    <link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!-- Login Screen -->
    <div id="loginScreen" class="screen active">
        <div class="login-container">
            <div class="logo-large">
                <span class="arabic-logo">ن</span>
                <h1>Nahwu Jurumiyah</h1>
                <p class="arabic-sub">متن الآجرومية</p>
            </div>
            
            <div class="login-form">
                <input type="text" id="username" placeholder="Nama Pengguna" class="input-field">
                <input type="password" id="password" placeholder="Kata Sandi" class="input-field">
                <button onclick="login()" class="btn-primary btn-full">Masuk</button>
                <button onclick="guestLogin()" class="btn-secondary btn-full">Masuk sebagai Tamu</button>
                <p class="text-center text-small mt-3">Belum punya akun? <a href="#" onclick="showRegister()">Daftar</a></p>
            </div>
            
            <div class="features-preview">
                <div class="feature-item">
                    <span>📚</span>
                    <small>9 Bab Lengkap</small>
                </div>
                <div class="feature-item">
                    <span>🎵</span>
                    <small>Audio Pembelajaran</small>
                </div>
                <div class="feature-item">
                    <span>✅</span>
                    <small>Quiz Interaktif</small>
                </div>
            </div>
        </div>
    </div>

    <!-- Register Screen -->
    <div id="registerScreen" class="screen">
        <div class="login-container">
            <div class="logo-large">
                <span class="arabic-logo">ن</span>
                <h1>Daftar Akun</h1>
            </div>
            
            <div class="login-form">
                <input type="text" id="regName" placeholder="Nama Lengkap" class="input-field">
                <input type="text" id="regUsername" placeholder="Nama Pengguna" class="input-field">
                <input type="email" id="regEmail" placeholder="Email" class="input-field">
                <input type="password" id="regPassword" placeholder="Kata Sandi" class="input-field">
                <button onclick="register()" class="btn-primary btn-full">Daftar</button>
                <button onclick="showLogin()" class="btn-secondary btn-full">Kembali ke Login</button>
            </div>
        </div>
    </div>

    <!-- Main App -->
    <div id="mainApp" class="screen">
        <!-- Header -->
        <header class="app-header">
            <div class="header-content">
                <div class="logo-small">
                    <span class="arabic-logo-small">ن</span>
                    <div>
                        <h2>Nahwu Pro</h2>
                        <p class="user-name" id="displayName">Santri</p>
                    </div>
                </div>
                <div class="header-actions">
                    <button onclick="toggleSettings()" class="icon-btn">⚙️</button>
                    <button onclick="logout()" class="icon-btn">🚪</button>
                </div>
            </div>
            
            <!-- XP Bar -->
            <div class="xp-container">
                <div class="xp-info">
                    <span>Level <span id="userLevel">1</span></span>
                    <span><span id="userXP">0</span> XP</span>
                </div>
                <div class="xp-bar">
                    <div class="xp-fill" id="xpFill" style="width: 0%"></div>
                </div>
            </div>
        </header>

        <!-- Navigation -->
        <nav class="main-nav">
            <button onclick="showSection('materi')" class="nav-btn active" data-section="materi">
                <span class="nav-icon">📖</span>
                <span>Materi</span>
            </button>
            <button onclick="showSection('kitab')" class="nav-btn" data-section="kitab">
                <span class="nav-icon">📜</span>
                <span>Kitab</span>
            </button>
            <button onclick="showSection('quiz')" class="nav-btn" data-section="quiz">
                <span class="nav-icon">✏️</span>
                <span>Quiz</span>
            </button>
            <button onclick="showSection('kamus')" class="nav-btn" data-section="kamus">
                <span class="nav-icon">📚</span>
                <span>Kamus</span>
            </button>
            <button onclick="showSection('irab')" class="nav-btn" data-section="irab">
                <span class="nav-icon">🔍</span>
                <span>I'rab</span>
            </button>
        </nav>

        <!-- Content Sections -->
        <main class="content-area">
            <!-- Materi Section -->
            <section id="materi" class="content-section active">
                <div class="section-header">
                    <h3>📖 Materi Pembelajaran</h3>
                    <p>Pelajari 9 bab kitab Jurumiyah</p>
                </div>
                
                <div class="bab-list" id="babList">
                    <!-- Generated by JS -->
                </div>
            </section>

            <!-- Kitab Section (Teks Asli) -->
            <section id="kitab" class="content-section">
                <div class="section-header">
                    <h3>📜 Kitab Jurumiyah</h3>
                    <p>Teks asli matan dengan terjemah</p>
                </div>
                
                <div class="kitab-controls">
                    <button onclick="changeKitabView('arab')" class="btn-small active" id="btnArab">Arab</button>
                    <button onclick="changeKitabView('latin')" class="btn-small" id="btnLatin">Latin</button>
                    <button onclick="changeKitabView('dual')" class="btn-small" id="btnDual">Dual</button>
                    <button onclick="playKitabAudio()" class="btn-small btn-audio">🔊 Baca</button>
                </div>
                
                <div class="kitab-content" id="kitabContent">
                    <!-- Generated by JS -->
                </div>
            </section>

            <!-- Quiz Section -->
            <section id="quiz" class="content-section">
                <div class="section-header">
                    <h3>✏️ Latihan Soal</h3>
                    <p>Uji pemahaman Anda per bab</p>
                </div>
                
                <div class="quiz-selection" id="quizSelection">
                    <!-- Generated by JS -->
                </div>
                
                <div class="quiz-container hidden" id="quizContainer">
                    <div class="quiz-progress">
                        <span id="quizCounter">1/10</span>
                        <div class="progress-bar"><div id="quizProgressFill"></div></div>
                    </div>
                    <div class="quiz-question" id="quizQuestion"></div>
                    <div class="quiz-options" id="quizOptions"></div>
                    <div class="quiz-feedback hidden" id="quizFeedback"></div>
                </div>
                
                <div class="quiz-result hidden" id="quizResult">
                    <div class="result-icon">🏆</div>
                    <h3>Quiz Selesai!</h3>
                    <p class="result-score">Skor: <span id="finalScore">0</span>/10</p>
                    <p id="resultMessage"></p>
                    <button onclick="backToQuizSelection()" class="btn-primary">Kembali</button>
                </div>
            </section>

            <!-- Kamus Section -->
            <section id="kamus" class="content-section">
                <div class="section-header">
                    <h3>📚 Kamus Istilah</h3>
                    <p>Istilah-istilah nahwu dan sharaf</p>
                </div>
                
                <div class="search-box">
                    <input type="text" id="kamusSearch" placeholder="Cari istilah..." onkeyup="searchKamus()">
                    <span>🔍</span>
                </div>
                
                <div class="kamus-list" id="kamusList">
                    <!-- Generated by JS -->
                </div>
            </section>

            <!-- I'rab Section -->
            <section id="irab" class="content-section">
                <div class="section-header">
                    <h3>🔍 Analisis I'rab</h3>
                    <p>Analisis gramatikal kalimat Arab</p>
                </div>
                
                <div class="irab-input-container">
                    <textarea id="irabInput" rows="3" placeholder="Masukkan kalimat Arab dengan harakat..." dir="rtl" class="arabic-input"></textarea>
                    <div class="irab-actions">
                        <button onclick="clearIrab()" class="btn-secondary">Hapus</button>
                        <button onclick="insertSample()" class="btn-secondary">Contoh</button>
                        <button onclick="analyzeIrab()" class="btn-primary">🔍 Analisis</button>
                    </div>
                </div>
                
                <div class="irab-result hidden" id="irabResult">
                    <h4>Hasil Analisis:</h4>
                    <div id="irabAnalysis"></div>
                </div>
                
                <div class="irab-guide">
                    <h4>📖 Panduan I'rab</h4>
                    <div class="guide-grid">
                        <div class="guide-item rafa"><strong>Marfu'</strong> - Dhommah (ُ)</div>
                        <div class="guide-item nasab"><strong>Mansub</strong> - Fathah (َ)</div>
                        <div class="guide-item jarr"><strong>Majrur</strong> - Kasrah (ِ)</div>
                        <div class="guide-item jazm"><strong>Majzum</strong> - Sukun (ْ)</div>
                    </div>
                </div>
            </section>
        </main>

        <!-- Settings Modal -->
        <div id="settingsModal" class="modal hidden">
            <div class="modal-content">
                <div class="modal-header">
                    <h3>⚙️ Pengaturan</h3>
                    <button onclick="toggleSettings()" class="close-btn">✕</button>
                </div>
                
                <div class="settings-list">
                    <div class="setting-item">
                        <span>🔊 Audio Pembelajaran</span>
                        <label class="switch">
                            <input type="checkbox" id="audioToggle" checked onchange="toggleAudio()">
                            <span class="slider"></span>
                        </label>
                    </div>
                    
                    <div class="setting-item">
                        <span>🌙 Mode Gelap</span>
                        <label class="switch">
                            <input type="checkbox" id="darkToggle" onchange="toggleDarkMode()">
                            <span class="slider"></span>
                        </label>
                    </div>
                    
                    <div class="setting-item">
                        <span>🔔 Notifikasi</span>
                        <label class="switch">
                            <input type="checkbox" id="notifToggle" checked>
                            <span class="slider"></span>
                        </label>
                    </div>
                    
                    <div class="setting-item">
                        <span>📝 Tampilan Latin</span>
                        <label class="switch">
                            <input type="checkbox" id="latinToggle" onchange="toggleLatin()">
                            <span class="slider"></span>
                        </label>
                    </div>
                    
                    <div class="setting-item info">
                        <span>📱 Versi Aplikasi</span>
                        <span class="version">v2.0.0</span>
                    </div>
                    
                    <button onclick="resetProgress()" class="btn-danger btn-full mt-3">🗑️ Reset Progress</button>
                </div>
            </div>
        </div>

        <!-- Materi Detail Modal -->
        <div id="materiModal" class="modal hidden">
            <div class="modal-content modal-large">
                <div class="modal-header sticky">
                    <button onclick="closeMateriModal()" class="back-btn">← Kembali</button>
                    <button onclick="playMateriAudio()" class="audio-btn" id="materiAudioBtn">🔊</button>
                </div>
                <div id="materiDetailContent"></div>
            </div>
        </div>

        <!-- Toast Notification -->
        <div id="toast" class="toast hidden"></div>
    </div>

    <script src="app.js"></script>
</body>
</html>
/* ==========================================
   ROOT VARIABLES & RESET
   ========================================== */
:root {
    --primary: #1f7a4c;
    --primary-dark: #145c36;
    --primary-light: #2d9c64;
    --secondary: #f59e0b;
    --danger: #dc2626;
    --bg: #eef2ef;
    --card: #ffffff;
    --text: #1f2937;
    --text-light: #6b7280;
    --border: #d1d5db;
    --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.dark {
    --bg: #111827;
    --card: #1f2937;
    --text: #f9fafb;
    --text-light: #9ca3af;
    --border: #374151;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    -webkit-tap-highlight-color: transparent;
}

body {
    font-family: 'Inter', sans-serif;
    background: var(--bg);
    color: var(--text);
    line-height: 1.6;
    overflow-x: hidden;
}

/* ==========================================
   SCREENS & CONTAINERS
   ========================================== */
.screen {
    display: none;
    min-height: 100vh;
}

.screen.active {
    display: block;
}

/* ==========================================
   LOGIN SCREEN
   ========================================== */
.login-container {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 20px;
    background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
}

.logo-large {
    text-align: center;
    color: white;
    margin-bottom: 40px;
}

.arabic-logo {
    font-size: 80px;
    font-family: 'Amiri', serif;
    display: block;
    margin-bottom: 10px;
    text-shadow: 0 4px 10px rgba(0,0,0,0.3);
}

.logo-large h1 {
    font-size: 28px;
    margin-bottom: 5px;
}

.arabic-sub {
    font-family: 'Amiri', serif;
    font-size: 18px;
    opacity: 0.9;
}

.login-form {
    background: var(--card);
    padding: 30px;
    border-radius: 20px;
    box-shadow: 0 20px 40px rgba(0,0,0,0.2);
    margin-bottom: 30px;
}

.input-field {
    width: 100%;
    padding: 15px;
    margin-bottom: 15px;
    border: 2px solid var(--border);
    border-radius: 12px;
    font-size: 16px;
    transition: all 0.3s;
    background: var(--card);
    color: var(--text);
}

.input-field:focus {
    outline: none;
    border-color: var(--primary);
}

.btn-primary, .btn-secondary, .btn-danger {
    padding: 15px 25px;
    border: none;
    border-radius: 12px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
}

.btn-primary {
    background: var(--primary);
    color: white;
}

.btn-primary:hover {
    background: var(--primary-dark);
    transform: translateY(-2px);
}

.btn-secondary {
    background: transparent;
    color: var(--primary);
    border: 2px solid var(--primary);
    margin-top: 10px;
}

.btn-secondary:hover {
    background: var(--primary);
    color: white;
}

.btn-danger {
    background: var(--danger);
    color: white;
}

.btn-full {
    width: 100%;
}

.btn-small {
    padding: 8px 16px;
    font-size: 12px;
    border: none;
    border-radius: 8px;
    background: var(--border);
    color: var(--text);
    cursor: pointer;
}

.btn-small.active {
    background: var(--primary);
    color: white;
}

.btn-audio {
    background: var(--secondary);
    color: white;
}

.features-preview {
    display: flex;
    justify-content: space-around;
    color: white;
    text-align: center;
}

.feature-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;
}

.feature-item span {
    font-size: 30px;
}

.text-center { text-align: center; }
.text-small { font-size: 14px; color: var(--text-light); }
.mt-3 { margin-top: 15px; }

/* ==========================================
   MAIN APP HEADER
   ========================================== */
.app-header {
    background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
    color: white;
    padding: 15px 20px;
    position: sticky;
    top: 0;
    z-index: 100;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
}

.header-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 15px;
}

.logo-small {
    display: flex;
    align-items: center;
    gap: 12px;
}

.arabic-logo-small {
    font-family: 'Amiri', serif;
    font-size: 36px;
    width: 50px;
    height: 50px;
    background: rgba(255,255,255,0.2);
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.logo-small h2 {
    font-size: 20px;
    margin-bottom: 2px;
}

.user-name {
    font-size: 13px;
    opacity: 0.9;
}

.header-actions {
    display: flex;
    gap: 10px;
}

.icon-btn {
    width: 40px;
    height: 40px;
    border: none;
    background: rgba(255,255,255,0.2);
    border-radius: 10px;
    color: white;
    font-size: 18px;
    cursor: pointer;
    transition: all 0.3s;
}

.icon-btn:hover {
    background: rgba(255,255,255,0.3);
}

/* XP Bar */
.xp-container {
    background: rgba(0,0,0,0.2);
    padding: 10px 15px;
    border-radius: 12px;
}

.xp-info {
    display: flex;
    justify-content: space-between;
    font-size: 12px;
    margin-bottom: 5px;
}

.xp-bar {
    height: 8px;
    background: rgba(255,255,255,0.2);
    border-radius: 4px;
    overflow: hidden;
}

.xp-fill {
    height: 100%;
    background: linear-gradient(90deg, #fbbf24, #f59e0b);
    border-radius: 4px;
    transition: width 0.5s ease;
}

/* ==========================================
   NAVIGATION
   ========================================== */
.main-nav {
    display: flex;
    background: var(--card);
    padding: 10px 5px;
    gap: 5px;
    overflow-x: auto;
    border-bottom: 1px solid var(--border);
    position: sticky;
    top: 110px;
    z-index: 99;
}

.nav-btn {
    flex: 1;
    min-width: 70px;
    padding: 10px 5px;
    border: none;
    background: transparent;
    border-radius: 12px;
    cursor: pointer;
    transition: all 0.3s;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;
    color: var(--text-light);
    font-size: 12px;
}

.nav-btn.active {
    background: var(--primary);
    color: white;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(31, 122, 76, 0.3);
}

.nav-icon {
    font-size: 24px;
}

/* ==========================================
   CONTENT SECTIONS
   ========================================== */
.content-area {
    padding: 20px;
    padding-bottom: 100px;
}

.content-section {
    display: none;
    animation: fadeIn 0.3s ease;
}

.content-section.active {
    display: block;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
}

.section-header {
    margin-bottom: 20px;
}

.section-header h3 {
    font-size: 22px;
    margin-bottom: 5px;
    color: var(--primary);
}

.section-header p {
    color: var(--text-light);
    font-size: 14px;
}

/* ==========================================
   CARDS & BAB LIST
   ========================================== */
.bab-list {
    display: flex;
    flex-direction: column;
    gap: 15px;
}

.bab-card {
    background: var(--card);
    border-radius: 16px;
    padding: 20px;
    box-shadow: var(--shadow);
    cursor: pointer;
    transition: all 0.3s;
    border: 2px solid transparent;
    position: relative;
    overflow: hidden;
}

.bab-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 10px 30px rgba(0,0,0,0.15);
}

.bab-card.completed {
    border-color: #10b981;
}

.bab-card.locked {
    opacity: 0.6;
    cursor: not-allowed;
}

.bab-card.locked::after {
    content: '🔒';
    position: absolute;
    top: 20px;
    right: 20px;
    font-size: 24px;
}

.bab-number {
    display: inline-block;
    width: 40px;
    height: 40px;
    background: var(--primary);
    color: white;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: bold;
    margin-bottom: 10px;
}

.bab-card.completed .bab-number {
    background: #10b981;
}

.bab-title {
    font-size: 18px;
    font-weight: 600;
    margin-bottom: 5px;
}

.bab-arabic {
    font-family: 'Amiri', serif;
    font-size: 20px;
    color: var(--primary);
    text-align: right;
    margin-bottom: 10px;
}

.bab-desc {
    font-size: 14px;
    color: var(--text-light);
    margin-bottom: 15px;
}

.bab-progress {
    display: flex;
    align-items: center;
    gap: 10px;
}

.progress-track {
    flex: 1;
    height: 6px;
    background: var(--border);
    border-radius: 3px;
    overflow: hidden;
}

.progress-fill {
    height: 100%;
    background: var(--primary);
    border-radius: 3px;
    transition: width 0.5s ease;
}

.bab-status {
    font-size: 12px;
    color: var(--text-light);
}

/* ==========================================
   KITAB SECTION
   ========================================== */
.kitab-controls {
    display: flex;
    gap: 10px;
    margin-bottom: 20px;
    flex-wrap: wrap;
}

.kitab-content {
    background: var(--card);
    border-radius: 16px;
    padding: 20px;
    box-shadow: var(--shadow);
    max-height: 60vh;
    overflow-y: auto;
}

.kitab-item {
    padding: 20px;
    border-bottom: 1px solid var(--border);
    margin-bottom: 15px;
}

.kitab-item:last-child {
    border-bottom: none;
}

.kitab-arabic {
    font-family: 'Amiri', serif;
    font-size: 24px;
    text-align: right;
    line-height: 2;
    margin-bottom: 15px;
    color: var(--text);
}

.kitab-latin {
    font-size: 16px;
    color: var(--text-light);
    margin-bottom: 10px;
    font-style: italic;
}

.kitab-terjemah {
    font-size: 14px;
    color: var(--text);
    line-height: 1.8;
    padding: 15px;
    background: var(--bg);
    border-radius: 10px;
    border-right: 4px solid var(--primary);
}

/* ==========================================
   QUIZ SECTION
   ========================================== */
.quiz-selection {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 15px;
}

.quiz-card {
    background: var(--card);
    border-radius: 16px;
    padding: 20px;
    text-align: center;
    cursor: pointer;
    transition: all 0.3s;
    box-shadow: var(--shadow);
}

.quiz-card:hover {
    transform: scale(1.05);
}

.quiz-card.locked {
    opacity: 0.5;
    cursor: not-allowed;
}

.quiz-icon {
    font-size: 40px;
    margin-bottom: 10px;
}

.quiz-title {
    font-weight: 600;
    margin-bottom: 5px;
}

.quiz-count {
    font-size: 12px;
    color: var(--text-light);
}

.quiz-container {
    background: var(--card);
    border-radius: 20px;
    padding: 25px;
    box-shadow: var(--shadow);
}

.quiz-progress {
    margin-bottom: 25px;
}

.quiz-progress span {
    font-size: 14px;
    color: var(--text-light);
    margin-bottom: 8px;
    display: block;
}

.progress-bar {
    height: 8px;
    background: var(--border);
    border-radius: 4px;
    overflow: hidden;
}

#quizProgressFill {
    height: 100%;
    background: var(--primary);
    border-radius: 4px;
    transition: width 0.3s ease;
}

.quiz-question {
    font-size: 18px;
    font-weight: 600;
    margin-bottom: 25px;
    line-height: 1.6;
}

.quiz-options {
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.quiz-option {
    padding: 18px;
    border: 2px solid var(--border);
    border-radius: 14px;
    cursor: pointer;
    transition: all 0.3s;
    text-align: left;
    background: var(--card);
    color: var(--text);
    font-size: 16px;
}

.quiz-option:hover:not(:disabled) {
    border-color: var(--primary);
    background: rgba(31, 122, 76, 0.05);
}

.quiz-option.correct {
    border-color: #10b981;
    background: rgba(16, 185, 129, 0.1);
}

.quiz-option.wrong {
    border-color: var(--danger);
    background: rgba(220, 38, 38, 0.1);
}

.quiz-option:disabled {
    cursor: not-allowed;
    opacity: 0.7;
}

.quiz-feedback {
    margin-top: 20px;
    padding: 20px;
    border-radius: 14px;
    animation: slideUp 0.3s ease;
}

.quiz-feedback.correct {
    background: rgba(16, 185, 129, 0.1);
    border: 2px solid #10b981;
}

.quiz-feedback.wrong {
    background: rgba(220, 38, 38, 0.1);
    border: 2px solid var(--danger);
}

@keyframes slideUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}

.quiz-result {
    text-align: center;
    padding: 40px 20px;
}

.result-icon {
    font-size: 80px;
    margin-bottom: 20px;
    animation: bounce 1s infinite;
}

@keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-20px); }
}

.result-score {
    font-size: 36px;
    font-weight: bold;
    color: var(--primary);
    margin: 20px 0;
}

/* ==========================================
   KAMUS SECTION
   ========================================== */
.search-box {
    position: relative;
    margin-bottom: 20px;
}

.search-box input {
    width: 100%;
    padding: 15px 50px 15px 20px;
    border: 2px solid var(--border);
    border-radius: 14px;
    font-size: 16px;
    background: var(--card);
    color: var(--text);
}

.search-box span {
    position: absolute;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
    font-size: 20px;
}

.kamus-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.kamus-item {
    background: var(--card);
    padding: 18px;
    border-radius: 14px;
    box-shadow: var(--shadow);
    border-right: 4px solid var(--primary);
}

.kamus-term {
    font-family: 'Amiri', serif;
    font-size: 22px;
    color: var(--primary);
    margin-bottom: 5px;
}

.kamus-def {
    font-size: 14px;
    color: var(--text);
    margin-bottom: 3px;
}

.kamus-explain {
    font-size: 12px;
    color: var(--text-light);
}

/* ==========================================
   I'RAB SECTION
   ========================================== */
.irab-input-container {
    margin-bottom: 25px;
}

.irab-input-container textarea {
    width: 100%;
    padding: 20px;
    border: 2px solid var(--border);
    border-radius: 16px;
    font-size: 20px;
    font-family: 'Amiri', serif;
    resize: none;
    margin-bottom: 15px;
    background: var(--card);
    color: var(--text);
    min-height: 100px;
}

.irab-actions {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
}

.irab-result {
    background: var(--card);
    border-radius: 20px;
    padding: 25px;
    margin-bottom: 25px;
    box-shadow: var(--shadow);
    animation: fadeIn 0.5s ease;
}

.irab-result h4 {
    margin-bottom: 20px;
    color: var(--primary);
    font-size: 18px;
}

.analysis-item {
    padding: 18px;
    margin-bottom: 15px;
    border-radius: 14px;
    color: white;
    position: relative;
    overflow: hidden;
}

.analysis-item::before {
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    width: 100px;
    height: 100px;
    background: rgba(255,255,255,0.1);
    border-radius: 50%;
    transform: translate(30%, -30%);
}

.analysis-item.isim { background: linear-gradient(135deg, #3b82f6, #1d4ed8); }
.analysis-item.fiil { background: linear-gradient(135deg, #10b981, #059669); }
.analysis-item.harf { background: linear-gradient(135deg, #8b5cf6, #6d28d9); }
.analysis-item.faill { background: linear-gradient(135deg, #f59e0b, #d97706); }
.analysis-item.mafkul { background: linear-gradient(135deg, #ec4899, #be185d); }

.analysis-word {
    font-family: 'Amiri', serif;
    font-size: 28px;
    text-align: right;
    margin-bottom: 8px;
    position: relative;
    z-index: 1;
}

.analysis-type {
    font-weight: bold;
    font-size: 16px;
    margin-bottom: 5px;
    position: relative;
    z-index: 1;
}

.analysis-desc {
    font-size: 14px;
    opacity: 0.9;
    position: relative;
    z-index: 1;
}

.irab-guide {
    background: var(--card);
    border-radius: 16px;
    padding: 20px;
    box-shadow: var(--shadow);
}

.irab-guide h4 {
    margin-bottom: 15px;
    color: var(--primary);
}

.guide-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
}

.guide-item {
    padding: 15px;
    border-radius: 12px;
    text-align: center;
    font-size: 14px;
}

.guide-item.rafa { background: rgba(16, 185, 129, 0.1); color: #059669; border: 2px solid #10b981; }
.guide-item.nasab { background: rgba(245, 158, 11, 0.1); color: #d97706; border: 2px solid #f59e0b; }
.guide-item.jarr { background: rgba(59, 130, 246, 0.1); color: #2563eb; border: 2px solid #3b82f6; }
.guide-item.jazm { background: rgba(139, 92, 246, 0.1); color: #7c3aed; border: 2px solid #8b5cf6; }

/* ==========================================
   MODAL
   ========================================== */
.modal {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0,0,0,0.5);
    z-index: 1000;
    display: flex;
    align-items: flex-end;
    justify-content: center;
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s;
}

.modal.hidden {
    opacity: 0;
    visibility: hidden;
}

.modal:not(.hidden) {
    opacity: 1;
    visibility: visible;
}

.modal-content {
    background: var(--card);
    width: 100%;
    max-width: 600px;
    max-height: 90vh;
    border-radius: 24px 24px 0 0;
    overflow: hidden;
    transform: translateY(100%);
    transition: transform 0.3s ease;
}

.modal:not(.hidden) .modal-content {
    transform: translateY(0);
}

.modal-large {
    height: 90vh;
    display: flex;
    flex-direction: column;
}

.modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;
    border-bottom: 1px solid var(--border);
}

.modal-header.sticky {
    position: sticky;
    top: 0;
    background: var(--card);
    z-index: 10;
}

.back-btn {
    background: none;
    border: none;
    font-size: 16px;
    color: var(--primary);
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 5px;
}

.audio-btn {
    width: 45px;
    height: 45px;
    border-radius: 50%;
    border: none;
    background: var(--primary);
    color: white;
    font-size: 20px;
    cursor: pointer;
    transition: all 0.3s;
}

.audio-btn.playing {
    animation: pulse 1s infinite;
}

.close-btn {
    width: 40px;
    height: 40px;
    border: none;
    background: var(--border);
    border-radius: 50%;
    cursor: pointer;
    font-size: 18px;
}

/* Settings */
.settings-list {
    padding: 20px;
}

.setting-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 18px 0;
    border-bottom: 1px solid var(--border);
}

.setting-item.info {
    color: var(--text-light);
}

.version {
    font-size: 14px;
    color: var(--text-light);
}

/* Switch Toggle */
.switch {
    position: relative;
    display: inline-block;
    width: 50px;
    height: 28px;
}

.switch input {
    opacity: 0;
    width: 0;
    height: 0;
}

.slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: var(--border);
    transition: .4s;
    border-radius: 28px;
}

.slider:before {
    position: absolute;
    content: "";
    height: 22px;
    width: 22px;
    left: 3px;
    bottom: 3px;
    background-color: white;
    transition: .4s;
    border-radius: 50%;
}

input:checked + .slider {
    background-color: var(--primary);
}

input:checked + .slider:before {
    transform: translateX(22px);
}

/* ==========================================
   MATERI DETAIL CONTENT
   ========================================== */
#materiDetailContent {
    flex: 1;
    overflow-y: auto;
    padding: 20px;
}

.materi-detail-header {
    text-align: center;
    margin-bottom: 30px;
    padding: 30px;
    background: linear-gradient(135deg, var(--primary), var(--primary-dark));
    color: white;
    border-radius: 20px;
}

.materi-detail-number {
    font-size: 60px;
    font-weight: bold;
    opacity: 0.3;
    line-height: 1;
}

.materi-detail-title {
    font-size: 24px;
    margin: 15px 0;
}

.materi-detail-arabic {
    font-family: 'Amiri', serif;
    font-size: 28px;
    opacity: 0.9;
}

.content-block {
    margin-bot
    // ==========================================
// DATA & CONFIGURATION
// ==========================================

const APP_VERSION = '2.0.0';
const DB_NAME = 'NahwuProDB';
const DB_VERSION = 1;

// Data Materi Lengkap (9 Bab)
const materiData = [
    {
        id: 1,
        title: "Kalimat (الْكَلَامُ)",
        arabic: "الْكَلَامُ هُوَ اللَّفْظُ الْمُرَكَّبُ الْمُفِيدُ بِالْوَضْعِ",
        latin: "Al-kalamu huwal lafzhul murakkabul mufidu bil wa'di",
        description: "Pengenalan dasar tentang definisi kalimat dalam ilmu nahwu",
        icon: "📖",
        content: `
            <div class="content-block">
                <h4>📌 Definisi Kalimat</h4>
                <p class="content-text">
                    Kalimat dalam ilmu nahwu adalah lafadz yang tersusun dari dua kata atau lebih, 
                    yang memberikan makna yang sempurna dan bermanfaat menurut penggunaan bahasa Arab.
                </p>
                <span class="arabic-highlight">الْكَلَامُ هُوَ اللَّفْظُ الْمُرَكَّبُ الْمُفِيدُ بِالْوَضْعِ</span>
            </div>
            
            <div class="content-block">
                <h4>🔑 Rukun Kalimat (3 Syarat)</h4>
                <div class="example-box">
                    <div class="example-item">
                        <div class="example-arabic">١. اللَّفْظُ (Lafadz)</div>
                        <div class="example-meaning">Suara yang mengandung huruf hijaiyah yang bisa diucapkan</div>
                    </div>
                    <div class="example-item">
                        <div class="example-arabic">٢. التَّرْكِيبُ (Tarkib)</div>
                        <div class="example-meaning">Tersusun dari dua kata atau lebih yang tersusun secara gramatikal</div>
                    </div>
                    <div class="example-item">
                        <div class="example-arabic">٣. الإِفَادَةُ (Ifadah)</div>
                        <div class="example-meaning">Memberi makna yang sempurna dan bermanfaat</div>
                    </div>
                </div>
            </div>
            
            <div class="content-block">
                <h4>📝 Contoh Kalimat</h4>
                <div class="example-box">
                    <div class="example-item">
                        <div class="example-arabic">قَامَ زَيْدٌ</div>
                        <div class="example-latin">Qama Zaidun</div>
                        <div class="example-meaning">✅ Kalimat sempurna (ada fi'il dan fa'il)</div>
                    </div>
                    <div class="example-item">
                        <div class="example-arabic">قَامَ</div>
                        <div class="example-latin">Qama</div>
                        <div class="example-meaning">❌ Bukan kalimat (kurang fa'il)</div>
                    </div>
                    <div class="example-item">
                        <div class="example-arabic">زَيْدٌ</div>
                        <div class="example-latin">Zaidun</div>
                        <div class="example-meaning">❌ Bukan kalimat (kurang fi'il)</div>
                    </div>
                </div>
            </div>
        `
    },
    {
        id: 2,
        title: "Isim, Fi'il, dan Harf",
        arabic: "أَقْسَامُ الْكَلَامِ ثَلَاثَةٌ: اِسْمٌ وَفِعْلٌ وَحَرْفٌ",
        latin: "Aqsamul kalami tsalatsah: ismun wa fi'lun wa harfun",
        description: "Pembagian kata dalam bahasa Arab menjadi 3 macam",
        icon: "✍️",
        content: `
            <div class="content-block">
                <h4>📌 Pembagian Kalam</h4>
                <p class="content-text">
                    Kitab Jurumiyah membagi kalimat (kata) dalam bahasa Arab menjadi tiga macam: 
                    Isim (kata benda), Fi'il (kata kerja), dan Harf (kata penghubung).
                </p>
                <span class="arabic-highlight">أَقْسَامُ الْكَلَامِ ثَلَاثَةٌ: اِسْمٌ وَفِعْلٌ وَحَرْفٌ</span>
            </div>
            
            <div class="content-block">
                <h4>📍 1. Isim (الاِسْمُ)</h4>
                <p class="content-text">Kata yang menunjukkan makna pada dirinya sendiri dan tidak terkait dengan waktu.</p>
                <span class="arabic-highlight">الْإِسْمُ كُلُّ كَلِمَةٍ دَلَّتْ عَلَى مَعْنًى فِي نَفْسِهَا وَلَمْ تَقْتَرِنْ بِزَمَانٍ</span>
                <div class="example-box">
                    <div class="example-item">
                        <div class="example-arabic">رَجُلٌ، فَرَسٌ، جَبَلٌ</div>
                        <div class="example-meaning">Laki-laki, kuda, gunung</div>
                    </div>
                </div>
            </div>
            
            <div class="content-block">
                <h4>⚡ 2. Fi'il (الْفِعْلُ)</h4>
                <p class="content-text">Kata yang menunjukkan makna pada dirinya sendiri dan terkait dengan waktu.</p>
                <span class="arabic-highlight">الْفِعْلُ كُلُّ كَلِمَةٍ دَلَّتْ عَلَى مَعْنًى فِي نَفْسِهَا وَاقْتَرَنَتْ بِزَمَانٍ</span>
                <div class="example-box">
                    <div class="example-item">
                        <div class="example-arabic">كَتَبَ (lampau)، يَكْتُبُ (sekarang)، اُكْتُبْ (perintah)</div>
                        <div class="example-meaning">Menulis - tiga bentuk waktu</div>
                    </div>
                </div>
            </div>
            
            <div class="content-block">
                <h4>🔗 3. Harf (الْحَرْفُ)</h4>
                <p class="content-text">Kata yang menunjukkan makna pada kata lain (tidak berdiri sendiri).</p>
                <span class="arabic-highlight">الْحَرْفُ كُلُّ كَلِمَةٍ دَلَّتْ عَلَى مَعْنًى فِي غَيْرِهَا</span>
                <div class="example-box">
                    <div class="example-item">
                        <div class="example-arabic">فِي، مِنْ، إِلَى، عَلَى، عَنْ</div>
                        <div class="example-meaning">Di, dari, ke, di atas, tentang</div>
                    </div>
                </div>
            </div>
        `
    },
    {
        id: 3,
        title: "Tanda-tanda Isim",
        arabic: "لِلْإِسْمِ أَرْبَعُ عَلَامَاتٍ",
        latin: "Lil ismi arba'u 'alamatin",
        description: "Empat tanda pengenal isim dalam bahasa Arab",
        icon: "🎯",
        content: `
            <div class="content-block">
                <h4>📌 Empat Tanda Isim</h4>
                <p class="content-text">
                    Isim memiliki empat tanda yang membedakannya dari fi'il dan harf. 
                    Dengan tanda-tanda ini, kita dapat mengenali isim dalam kalimat.
                </p>
            </div>
            
            <div class="content-block">
                <h4>1️⃣ Al-Qabul bit-Tanwin (Penerimaan Tanwin)</h4>
                <p class="content-text">Isim bisa menerima tanwin (nunnation) di akhirnya</p>
                <span class="arabic-highlight">مُسْلِمٌ - مُسْلِمًا - مُسْلِمٍ</span>
            </div>
            
            <div class="content-block">
                <h4>2️⃣ Dukhulul Alif lam (Dapat diawali Alif Lam)</h4>
                <p class="content-text">Isim bisa didahului dengan alif lam (ال)</p>
                <span class="arabic-highlight">الرَّجُلُ - الْكِتَابُ - الْمَدْرَسَةُ</span>
            </div>
            
            <div class="content-block">
                <h4>3️⃣ Al-Isnad Ilayh (Bersandung kepadanya)</h4>
                <p class="content-text">Isim bisa menjadi tempat bersandung (mudhaf ilaih)</p>
                <span class="arabic-highlight">كِتَابُ زَيْدٍ - بَابُ الْمَسْجِدِ</span>
            </div>
            
            <div class="content-block">
                <h4>4️⃣ Dukhul Huruf Jar (Bisa didahului huruf jar)</h4>
                <p class="content-text">Isim bisa didahului harf jar seperti في, من, إلى</p>
                <span class="arabic-highlight">فِي الْبَيْتِ - مِنَ الْمَدْرَسَةِ</span>
            </div>
        `
    },
    {
        id: 4,
        title: "Tanda-tanda Fi'il",
        arabic: "عَلَامَاتُ الْفِعْلِ",
        latin: "Alamatul fi'li",
        description: "Tanda pengenal fi'il mudhori' dan fi'il amar",
        icon: "⚡",
        content: `<div class="content-block"><h4>📌 Tanda Fi'il</h4><p>Sedang dalam pengembangan...</p></div>`
    },
    {
        id: 5,
        title: "Tanda-tanda Harf",
        arabic: "عَلَامَاتُ الْحَرْفِ",
        latin: "Alamatul harfi",
        description: "Tanda pengenal huruf dalam nahwu",
        icon: "🔤",
        content: `<div class="content-block"><h4>📌 Tanda Harf</h4><p>Sedang dalam pengembangan...</p></div>`
    },
    {
        id: 6,
        title: "Mu'rab dan Mabni",
        arabic: "الْمُعْرَبُ وَالْمَبْنِيُّ",
        latin: "Al-mu'rabu wal mabniyyu",
        description: "Pembagian kata berdasarkan perubahan akhirnya",
        icon: "🔄",
        content: `<div class="content-block"><h4>📌 Mu'rab dan Mabni</h4><p>Sedang dalam pengembangan...</p></div>`
    },
    {
        id: 7,
        title: "Marfu'at",
        arabic: "الْمَرْفُوعَاتُ",
        latin: "Al-marfu'at",
        description: "Kata-kata yang diakhiri dengan dhommah",
        icon: "⬆️",
        content: `<div class="content-block"><h4>📌 Marfu'at</h4><p>Sedang dalam pengembangan...</p></div>`
    },
    {
        id: 8,
        title: "Mansubat",
        arabic: "الْمَنْصُوبَاتُ",
        latin: "Al-mansubat",
        description: "Kata-kata yang diakhiri dengan fathah",
        icon: "➡️",
        content: `<div class="content-block"><h4>📌 Mansubat</h4><p>Sedang dalam pengembangan...</p></div>`
    },
    {
        id: 9,
        title: "Majrurat",
        arabic: "الْمَجْرُورَاتُ",
        latin: "Al-majrurat",
        description: "Kata-kata yang diakhiri dengan kasrah",
        icon: "⬇️",
        content: `<div class="content-block"><h4>📌 Majrurat</h4><p>Sedang dalam pengembangan...</p></div>`
    }
];

// Kitab Jurumiyah (Teks Asli)
const kitabData = [
    {
        id: 1,
        arabic: "بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ",
        latin: "Bismillahir-rahmanir-rahim",
        terjemah: "Dengan nama Allah Yang Maha Pengasih lagi Maha Penyayang"
    },
    {
        id: 2,
        arabic: "قَالَ أَبُو عَبْدِ اللَّهِ مُحَمَّدُ بْنُ دَاوُدَ الصَّنْهَاجِيُّ",
        latin: "Qala Abu Abdullah Muhammad bin Dawud as-Sanhaji",
        terjemah: "Berkata Abu Abdullah Muhammad bin Dawud as-Sanhaji (penulis kitab)"
    },
    {
        id: 3,
        arabic: "الْكَلَامُ هُوَ اللَّفْظُ الْمُرَكَّبُ الْمُفِيدُ بِالْوَضْعِ",
        latin: "Al-kalamu huwal-lafzhul murakkabul mufidu bil-wa'di",
        terjemah: "Kalimat adalah lafadz yang tersusun yang memberi manfaat menurut penggunaan bahasa Arab"
    },
    {
        id: 4,
        arabic: "وَأَقْسَامُهُ ثَلَاثَةٌ: اِسْمٌ وَفِعْلٌ وَحَرْفٌ جَاءَ لِمَعْنًى",
        latin: "Wa aqsamuhu tsalatsah: ismun wa fi'lun wa harfun ja'a lima'na",
        terjemah: "Dan pembagiannya ada tiga: isim, fi'il, dan harf yang datang untuk suatu makna"
    },
    {
        id: 5,
        arabic: "فَالْإِسْمُ يُعْرَفُ بِالْخَفْضِ وَالتَّنْوِينِ وَدُخُولِ الأَلِفِ وَاللَّامِ وَالْحُرُوفِ",
        latin: "Fal-ismu yu'rafu bil-khafdi wat-tanwini wa dukhulil alifi wal-lami wal-huruf",
        terjemah: "Maka isim dikenal dengan khafdh (kasrah), tanwin, masuknya alif lam, dan huruf-huruf (jar)"
    }
];

// Data Kamus
const kamusData = [
    { term: "إِسْمٌ", definisi: "Kata benda", penjelasan: "Kata yang menunjukkan makna pada dirinya sendiri tanpa terkait waktu" },
    { term: "فِعْلٌ", definisi: "Kata kerja", penjelasan: "Kata yang menunjukkan makna pada dirinya sendiri dan terkait dengan waktu" },
    { term: "حَرْفٌ", definisi: "Kata penghubung", penjelasan: "Kata yang menunjukkan makna pada kata lain, tidak berdiri sendiri" },
    { term: "فَاعِلٌ", definisi: "Pelaku", penjelasan: "Isim yang berupa pelaku dari suatu perbuatan, marfu' dengan dhommah" },
    { term: "مَفْعُولٌ بِهِ", definisi: "Objek", penjelasan: "Isim yang dikenai perbuatan, mansub dengan fathah" },
    { term: "مُبْتَدَأٌ", definisi: "Subjek awal", penjelasan: "Isim yang diawali kalimat, marfu' dengan dhommah" },
    { term: "خَبَرٌ", definisi: "Predikat", penjelasan: "Keterangan tentang mubtada', marfu' dengan dhommah" },
    { term: "مَرْفُوعٌ", definisi: "Dhommah", penjelasan: "Tanda i'rab isim dengan harakat dhommah (ُ)" },
    { term: "مَنْصُوبٌ", definisi: "Fathah", penjelasan: "Tanda i'rab isim dengan harakat fathah (َ)" },
    { term: "مَجْرُورٌ", definisi: "Kasrah", penjelasan: "Tanda i'rab isim dengan harakat kasrah (ِ)" },
    { term: "مَعْرِفَةٌ", definisi: "Isim ma'rifah", penjelasan: "Isim yang ditentukan, diawali dengan alif lam (ال)" },
    { term: "نَكِرَةٌ", definisi: "Isim nakirah", penjemah: "Isim yang tidak ditentukan, bertanwin" },
    { term: "مُضَافٌ", definisi: "Yang bersandung", penjelasan: "Isim yang bersandung kepada isim lain" },
    { term: "مُضَافٌ إِلَيْهِ", definisi: "Tempat bersandung", penjelasan: "Isim yang menjadi tempat bersandung, majrur" },
    { term: "تَنْوِينٌ", definisi: "Nunnation", penjelasan: "Nun sukun yang ditambahkan di akhir isim nakirah (ٌ ٍ ً)" }
];

// Data Quiz per Bab
const quizData = {
    1: [
        { soal: "Apa definisi kalimat menurut ilmu nahwu?", pilihan: ["Lafadz tunggal", "Lafadz yang tersusun dan memberi manfaat", "Huruf hijaiyah", "Kata kerja saja"], jawaban: 1, penjelasan: "Kalimat adalah lafadz yang tersusun (murakkab) yang memberi manfaat (mufid)." },
        { soal: "Berapa rukun kalimat?", pilihan: ["2", "3", "4", "5"], jawaban: 1, penjelasan: "Rukun kalimat ada 3: lafadz, tarkib (tersusun), dan ifadah (memberi manfaat)." },
        { soal: "Manakah yang termasuk kalimat sempurna?", pilihan: ["قَامَ", "زَيْدٌ", "قَامَ زَيْدٌ", "فِي"], jawaban: 2, penjelasan: "قَامَ زَيْدٌ adalah kalimat sempurna karena memiliki fi'il (قَامَ) dan fa'il (زَيْدٌ)." },
        { soal: "Apa yang dimaksud dengan اللَّفْظُ?", pilihan: ["Makna", "Suara yang mengandung huruf hijaiyah", "Kalimat", "Waktu"], jawaban: 1, penjelasan: "Lafadz adalah suara yang mengandung huruf hijaiyah yang bisa diucapkan." }
    ],
    2: [
        { soal: "Berapa pembagian kalam menurut Jurumiyah?", pilihan: ["2", "3", "4", "5"], jawaban: 1, penjelasan: "Kalam dibagi menjadi 3: isim, fi'il, dan harf." },
        { soal: "Apa ciri utama isim?", pilihan: ["Terkait dengan waktu", "Tidak terkait dengan waktu", "Selalu bergerak", "Berupa perintah"], jawaban: 1, penjelasan: "Isim tidak terkait dengan waktu (lam yaqtarin biz-zaman)." },
        { soal: "Manakah yang termasuk fi'il?", pilihan: ["كِتَابٌ", "مُحَمَّدٌ", "كَتَبَ", "فِي"], jawaban: 2, penjelasan: "كَتَبَ adalah fi'il (kata kerja) yang menunjukkan perbuatan menulis." },
        { soal: "Apa fungsi harf?", pilihan: ["Sebagai subjek", "Menghubungkan atau memberi makna pada kata lain", "Sebagai objek", "Sebagai keterangan"], jawaban: 1, penjelasan: "Harf berfungsi memberi makna pada kata lain (isim) setelahnya." }
    ],
    3: [
        { soal: "Berapa tanda isim menurut Jurumiyah?", pilihan: ["3", "4", "5", "6"], jawaban: 1, penjelasan: "Isim memiliki 4 tanda: qabul bit-tanwin, dukhul alif lam, al-isnad ilaih, dan dukhul huruf jar." },
        { soal: "Apa yang dimaksud dengan tanwin?", pilihan: ["Alif lam", "Nun sukun di akhir isim", "Kasrah ganda", "Dhommah tunggal"], jawaban: 1, penjelasan: "Tanwin adalah nun sukun yang ditambahkan di akhir isim nakirah." },
        { soal: "Manakah contoh isim dengan alif lam?", pilihan: ["رَجُلٌ", "الرَّجُلُ", "رَجُلًا", "فِي"], jawaban: 1, penjelasan: "الرَّجُلُ memiliki alif lam (ال) di awalnya, menunjukkan isim ma'rifah." }
    ]
};

// ==========================================
// STATE MANAGEMENT
// ==========================================

let currentUser = null;
let userProgress = {
    xp: 0,
    level: 1,
    completedBabs: [],
    quizScores: {}
};

let currentQuiz = null;
let currentQuestion = 0;
let quizScore = 0;
let audioEnabled = true;
let darkMode = false;
let latinMode = false;

// ==========================================
// INITIALIZATION
// ==========================================

document.addEventListener('DOMContentLoaded', () => {
    loadUserData();
    initApp();
});

function initApp() {
    renderBabList();
    renderKitab();
    renderKamus();
    renderQuizSelection();
    
    // Check saved preferences
    const savedDark = localStorage.getItem('darkMode') === 'true';
    if (savedDark) toggleDarkMode();
    
    const savedAudio = localStorage.getItem('audioEnabled');
    if (savedAudio !== null) audioEnabled = savedAudio === 'true';
}

// ==========================================
// AUTHENTICATION
// ==========================================

function login() {
    const username = document.getElementById('username').value;
    const password = document.getElementById('password').value;
    
    if (!username || !password) {
        showToast('Mohon isi username dan password', 'error');
        return;
    }
    
    // Simple auth (in real app, use proper backend)
    const users = JSON.parse(localStorage.getItem('nahwuUsers') || '[]');
    const user = users.find(u => u.username === username && u.password === password);
    
    if (user || (username === 'demo' && password === 'demo')) {
        currentUser = { username, name: user?.name || username };
        localStorage.setItem('currentUser', JSON.stringify(currentUser));
        showMainApp();
        showToast('Selamat datang kembali!', 'success');
        playAudio('login');
    } else {
        showToast('Username atau password salah', 'error');
    }
}

function guestLogin() {
    currentUser = { username: 'guest', name: 'Tamu' };
    showMainApp();
    showToast('Masuk sebagai tamu', 'info');
}

function register() {
    const name = document.getElementById('regName').value;
    const username = document.getElementById('regUsername').value;
    const email = document.getElementById('regEmail').value;
    const password = document.getElementById('regPassword').value;
    
    if (!name || !username || !password) {
        showToast('Mohon lengkapi data', 'error');
        return;
    }
    
    const users = JSON.parse(localStorage.getItem('nahwuUsers') || '[]');
    
    if (users.find(u => u.username === username)) {
        showToast('Username sudah terdaftar', 'error');
        return;
    }
    
    users.push({ name, username, email, password });
    localStorage.setItem('nahwuUsers', JSON.stringify(users));
    
    showToast('Pendaftaran berhasil! Silakan login', 'success');
    showLogin();
}

function logout() {
    currentUser = null;
    localStorage.removeItem('currentUser');
    document.getElementById('mainApp').classList.remove('active');
    document.getElementById('loginScreen').classList.add('active');
    showToast('Berhasil keluar', 'info');
}

function showRegister() {
    document.getElementById('loginScreen').classList.remove('active');
    document.getElementById('registerScreen').classList.add('active');
}

function showLogin() {
    document.getElementById('registerScreen').classList.remove('active');
    document.getElementById('loginScreen').classList.add('active');
}

function showMainApp() {
    document.getElementById('loginScreen').classList.remove('active');
    document.getElementById('registerScreen').classList.remove('active');
    document.getElementById('mainApp').classList.add('active');
    
    document.getElementById('displayName').textContent = currentUser?.name || 'Santri';
    updateXPDistplay();
}
// ==========================================
// DATA & CONFIGURATION
// ==========================================

const APP_VERSION = '2.0.0';
const DB_NAME = 'NahwuProDB';
const DB_VERSION = 1;

// Data Materi Lengkap (9 Bab)
const materiData = [
    {
        id: 1,
        title: "Kalimat (الْكَلَامُ)",
        arabic: "الْكَلَامُ هُوَ اللَّفْظُ الْمُرَكَّبُ الْمُفِيدُ بِالْوَضْعِ",
        latin: "Al-kalamu huwal lafzhul murakkabul mufidu bil wa'di",
        description: "Pengenalan dasar tentang definisi kalimat dalam ilmu nahwu",
        icon: "📖",
        content: `
            <div class="content-block">
                <h4>📌 Definisi Kalimat</h4>
                <p class="content-text">
                    Kalimat dalam ilmu nahwu adalah lafadz yang tersusun dari dua kata atau lebih, 
                    yang memberikan makna yang sempurna dan bermanfaat menurut penggunaan bahasa Arab.
                </p>
                <span class="arabic-highlight">الْكَلَامُ هُوَ اللَّفْظُ الْمُرَكَّبُ الْمُفِيدُ بِالْوَضْعِ</span>
            </div>
            
            <div class="content-block">
                <h4>🔑 Rukun Kalimat (3 Syarat)</h4>
                <div class="example-box">
                    <div class="example-item">
                        <div class="example-arabic">١. اللَّفْظُ (Lafadz)</div>
                        <div class="example-meaning">Suara yang mengandung huruf hijaiyah yang bisa diucapkan</div>
                    </div>
                    <div class="example-item">
                        <div class="example-arabic">٢. التَّرْكِيبُ (Tarkib)</div>
                        <div class="example-meaning">Tersusun dari dua kata atau lebih yang tersusun secara gramatikal</div>
                    </div>
                    <div class="example-item">
                        <div class="example-arabic">٣. الإِفَادَةُ (Ifadah)</div>
                        <div class="example-meaning">Memberi makna yang sempurna dan bermanfaat</div>
                    </div>
                </div>
            </div>
            
            <div class="content-block">
                <h4>📝 Contoh Kalimat</h4>
                <div class="example-box">
                    <div class="example-item">
                        <div class="example-arabic">قَامَ زَيْدٌ</div>
                        <div class="example-latin">Qama Zaidun</div>
                        <div class="example-meaning">✅ Kalimat sempurna (ada fi'il dan fa'il)</div>
                    </div>
                    <div class="example-item">
                        <div class="example-arabic">قَامَ</div>
                        <div class="example-latin">Qama</div>
                        <div class="example-meaning">❌ Bukan kalimat (kurang fa'il)</div>
                    </div>
                    <div class="example-item">
                        <div class="example-arabic">زَيْدٌ</div>
                        <div class="example-latin">Zaidun</div>
                        <div class="example-meaning">❌ Bukan kalimat (kurang fi'il)</div>
                    </div>
                </div>
            </div>
        `
    },
    {
        id: 2,
        title: "Isim, Fi'il, dan Harf",
        arabic: "أَقْسَامُ الْكَلَامِ ثَلَاثَةٌ: اِسْمٌ وَفِعْلٌ وَحَرْفٌ",
        latin: "Aqsamul kalami tsalatsah: ismun wa fi'lun wa harfun",
        description: "Pembagian kata dalam bahasa Arab menjadi 3 macam",
        icon: "✍️",
        content: `
            <div class="content-block">
                <h4>📌 Pembagian Kalam</h4>
                <p class="content-text">
                    Kitab Jurumiyah membagi kalimat (kata) dalam bahasa Arab menjadi tiga macam: 
                    Isim (kata benda), Fi'il (kata kerja), dan Harf (kata penghubung).
                </p>
                <span class="arabic-highlight">أَقْسَامُ الْكَلَامِ ثَلَاثَةٌ: اِسْمٌ وَفِعْلٌ وَحَرْفٌ</span>
            </div>
            
            <div class="content-block">
                <h4>📍 1. Isim (الاِسْمُ)</h4>
                <p class="content-text">Kata yang menunjukkan makna pada dirinya sendiri dan tidak terkait dengan waktu.</p>
                <span class="arabic-highlight">الْإِسْمُ كُلُّ كَلِمَةٍ دَلَّتْ عَلَى مَعْنًى فِي نَفْسِهَا وَلَمْ تَقْتَرِنْ بِزَمَانٍ</span>
                <div class="example-box">
                    <div class="example-item">
                        <div class="example-arabic">رَجُلٌ، فَرَسٌ، جَبَلٌ</div>
                        <div class="example-meaning">Laki-laki, kuda, gunung</div>
                    </div>
                </div>
            </div>
            
            <div class="content-block">
                <h4>⚡ 2. Fi'il (الْفِعْلُ)</h4>
                <p class="content-text">Kata yang menunjukkan makna pada dirinya sendiri dan terkait dengan waktu.</p>
                <span class="arabic-highlight">الْفِعْلُ كُلُّ كَلِمَةٍ دَلَّتْ عَلَى مَعْنًى فِي نَفْسِهَا وَاقْتَرَنَتْ بِزَمَانٍ</span>
                <div class="example-box">
                    <div class="example-item">
                        <div class="example-arabic">كَتَبَ (lampau)، يَكْتُبُ (sekarang)، اُكْتُبْ (perintah)</div>
                        <div class="example-meaning">Menulis - tiga bentuk waktu</div>
                    </div>
                </div>
            </div>
            
            <div class="content-block">
                <h4>🔗 3. Harf (الْحَرْفُ)</h4>
                <p class="content-text">Kata yang menunjukkan makna pada kata lain (tidak berdiri sendiri).</p>
                <span class="arabic-highlight">الْحَرْفُ كُلُّ كَلِمَةٍ دَلَّتْ عَلَى مَعْنًى فِي غَيْرِهَا</span>
                <div class="example-box">
                    <div class="example-item">
                        <div class="example-arabic">فِي، مِنْ، إِلَى، عَلَى، عَنْ</div>
                        <div class="example-meaning">Di, dari, ke, di atas, tentang</div>
                    </div>
                </div>
            </div>
        `
    },
    {
        id: 3,
        title: "Tanda-tanda Isim",
        arabic: "لِلْإِسْمِ أَرْبَعُ عَلَامَاتٍ",
        latin: "Lil ismi arba'u 'alamatin",
        description: "Empat tanda pengenal isim dalam bahasa Arab",
        icon: "🎯",
        content: `
            <div class="content-block">
                <h4>📌 Empat Tanda Isim</h4>
                <p class="content-text">
                    Isim memiliki empat tanda yang membedakannya dari fi'il dan harf. 
                    Dengan tanda-tanda ini, kita dapat mengenali isim dalam kalimat.
                </p>
            </div>
            
            <div class="content-block">
                <h4>1️⃣ Al-Qabul bit-Tanwin (Penerimaan Tanwin)</h4>
                <p class="content-text">Isim bisa menerima tanwin (nunnation) di akhirnya</p>
                <span class="arabic-highlight">مُسْلِمٌ - مُسْلِمًا - مُسْلِمٍ</span>
            </div>
            
            <div class="content-block">
                <h4>2️⃣ Dukhulul Alif lam (Dapat diawali Alif Lam)</h4>
                <p class="content-text">Isim bisa didahului dengan alif lam (ال)</p>
                <span class="arabic-highlight">الرَّجُلُ - الْكِتَابُ - الْمَدْرَسَةُ</span>
            </div>
            
            <div class="content-block">
                <h4>3️⃣ Al-Isnad Ilayh (Bersandung kepadanya)</h4>
                <p class="content-text">Isim bisa menjadi tempat bersandung (mudhaf ilaih)</p>
                <span class="arabic-highlight">كِتَابُ زَيْدٍ - بَابُ الْمَسْجِدِ</span>
            </div>
            
            <div class="content-block">
                <h4>4️⃣ Dukhul Huruf Jar (Bisa didahului huruf jar)</h4>
                <p class="content-text">Isim bisa didahului harf jar seperti في, من, إلى</p>
                <span class="arabic-highlight">فِي الْبَيْتِ - مِنَ الْمَدْرَسَةِ</span>
            </div>
        `
    },
    {
        id: 4,
        title: "Tanda-tanda Fi'il",
        arabic: "عَلَامَاتُ الْفِعْلِ",
        latin: "Alamatul fi'li",
        description: "Tanda pengenal fi'il mudhori' dan fi'il amar",
        icon: "⚡",
        content: `<div class="content-block"><h4>📌 Tanda Fi'il</h4><p>Sedang dalam pengembangan...</p></div>`
    },
    {
        id: 5,
        title: "Tanda-tanda Harf",
        arabic: "عَلَامَاتُ الْحَرْفِ",
        latin: "Alamatul harfi",
        description: "Tanda pengenal huruf dalam nahwu",
        icon: "🔤",
        content: `<div class="content-block"><h4>📌 Tanda Harf</h4><p>Sedang dalam pengembangan...</p></div>`
    },
    {
        id: 6,
        title: "Mu'rab dan Mabni",
        arabic: "الْمُعْرَبُ وَالْمَبْنِيُّ",
        latin: "Al-mu'rabu wal mabniyyu",
        description: "Pembagian kata berdasarkan perubahan akhirnya",
        icon: "🔄",
        content: `<div class="content-block"><h4>📌 Mu'rab dan Mabni</h4><p>Sedang dalam pengembangan...</p></div>`
    },
    {
        id: 7,
        title: "Marfu'at",
        arabic: "الْمَرْفُوعَاتُ",
        latin: "Al-marfu'at",
        description: "Kata-kata yang diakhiri dengan dhommah",
        icon: "⬆️",
        content: `<div class="content-block"><h4>📌 Marfu'at</h4><p>Sedang dalam pengembangan...</p></div>`
    },
    {
        id: 8,
        title: "Mansubat",
        arabic: "الْمَنْصُوبَاتُ",
        latin: "Al-mansubat",
        description: "Kata-kata yang diakhiri dengan fathah",
        icon: "➡️",
        content: `<div class="content-block"><h4>📌 Mansubat</h4><p>Sedang dalam pengembangan...</p></div>`
    },
    {
        id: 9,
        title: "Majrurat",
        arabic: "الْمَجْرُورَاتُ",
        latin: "Al-majrurat",
        description: "Kata-kata yang diakhiri dengan kasrah",
        icon: "⬇️",
        content: `<div class="content-block"><h4>📌 Majrurat</h4><p>Sedang dalam pengembangan...</p></div>`
    }
];

// Kitab Jurumiyah (Teks Asli)
const kitabData = [
    {
        id: 1,
        arabic: "بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ",
        latin: "Bismillahir-rahmanir-rahim",
        terjemah: "Dengan nama Allah Yang Maha Pengasih lagi Maha Penyayang"
    },
    {
        id: 2,
        arabic: "قَالَ أَبُو عَبْدِ اللَّهِ مُحَمَّدُ بْنُ دَاوُدَ الصَّنْهَاجِيُّ",
        latin: "Qala Abu Abdullah Muhammad bin Dawud as-Sanhaji",
        terjemah: "Berkata Abu Abdullah Muhammad bin Dawud as-Sanhaji (penulis kitab)"
    },
    {
        id: 3,
        arabic: "الْكَلَامُ هُوَ اللَّفْظُ الْمُرَكَّبُ الْمُفِيدُ بِالْوَضْعِ",
        latin: "Al-kalamu huwal-lafzhul murakkabul mufidu bil-wa'di",
        terjemah: "Kalimat adalah lafadz yang tersusun yang memberi manfaat menurut penggunaan bahasa Arab"
    },
    {
        id: 4,
        arabic: "وَأَقْسَامُهُ ثَلَاثَةٌ: اِسْمٌ وَفِعْلٌ وَحَرْفٌ جَاءَ لِمَعْنًى",
        latin: "Wa aqsamuhu tsalatsah: ismun wa fi'lun wa harfun ja'a lima'na",
        terjemah: "Dan pembagiannya ada tiga: isim, fi'il, dan harf yang datang untuk suatu makna"
    },
    {
        id: 5,
        arabic: "فَالْإِسْمُ يُعْرَفُ بِالْخَفْضِ وَالتَّنْوِينِ وَدُخُولِ الأَلِفِ وَاللَّامِ وَالْحُرُوفِ",
        latin: "Fal-ismu yu'rafu bil-khafdi wat-tanwini wa dukhulil alifi wal-lami wal-huruf",
        terjemah: "Maka isim dikenal dengan khafdh (kasrah), tanwin, masuknya alif lam, dan huruf-huruf (jar)"
    }
];

// Data Kamus
const kamusData = [
    { term: "إِسْمٌ", definisi: "Kata benda", penjelasan: "Kata yang menunjukkan makna pada dirinya sendiri tanpa terkait waktu" },
    { term: "فِعْلٌ", definisi: "Kata kerja", penjelasan: "Kata yang menunjukkan makna pada dirinya sendiri dan terkait dengan waktu" },
    { term: "حَرْفٌ", definisi: "Kata penghubung", penjelasan: "Kata yang menunjukkan makna pada kata lain, tidak berdiri sendiri" },
    { term: "فَاعِلٌ", definisi: "Pelaku", penjelasan: "Isim yang berupa pelaku dari suatu perbuatan, marfu' dengan dhommah" },
    { term: "مَفْعُولٌ بِهِ", definisi: "Objek", penjelasan: "Isim yang dikenai perbuatan, mansub dengan fathah" },
    { term: "مُبْتَدَأٌ", definisi: "Subjek awal", penjelasan: "Isim yang diawali kalimat, marfu' dengan dhommah" },
    { term: "خَبَرٌ", definisi: "Predikat", penjelasan: "Keterangan tentang mubtada', marfu' dengan dhommah" },
    { term: "مَرْفُوعٌ", definisi: "Dhommah", penjelasan: "Tanda i'rab isim dengan harakat dhommah (ُ)" },
    { term: "مَنْصُوبٌ", definisi: "Fathah", penjelasan: "Tanda i'rab isim dengan harakat fathah (َ)" },
    { term: "مَجْرُورٌ", definisi: "Kasrah", penjelasan: "Tanda i'rab isim dengan harakat kasrah (ِ)" },
    { term: "مَعْرِفَةٌ", definisi: "Isim ma'rifah", penjelasan: "Isim yang ditentukan, diawali dengan alif lam (ال)" },
    { term: "نَكِرَةٌ", definisi: "Isim nakirah", penjemah: "Isim yang tidak ditentukan, bertanwin" },
    { term: "مُضَافٌ", definisi: "Yang bersandung", penjelasan: "Isim yang bersandung kepada isim lain" },
    { term: "مُضَافٌ إِلَيْهِ", definisi: "Tempat bersandung", penjelasan: "Isim yang menjadi tempat bersandung, majrur" },
    { term: "تَنْوِينٌ", definisi: "Nunnation", penjelasan: "Nun sukun yang ditambahkan di akhir isim nakirah (ٌ ٍ ً)" }
];

// Data Quiz per Bab
const quizData = {
    1: [
        { soal: "Apa definisi kalimat menurut ilmu nahwu?", pilihan: ["Lafadz tunggal", "Lafadz yang tersusun dan memberi manfaat", "Huruf hijaiyah", "Kata kerja saja"], jawaban: 1, penjelasan: "Kalimat adalah lafadz yang tersusun (murakkab) yang memberi manfaat (mufid)." },
        { soal: "Berapa rukun kalimat?", pilihan: ["2", "3", "4", "5"], jawaban: 1, penjelasan: "Rukun kalimat ada 3: lafadz, tarkib (tersusun), dan ifadah (memberi manfaat)." },
        { soal: "Manakah yang termasuk kalimat sempurna?", pilihan: ["قَامَ", "زَيْدٌ", "قَامَ زَيْدٌ", "فِي"], jawaban: 2, penjelasan: "قَامَ زَيْدٌ adalah kalimat sempurna karena memiliki fi'il (قَامَ) dan fa'il (زَيْدٌ)." },
        { soal: "Apa yang dimaksud dengan اللَّفْظُ?", pilihan: ["Makna", "Suara yang mengandung huruf hijaiyah", "Kalimat", "Waktu"], jawaban: 1, penjelasan: "Lafadz adalah suara yang mengandung huruf hijaiyah yang bisa diucapkan." }
    ],
    2: [
        { soal: "Berapa pembagian kalam menurut Jurumiyah?", pilihan: ["2", "3", "4", "5"], jawaban: 1, penjelasan: "Kalam dibagi menjadi 3: isim, fi'il, dan harf." },
        { soal: "Apa ciri utama isim?", pilihan: ["Terkait dengan waktu", "Tidak terkait dengan waktu", "Selalu bergerak", "Berupa perintah"], jawaban: 1, penjelasan: "Isim tidak terkait dengan waktu (lam yaqtarin biz-zaman)." },
        { soal: "Manakah yang termasuk fi'il?", pilihan: ["كِتَابٌ", "مُحَمَّدٌ", "كَتَبَ", "فِي"], jawaban: 2, penjelasan: "كَتَبَ adalah fi'il (kata kerja) yang menunjukkan perbuatan menulis." },
        { soal: "Apa fungsi harf?", pilihan: ["Sebagai subjek", "Menghubungkan atau memberi makna pada kata lain", "Sebagai objek", "Sebagai keterangan"], jawaban: 1, penjelasan: "Harf berfungsi memberi makna pada kata lain (isim) setelahnya." }
    ],
    3: [
        { soal: "Berapa tanda isim menurut Jurumiyah?", pilihan: ["3", "4", "5", "6"], jawaban: 1, penjelasan: "Isim memiliki 4 tanda: qabul bit-tanwin, dukhul alif lam, al-isnad ilaih, dan dukhul huruf jar." },
        { soal: "Apa yang dimaksud dengan tanwin?", pilihan: ["Alif lam", "Nun sukun di akhir isim", "Kasrah ganda", "Dhommah tunggal"], jawaban: 1, penjelasan: "Tanwin adalah nun sukun yang ditambahkan di akhir isim nakirah." },
        { soal: "Manakah contoh isim dengan alif lam?", pilihan: ["رَجُلٌ", "الرَّجُلُ", "رَجُلًا", "فِي"], jawaban: 1, penjelasan: "الرَّجُلُ memiliki alif lam (ال) di awalnya, menunjukkan isim ma'rifah." }
    ]
};

// ==========================================
// STATE MANAGEMENT
// ==========================================

let currentUser = null;
let userProgress = {
    xp: 0,
    level: 1,
    completedBabs: [],
    quizScores: {}
};

let currentQuiz = null;
let currentQuestion = 0;
let quizScore = 0;
let audioEnabled = true;
let darkMode = false;
let latinMode = false;

// ==========================================
// INITIALIZATION
// ==========================================

document.addEventListener('DOMContentLoaded', () => {
    loadUserData();
    initApp();
});

function initApp() {
    renderBabList();
    renderKitab();
    renderKamus();
    renderQuizSelection();
    
    // Check saved preferences
    const savedDark = localStorage.getItem('darkMode') === 'true';
    if (savedDark) toggleDarkMode();
    
    const savedAudio = localStorage.getItem('audioEnabled');
    if (savedAudio !== null) audioEnabled = savedAudio === 'true';
}

// ==========================================
// AUTHENTICATION
// ==========================================

function login() {
    const username = document.getElementById('username').value;
    const password = document.getElementById('password').value;
    
    if (!username || !password) {
        showToast('Mohon isi username dan password', 'error');
        return;
    }
    
    // Simple auth (in real app, use proper backend)
    const users = JSON.parse(localStorage.getItem('nahwuUsers') || '[]');
    const user = users.find(u => u.username === username && u.password === password);
    
    if (user || (username === 'demo' && password === 'demo')) {
        currentUser = { username, name: user?.name || username };
        localStorage.setItem('currentUser', JSON.stringify(currentUser));
        showMainApp();
        showToast('Selamat datang kembali!', 'success');
        playAudio('login');
    } else {
        showToast('Username atau password salah', 'error');
    }
}

function guestLogin() {
    currentUser = { username: 'guest', name: 'Tamu' };
    showMainApp();
    showToast('Masuk sebagai tamu', 'info');
}

function register() {
    const name = document.getElementById('regName').value;
    const username = document.getElementById('regUsername').value;
    const email = document.getElementById('regEmail').value;
    const password = document.getElementById('regPassword').value;
    
    if (!name || !username || !password) {
        showToast('Mohon lengkapi data', 'error');
        return;
    }
    
    const users = JSON.parse(localStorage.getItem('nahwuUsers') || '[]');
    
    if (users.find(u => u.username === username)) {
        showToast('Username sudah terdaftar', 'error');
        return;
    }
    
    users.push({ name, username, email, password });
    localStorage.setItem('nahwuUsers', JSON.stringify(users));
    
    showToast('Pendaftaran berhasil! Silakan login', 'success');
    showLogin();
}

function logout() {
    currentUser = null;
    localStorage.removeItem('currentUser');
    document.getElementById('mainApp').classList.remove('active');
    document.getElementById('loginScreen').classList.add('active');
    showToast('Berhasil keluar', 'info');
}

function showRegister() {
    document.getElementById('loginScreen').classList.remove('active');
    document.getElementById('registerScreen').classList.add('active');
}

function showLogin() {
    document.getElementById('registerScreen').classList.remove('active');
    document.getElementById('loginScreen').classList.add('active');
}

function showMainApp() {
    document.getElementById('loginScreen').classList.remove('active');
    document.getElementById('registerScreen').classList.remove('active');
    document.getElementById('mainApp').classList.add('active');
    
    document.getElementById('displayName').textContent = currentUser?.name || 'Santri';
    updateXPDisplay();
}

// ==========================================
// DATA PERSISTENCE
// ==========================================

function loadUserData() {
    const saved = localStorage.getItem('currentUser');
    if (saved) {
        currentUser = JSON.parse(saved);
        const progress = localStorage.getItem(`progress_${currentUser.username}`);
        if (progress) userProgress = JSON.parse(progress);
    }
    
    const savedProgress = localStorage.getItem('userProgress');
   {
  "name": "Nahwu Jurumiyah Pro",
  "short_name": "Nahwu Pro",
  "description": "Aplikasi pembelajaran ilmu nahwu kitab Jurumiyah lengkap dengan audio dan quiz",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#1f7a4c",
  "theme_color": "#1f7a4c",
  "orientation": "portrait",
  "icons": [
    {
      "src": "data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Crect fill='%231f7a4c' width='100' height='100' rx='20'/%3E%3Ctext x='50' y='70' font-size='60' text-anchor='middle' fill='white' font-family='serif'%3Eن%3C/text%3E%3C/svg%3E",
      "sizes": "192x192",
      "type": "image/svg+xml"
    }
  ]
} 
 
