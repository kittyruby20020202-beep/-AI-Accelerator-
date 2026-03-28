<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI Cloning Accelerator — 工具手冊</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@300;400;500;700&family=DM+Mono:ital,wght@0,400;0,500;1,400&family=Fraunces:ital,wght@0,300;0,600;1,300&display=swap" rel="stylesheet">
<link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><rect width='100' height='100' rx='20' fill='%230D7377'/><text y='68' x='50' text-anchor='middle' font-size='58' font-family='serif' fill='white'>工</text></svg>">
<style>
  :root {
    --bg: #F7F5F0;
    --surface: #FFFFFF;
    --surface2: #F2EFE9;
    --border: #E2DDD6;
    --text: #1C1917;
    --text-muted: #78716C;
    --accent: #0D7377;
    --accent-light: #E8F5F5;
    --accent-mid: #14A085;
    --beginner: #15803D;
    --beginner-bg: #DCFCE7;
    --intermediate: #B45309;
    --intermediate-bg: #FEF3C7;
    --advanced: #DC2626;
    --advanced-bg: #FEE2E2;
    --shadow-sm: 0 1px 3px rgba(0,0,0,0.06), 0 1px 2px rgba(0,0,0,0.04);
    --shadow-md: 0 4px 16px rgba(0,0,0,0.07), 0 2px 6px rgba(0,0,0,0.05);
    --shadow-lg: 0 12px 40px rgba(0,0,0,0.10), 0 4px 12px rgba(0,0,0,0.06);
    --radius: 12px;
    --radius-sm: 6px;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Noto Sans TC', sans-serif;
    font-weight: 400;
    min-height: 100vh;
    -webkit-font-smoothing: antialiased;
  }

  header {
    background: rgba(255,255,255,0.92);
    border-bottom: 1px solid var(--border);
    padding: 2.5rem 2rem 2rem;
    position: sticky;
    top: 0;
    z-index: 100;
    backdrop-filter: blur(12px);
  }

  .header-inner { max-width: 1100px; margin: 0 auto; }

  .header-top {
    display: flex;
    align-items: flex-end;
    gap: 1.2rem;
    margin-bottom: 1.4rem;
    flex-wrap: wrap;
  }

  header h1 {
    font-family: 'Fraunces', serif;
    font-weight: 600;
    font-size: clamp(1.5rem, 3vw, 2.1rem);
    line-height: 1.1;
    color: var(--text);
    letter-spacing: -0.02em;
  }

  header h1 span { color: var(--accent); }

  .lesson-badge {
    font-family: 'DM Mono', monospace;
    font-size: 0.68rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--text-muted);
    background: var(--surface2);
    padding: 0.3rem 0.7rem;
    border-radius: 99px;
    border: 1px solid var(--border);
    white-space: nowrap;
    margin-bottom: 0.25rem;
  }

  .search-wrap {
    position: relative;
    display: flex;
    gap: 0.75rem;
    align-items: center;
    flex-wrap: wrap;
  }

  .search-box { position: relative; flex: 1; min-width: 220px; }

  .search-icon {
    position: absolute;
    left: 0.9rem;
    top: 50%;
    transform: translateY(-50%);
    color: var(--text-muted);
    pointer-events: none;
  }

  #search {
    width: 100%;
    padding: 0.75rem 1rem 0.75rem 2.5rem;
    border: 1.5px solid var(--border);
    border-radius: var(--radius-sm);
    background: var(--surface);
    font-family: 'Noto Sans TC', sans-serif;
    font-size: 0.9rem;
    color: var(--text);
    outline: none;
    transition: border-color 0.15s, box-shadow 0.15s;
  }

  #search:focus {
    border-color: var(--accent);
    box-shadow: 0 0 0 3px rgba(13,115,119,0.12);
  }

  #search::placeholder { color: var(--text-muted); }

  .filters { display: flex; gap: 0.4rem; flex-wrap: wrap; }

  .pill {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    padding: 0.35rem 0.9rem;
    border-radius: 99px;
    border: 1.5px solid var(--border);
    background: var(--surface);
    color: var(--text-muted);
    cursor: pointer;
    transition: all 0.15s;
    white-space: nowrap;
  }
  .pill:hover { border-color: var(--accent); color: var(--accent); }
  .pill.active { background: var(--accent); border-color: var(--accent); color: #fff; }
  .pill.beginner.active { background: var(--beginner); border-color: var(--beginner); }
  .pill.intermediate.active { background: var(--intermediate); border-color: var(--intermediate); }
  .pill.advanced.active { background: var(--advanced); border-color: var(--advanced); }

  .count-bar {
    max-width: 1100px;
    margin: 1.5rem auto 0;
    padding: 0 1.5rem;
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--text-muted);
    letter-spacing: 0.04em;
  }

  main {
    max-width: 1100px;
    margin: 0 auto;
    padding: 1.25rem 1.5rem 4rem;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1rem;
  }

  .card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    overflow: hidden;
    box-shadow: var(--shadow-sm);
    transition: box-shadow 0.2s, transform 0.2s, border-color 0.2s;
    cursor: pointer;
    animation: fadeUp 0.3s ease both;
  }

  .card:hover {
    box-shadow: var(--shadow-md);
    transform: translateY(-2px);
    border-color: #C8C4BE;
  }

  .card.open {
    border-color: var(--accent);
    box-shadow: var(--shadow-lg);
    grid-column: 1 / -1;
    cursor: default;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(12px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .card-head {
    padding: 1.2rem 1.3rem 1rem;
    display: flex;
    gap: 0.8rem;
    align-items: flex-start;
  }

  .card-num {
    font-family: 'DM Mono', monospace;
    font-size: 0.68rem;
    font-weight: 500;
    color: var(--accent);
    background: var(--accent-light);
    border-radius: 4px;
    padding: 0.15rem 0.45rem;
    flex-shrink: 0;
    margin-top: 0.15rem;
    letter-spacing: 0.03em;
  }

  .card-title-wrap { flex: 1; min-width: 0; }

  .card-title {
    font-family: 'Fraunces', serif;
    font-weight: 600;
    font-size: 1.05rem;
    line-height: 1.3;
    color: var(--text);
    letter-spacing: -0.01em;
  }

  .card-timing {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    color: var(--text-muted);
    margin-top: 0.3rem;
    letter-spacing: 0.03em;
  }

  .badge {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    font-weight: 500;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    padding: 0.25rem 0.6rem;
    border-radius: 99px;
    flex-shrink: 0;
  }
  .badge-beginner     { color: var(--beginner);     background: var(--beginner-bg); }
  .badge-intermediate { color: var(--intermediate); background: var(--intermediate-bg); }
  .badge-advanced     { color: var(--advanced);     background: var(--advanced-bg); }

  .card-preview {
    padding: 0 1.3rem 1.1rem;
    font-size: 0.82rem;
    color: var(--text-muted);
    line-height: 1.6;
  }

  .card-footer {
    padding: 0.7rem 1.3rem;
    border-top: 1px solid var(--surface2);
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: var(--surface2);
  }

  .expand-hint {
    font-family: 'DM Mono', monospace;
    font-size: 0.68rem;
    color: var(--accent);
    letter-spacing: 0.04em;
    display: flex;
    align-items: center;
    gap: 0.3rem;
  }

  .chevron {
    display: inline-block;
    transition: transform 0.25s;
    font-size: 0.75rem;
  }
  .card.open .chevron { transform: rotate(180deg); }

  .card-detail { display: none; border-top: 1px solid var(--border); }
  .card.open .card-detail { display: block; }

  .detail-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 0;
  }

  .detail-section {
    padding: 1.4rem 1.5rem;
    border-right: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }
  .detail-section:last-child { border-right: none; }
  .detail-section.full { grid-column: 1 / -1; border-right: none; }

  .detail-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--accent);
    margin-bottom: 0.7rem;
    display: flex;
    align-items: center;
    gap: 0.4rem;
  }

  .detail-label::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 3px;
    border-radius: 50%;
    background: var(--accent);
  }

  .detail-text { font-size: 0.85rem; line-height: 1.7; color: var(--text); }

  .steps-list { list-style: none; display: flex; flex-direction: column; gap: 0.55rem; }

  .steps-list li {
    display: flex;
    gap: 0.7rem;
    align-items: flex-start;
    font-size: 0.84rem;
    line-height: 1.6;
    color: var(--text);
  }

  .step-num {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    font-weight: 500;
    color: var(--accent);
    background: var(--accent-light);
    border-radius: 4px;
    padding: 0.1rem 0.4rem;
    flex-shrink: 0;
    margin-top: 0.2rem;
    min-width: 1.6rem;
    text-align: center;
  }

  .prompt-box {
    background: #F8F7F3;
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent);
    border-radius: var(--radius-sm);
    padding: 1rem 1.1rem;
    font-family: 'DM Mono', monospace;
    font-size: 0.78rem;
    line-height: 1.75;
    color: #374151;
    white-space: pre-wrap;
    word-break: break-word;
  }

  .detail-close {
    padding: 0.8rem 1.5rem;
    display: flex;
    justify-content: flex-end;
    background: var(--surface);
    border-top: 1px solid var(--border);
  }

  .close-btn {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--text-muted);
    background: none;
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 0.35rem 0.9rem;
    cursor: pointer;
    transition: all 0.15s;
  }
  .close-btn:hover { border-color: var(--advanced); color: var(--advanced); }

  .empty {
    text-align: center;
    padding: 5rem 2rem;
    color: var(--text-muted);
    display: none;
  }
  .empty svg { opacity: 0.3; margin-bottom: 1rem; }
  .empty p { font-size: 0.9rem; }
  .empty strong { display: block; font-size: 1.1rem; margin-bottom: 0.4rem; color: var(--text); }

  @media (max-width: 600px) {
    header { padding: 1.5rem 1rem 1rem; }
    main { padding: 1rem 1rem 3rem; }
    .grid { grid-template-columns: 1fr; }
    .card.open { grid-column: 1; }
    .detail-grid { grid-template-columns: 1fr; }
    .detail-section { border-right: none; }
  }

  /* ── COMPLETED STATE ── */
  .card.done {
    opacity: 0.55;
    border-color: var(--beginner) !important;
    background: #FAFFF8;
  }
  .card.done .card-title {
    text-decoration: line-through;
    text-decoration-color: var(--beginner);
    text-decoration-thickness: 2px;
  }
  .card.done .card-num {
    background: var(--beginner-bg);
    color: var(--beginner);
  }
  .done-check {
    display: none;
    width: 16px;
    height: 16px;
    border-radius: 50%;
    background: var(--beginner);
    flex-shrink: 0;
    align-items: center;
    justify-content: center;
    margin-top: 0.2rem;
  }
  .done-check svg { width: 9px; height: 9px; }
  .card.done .done-check { display: flex; }
  .done-btn {
    font-family: 'DM Mono', monospace;
    font-size: 0.68rem;
    letter-spacing: 0.04em;
    color: var(--text-muted);
    background: none;
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 0.25rem 0.7rem;
    cursor: pointer;
    transition: all 0.15s;
    white-space: nowrap;
  }
  .done-btn:hover { border-color: var(--beginner); color: var(--beginner); }
  .card.done .done-btn { border-color: var(--beginner); color: var(--beginner); background: var(--beginner-bg); }

  /* ── COURSE TAGS ── */
  .course-tags {
    display: flex;
    gap: 0.35rem;
    flex-wrap: wrap;
    padding: 0.6rem 1.3rem 0.9rem;
  }
  .course-tag {
    font-family: 'DM Mono', monospace;
    font-size: 0.62rem;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    padding: 0.2rem 0.55rem;
    border-radius: 3px;
    background: var(--surface2);
    color: var(--text-muted);
    border: 1px solid var(--border);
  }
  .course-tag.l1 { background: #EEF6FF; color: #3B82F6; border-color: #BFDBFE; }
  .course-tag.l2 { background: #FFF7ED; color: #EA580C; border-color: #FDBA74; }
  .course-tag.l3 { background: #FDF4FF; color: #9333EA; border-color: #E9D5FF; }
  .course-tag.l4 { background: #ECFDF5; color: #059669; border-color: #A7F3D0; }
  .course-tag.l5 { background: #FEF9C3; color: #CA8A04; border-color: #FDE68A; }
  .course-tag.l6 { background: #FFF1F2; color: #E11D48; border-color: #FECDD3; }
  .course-tag.l7 { background: #F0FDF4; color: #16A34A; border-color: #BBF7D0; }
  .course-tag.l8 { background: #FFF7ED; color: #C2410C; border-color: #FED7AA; }
  .course-tag.l9 { background: #EFF6FF; color: #1D4ED8; border-color: #BFDBFE; }
  .course-tag.l10 { background: #FAF5FF; color: #7C3AED; border-color: #E9D5FF; }
  .course-tag.l11 { background: #F0F9FF; color: #0369A1; border-color: #BAE6FD; }
  .course-tag.l12 { background: #FDF4FF; color: #A21CAF; border-color: #F5D0FE; }

  /* ── ALT+G SHORTCUT BADGE ── */
  .shortcut-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.35rem;
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    color: var(--text-muted);
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 99px;
    padding: 0.25rem 0.7rem;
    cursor: pointer;
    transition: all 0.15s;
    white-space: nowrap;
    text-decoration: none;
  }
  .shortcut-badge:hover { border-color: var(--accent); color: var(--accent); background: var(--accent-light); }
  .shortcut-badge kbd {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 3px;
    padding: 0.05rem 0.35rem;
    font-size: 0.6rem;
    font-family: 'DM Mono', monospace;
    box-shadow: 0 1px 0 var(--border);
  }

  /* ── TOAST ── */
  .toast {
    position: fixed;
    bottom: 1.5rem;
    left: 50%;
    transform: translateX(-50%) translateY(10px);
    background: var(--text);
    color: #fff;
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    padding: 0.6rem 1.2rem;
    border-radius: 99px;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.2s, transform 0.2s;
    z-index: 999;
    white-space: nowrap;
  }
  .toast.show { opacity: 1; transform: translateX(-50%) translateY(0); }
</style>
</head>
<body>

<header>
  <div class="header-inner">
    <div class="header-top">
      <div>
        <h1>AI <span>工具手冊</span></h1>
      </div>
      <span class="lesson-badge">AI Cloning Accelerator · Lesson 1–6</span>
      <a class="shortcut-badge" id="chatgpt-link" href="https://chatgpt.com" target="_blank" title="Alt+G 開啟 ChatGPT">
        <kbd>Alt</kbd>+<kbd>G</kbd>
        <span>開啟 ChatGPT</span>
      </a>
    </div>
    <div class="search-wrap">
      <div class="search-box">
        <svg class="search-icon" width="15" height="15" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
          <circle cx="11" cy="11" r="8"/><path d="M21 21l-4.35-4.35"/>
        </svg>
        <input type="text" id="search" placeholder="搜尋工具名稱、問題描述…" autocomplete="off">
      </div>
      <div class="filters">
        <button class="pill active" data-filter="all">全部</button>
        <button class="pill beginner" data-filter="Beginner">Beginner</button>
        <button class="pill intermediate" data-filter="Intermediate">Intermediate</button>
        <button class="pill advanced" data-filter="Advanced">Advanced</button>
      </div>
    </div>
  </div>
</header>

<div class="count-bar" id="count-bar"></div>

<main>
  <div class="grid" id="grid"></div>
  <div class="empty" id="empty">
    <svg width="48" height="48" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
      <path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 15.803a7.5 7.5 0 0010.607 0z"/>
    </svg>
    <strong>找不到相符的工具</strong>
    <p>請嘗試其他關鍵字，或清除篩選條件</p>
  </div>
</main>

<div class="toast" id="toast"></div>

<script>

// ── COMPLETED STATE (localStorage) ──
const DONE_KEY = 'aia_done_ids';
function loadDone() {
  try { return new Set(JSON.parse(localStorage.getItem(DONE_KEY) || '[]')); }
  catch { return new Set(); }
}
function saveDone(set) {
  localStorage.setItem(DONE_KEY, JSON.stringify([...set]));
}
let doneIds = loadDone();

// ── TOAST ──
const toastEl = document.getElementById('toast');
let toastTimer;
function showToast(msg) {
  toastEl.textContent = msg;
  toastEl.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer = setTimeout(() => toastEl.classList.remove('show'), 2000);
}

// ── ALT+G SHORTCUT ──
document.addEventListener('keydown', e => {
  if (e.altKey && e.key.toLowerCase() === 'g') {
    e.preventDefault();
    window.open('https://chatgpt.com', '_blank');
    showToast('⚡ 開啟 ChatGPT…');
  }
});

// ── LESSON TAG CONFIG ──
const lessonMeta = {
  1: { label: 'Lesson 1', cls: 'l1' },
  2: { label: 'Lesson 2', cls: 'l2' },
  3: { label: 'Lesson 3', cls: 'l3' },
  4: { label: 'Lesson 4', cls: 'l4' },
  5: { label: 'Lesson 5', cls: 'l5' },
  6: { label: 'Lesson 6', cls: 'l6' },
  7: { label: 'Lesson 7', cls: 'l7' },
  8: { label: 'Lesson 8', cls: 'l8' },
  9: { label: 'Lesson 9', cls: 'l9' },
  10: { label: 'Lesson 10', cls: 'l10' },
  11: { label: 'Lesson 11', cls: 'l11' },
  12: { label: 'Lesson 12', cls: 'l12' },
};

const tools = [
  // ── LESSON 1–3 ──
  {
    id: 1, lessons: [1],
    name: "ChatGPT / Claude — Projects 功能",
    difficulty: "Beginner",
    timing: "Lesson 1（通訊分身建立）",
    problem: "每次開新對話都要重新說明背景，AI 不記得你是誰、你的語氣風格、你的產品",
    situation: "想建立「溝通分身」，讓 AI 長期記住你的風格、幫你持續產生內容",
    steps: [
      "在 ChatGPT 側邊欄找到「Projects」→ 點「New Project」",
      "在 Claude 側邊欄點「Projects」圖示 → 點「New Project」",
      "為專案命名（例如：My Communication Clone）",
      "在「Files」區塊上傳你的知識文件（.txt 或 .md 格式）",
      "在「Instructions」區塊輸入系統提示詞（角色定義、行為規則）",
      "在此專案下開始對話，AI 每次都會自動套用設定"
    ],
    prompt: `You are [你的名字]'s communication clone. Use the uploaded files to write content that matches their exact tone of voice, teaching style, and brand values. Always ask clarifying questions before generating content.`
  },
  {
    id: 2, lessons: [1],
    name: "Voice Profile 語氣文件建立",
    difficulty: "Beginner",
    timing: "Lesson 1（通訊分身建立）",
    problem: "AI 寫出來的內容聽起來不像你，太正式、太生硬，或風格不一致",
    situation: "需要讓 AI 產生完全符合你個人語氣的文章、腳本、社群貼文",
    steps: [
      "打開 ChatGPT 或 Claude（當作「AI 教師」）",
      "輸入：「我要建立一個語氣分析文件，請準備好接收我的樣本內容」",
      "貼上你的書籍章節、部落格、演講逐字稿或 YouTube 影片字幕",
      "請 AI 分析並產出語氣側寫（列出你慣用詞、句型、節奏等）",
      "將結果複製到 Google Doc，下載為 .txt 檔",
      "上傳到你的 Project 作為知識文件"
    ],
    prompt: `請分析以下內容，建立這位講者/作者的語氣側寫（Voice Profile）。包含：慣用詞彙、避免的詞彙、句子長度習慣、說故事方式、開場模式、情緒節奏。輸出為可直接存成文件的格式。`
  },
  {
    id: 3, lessons: [1, 4],
    name: "Whisper Flow — 語音輸入工具",
    difficulty: "Beginner",
    timing: "Lesson 1（工具介紹段落）",
    problem: "打字輸入 AI 提示詞太慢，或不擅長用文字精確描述需求",
    situation: "想用說的方式和 AI 溝通，尤其在移動中、開車時、帶小孩時",
    steps: [
      "前往 wispr.flow.ai 下載安裝",
      "設定快捷鍵（按住即可開始語音輸入）",
      "在任何 AI 對話框中使用，說完自動轉文字",
      "說話可以有「嗯」「啊」，AI 會自動理解意思",
      "進階：在 Whisper 的 Dictionary 設定自訂詞庫，加入品牌名、人名、工具名，提升辨識準確率"
    ],
    prompt: `（此工具本身是輸入媒介，與其他 Prompt 搭配使用。不需要特定 Prompt——說出你的需求即可。）`
  },
  {
    id: 4, lessons: [1],
    name: "PDF to Text 格式轉換",
    difficulty: "Beginner",
    timing: "Lesson 1（文件準備段落）",
    problem: "上傳 PDF 給 AI 速度慢，AI 處理效率低，容量也佔用大",
    situation: "有書稿、講義、課程 PDF 想上傳到 AI Project，需先轉換格式",
    steps: [
      "Google 搜尋「PDF to text converter」",
      "上傳你的 PDF 檔案，下載轉換後的 .txt 文字檔",
      "或：將任何網頁文字複製，貼入新 Google Doc",
      "在 Google Doc：點「檔案」→「下載」→「純文字 (.txt)」",
      "將 .txt 檔上傳至 AI Project 的 Files 區塊"
    ],
    prompt: `（此步驟為前置作業，無需特定 Prompt）`
  },
  {
    id: 5, lessons: [2],
    name: "Suno — AI 音樂生成",
    difficulty: "Beginner",
    timing: "Lesson 2（開場音樂示範）",
    problem: "想為課程或內容加入客製化的歌曲或背景音樂，但沒有音樂製作能力",
    situation: "Vykintas 在每堂課前用 Suno 生成一首根據當天主題的歌曲，增加記憶點",
    steps: [
      "前往 suno.com 註冊帳號",
      "輸入歌曲描述（主題、風格、歌詞方向）",
      "AI 自動生成歌曲（含人聲），可選擇不同版本",
      "下載使用或直接分享連結"
    ],
    prompt: `請生成一首關於「AI 溝通分身」的歌曲，風格為現代流行電子樂。歌詞需包含：克服對 AI 的恐懼、用 AI 放大自己的聲音、建立數位分身等主題。語氣積極正向，節奏感強。`
  },
  {
    id: 6, lessons: [2, 4],
    name: "Deep Research（深度研究）",
    difficulty: "Intermediate",
    timing: "Lesson 2–4（支援課 Q&A 段落）",
    problem: "不知道某個領域的最佳實踐，或需要快速建立高品質的 DNA 知識文件",
    situation: "剛起步的獨立工作者，需要建立 Email 自動回覆、VSL 腳本、社群貼文等的標準文件",
    steps: [
      "在 ChatGPT 對話框點擊「+」→ 選擇「Deep Research」",
      "輸入你的研究需求（例如：建立 Email 自動回覆序列的標準文件）",
      "AI 會先詢問你幾個釐清問題，請認真回答",
      "AI 開始深度搜尋（需等待 10–20 分鐘，最多可執行 242 次搜尋）",
      "進階：點擊「Sites」按鈕，可指定特定網站作為研究來源",
      "進階：在「Apps」中選擇 Gmail、Airtable 等，讓 Deep Research 也搜尋你的私人資料",
      "取得長篇研究報告後，複製到 Google Doc 存成 .txt，上傳到 AI Project"
    ],
    prompt: `幫我建立一份 Email Autoresponder 的 DNA 標準文件，確保內容具高轉換率。在開始研究前，先問我問題深入了解我的狀況，包含：目標受眾、品牌語氣、Email 目標、使用平台、成效指標等，讓研究結果真正符合我的情境。`
  },
  {
    id: 7, lessons: [1, 2],
    name: "AI 雙開法（Tutor + Project 並行）",
    difficulty: "Intermediate",
    timing: "Lesson 1–2（建立溝通分身的方法論）",
    problem: "不知道該如何設計 AI Project 的指令、要上傳哪些文件",
    situation: "建立溝通分身或任何 AI Clone 的初始設定階段，需要有人引導",
    steps: [
      "開啟第一個 AI 視窗（「AI 教師」）：用來詢問如何設計 Project",
      "開啟第二個 AI 視窗（「AI Project」）：實際建立你的 Clone",
      "在 AI 教師中問：「我要建立 [用途] 的 Claude Project，建議我上傳哪些知識文件？」",
      "根據建議，用 AI 教師幫你從現有素材生成各種文件",
      "將生成的文件（.txt）上傳到第二個視窗的 Project"
    ],
    prompt: `我正在建立一個 Claude Project，用來幫我製作線上課程。請問我應該準備哪些知識文件上傳？（我已有的素材：演講逐字稿、兩本書、行事曆素材）請給我具體建議，並說明每份文件的用途。`
  },
  {
    id: 8, lessons: [2, 4],
    name: "Project Instructions 生成",
    difficulty: "Intermediate",
    timing: "Lesson 2–4（步驟七；Markdown 輸出技巧）",
    problem: "不知道怎麼寫 Project 的系統提示詞（Instructions），自己寫的效果很差",
    situation: "建立 AI Clone 的最後一步：設定 AI 應該如何運作的核心指令",
    steps: [
      "在「AI 教師」視窗輸入下方 Prompt",
      "回答 AI 提出的釐清問題（目標、風格、限制、受眾等）",
      "要求 AI 將 Instructions 輸出在 Code Block（Markdown 格式）內，方便一鍵複製",
      "複製貼到 ChatGPT Project 或 Claude Project 的 Instructions 欄位",
      "測試效果；若不滿意可回饋給 AI 教師，請它迭代改善"
    ],
    prompt: `我想建立一個 AI 溝通分身作為 Claude Project。在撰寫任何 Instructions 之前，請先不要生成內容。你的任務是找出最重要的變數、限制與決策，整理成清楚的分類，然後逐一向我提問，確保充分理解我的情境後，再生成高度客製化的 Instructions。請在最後將 Instructions 輸出在 code block 中，格式為 Markdown。`
  },
  {
    id: 9, lessons: [2, 4],
    name: "Gmail / Outlook 整合",
    difficulty: "Intermediate",
    timing: "Lesson 2–4（Q&A 段落：如何連接 Email）",
    problem: "想讓 AI 幫你整理信箱、摘要特定信件，或從 Email 中提取行動事項",
    situation: "希望 AI Clone 能主動查閱你的 Email，協助追蹤任務與溝通",
    steps: [
      "ChatGPT：前往 chatgpt.com/apps → 搜尋 Gmail 或 Outlook → 點擊連接",
      "Claude：點左側「+」→「Connectors」→「Browse Connectors」→ 連接 Gmail",
      "連接後，可在對話中直接請 AI 找特定信件或摘要 Email",
      "進階：在對話框輸入 @ 符號，可叫出你的 Communication Clone Project，讓 AI 用你的語氣草擬回信",
      "注意：目前 AI 只能「讀取」，無法代為「發送」Email"
    ],
    prompt: `請去我的 Gmail 信箱，找出過去 7 天所有與「[專案名稱]」相關的信件，整理成摘要，並列出所有待辦行動事項，依緊急程度排序。完成後，@我的通訊分身 Project，依照我的語氣草擬每封信的回覆。`
  },
  {
    id: 10, lessons: [1],
    name: "VSL 腳本生成器",
    difficulty: "Advanced",
    timing: "Lesson 1（VSL 生成器示範）",
    problem: "製作 YouTube 銷售廣告腳本耗時，且很難同時符合個人語氣與高轉換邏輯",
    situation: "要製作銷售型 YouTube 廣告，希望 AI 根據你的書或課程自動生成腳本",
    steps: [
      "建立一個新的 Claude Project（例如：VSL 生成器）",
      "上傳文件：① 語氣側寫 ② 過去成功廣告的逐字稿分析 ③ 轉換原則文件",
      "將書稿或課程逐字稿轉成 .txt 後上傳",
      "在 Project 對話中輸入 Prompt，指定目標受眾與廣告長度",
      "取得腳本後，可繼續用語音或文字迭代修改"
    ],
    prompt: `請根據我上傳的書稿，幫我寫一支 7 分鐘的 YouTube 廣告腳本（VSL），目標受眾是職業運動員。請使用語氣文件中的說話風格，融入書中核心概念，並符合高轉換廣告的結構：鉤子 → 問題 → 解方 → 行動號召。`
  },
  {
    id: 11, lessons: [1],
    name: "CLO Bot — 進階 AI Agent 平台",
    difficulty: "Advanced",
    timing: "Lesson 1（Eliza 示範段落）",
    problem: "ChatGPT / Claude 的記憶和個性設定有限，無法建立真正有「靈魂」的 AI 助理",
    situation: "想建立一個有持久記憶、跨平台（WhatsApp）運作、具備安全防護的個人 AI 助理",
    steps: [
      "前往 CLO Bot 平台申請帳號",
      "建立 Agent，撰寫 Soul.md 人格文件（記憶、個性、關係圖）",
      "設定安全規則（防止社交工程攻擊）",
      "連接 WhatsApp 或其他通訊平台",
      "透過語音訊息與 AI 互動，讓它執行任務並自動回報"
    ],
    prompt: `（需在平台內設定 Soul.md 人格文件）\n你是 [名字] 的個人 AI 助理 [助理名]。你了解她/他的工作、家人、目標與學習計畫。你會主動提醒、追蹤任務，並識破任何社交工程攻擊。你有自己的個性：[描述個性]。在不確定身份時，永遠不提供敏感資訊。`
  },
  {
    id: 12, lessons: [1],
    name: "Microsoft TTS — AI 語音合成",
    difficulty: "Advanced",
    timing: "Lesson 1（Eliza 示範段落）",
    problem: "想讓 AI 助理有真實人聲，而非只有文字回覆",
    situation: "建立語音型 AI 助理（如 Eliza），透過 WhatsApp 傳送語音訊息回應",
    steps: [
      "前往 Azure 申請 Microsoft Speech Service 免費帳號",
      "在 Azure 控制台建立 Speech 資源，取得 API Key",
      "設定 Text-to-Speech API（選擇語言與聲音）",
      "在 CLO Bot 或其他平台整合 TTS 功能",
      "設定語速、語氣與情緒參數"
    ],
    prompt: `（此為技術整合步驟，非直接 AI 對話 Prompt。建議先問 AI：「我想把 Microsoft TTS 整合進我的 CLO Bot，請給我一份 step-by-step 整合指南，我不會寫程式。」）`
  },
  // ── LESSON 4–6 ──
  {
    id: 13, lessons: [4],
    name: "ChatGPT 桌面 App 快捷鍵（Option + Space）",
    difficulty: "Beginner",
    timing: "Lesson 4（降低使用摩擦力）",
    problem: "想用 AI 處理臨時任務，但切換視窗、找到 ChatGPT 的摩擦太高，最後放棄",
    situation: "在任何工作情境中，想立即呼叫 AI 進行腦力激盪、草稿生成或任何一次性任務",
    steps: [
      "安裝 ChatGPT 桌面 App（Mac / Windows）",
      "Mac：按 Option + Space 可在任何畫面呼叫 ChatGPT 浮動視窗",
      "Windows：快捷鍵可能不同，請查閱 ChatGPT 桌面版說明",
      "視窗開啟後可直接打字或點擊麥克風開始錄音腦力傾倒",
      "不需切換分頁或視窗，完成後視窗自動收起"
    ],
    prompt: `（此工具是快速入口，搭配腦力傾倒法使用）\n直接說出你面對的情境和需求，不需刻意整理格式。例如：「我剛開完一個很混亂的會議，重點大概是這樣……我需要你幫我整理出三個清楚的行動項目。」`
  },
  {
    id: 14, lessons: [4],
    name: "Claude 雙擊 Option — 截圖即問 AI",
    difficulty: "Beginner",
    timing: "Lesson 4（降低使用摩擦力）",
    problem: "看到畫面上有東西想問 AI，但需要截圖、存檔、上傳，步驟太繁瑣",
    situation: "瀏覽器、應用程式、任何畫面上有內容想立即請 AI 分析或解釋",
    steps: [
      "安裝 Claude 桌面 App（Mac）",
      "在任何畫面按兩下 Option 鍵，喚出 Claude 浮動視窗",
      "用滑鼠拖曳想截取的區域，自動附加為圖片訊息",
      "直接輸入或說出問題，Claude 會根據截圖畫面回答",
      "Windows 版快捷鍵請查閱 Claude 桌面版說明"
    ],
    prompt: `（直接拖曳截圖後輸入問題即可，例如：「這個錯誤訊息是什麼意思？」「幫我解釋這張圖表」「根據這個畫面，我下一步應該怎麼做？」）`
  },
  {
    id: 15, lessons: [4],
    name: "ChatGPT Browser Extension（瀏覽器擴充）",
    difficulty: "Beginner",
    timing: "Lesson 4（降低使用摩擦力）",
    problem: "在網頁上看到文章或 YouTube 影片，想讓 AI 分析，但要複製貼上內容很麻煩",
    situation: "瀏覽 YouTube、部落格、Gmail 等網頁時，想立即讓 AI 讀取當前頁面內容",
    steps: [
      "安裝 ChatGPT 瀏覽器擴充套件（Chrome）",
      "瀏覽任何網頁時，點擊右上角 ChatGPT 圖示",
      "AI 自動讀取當前頁面（包含 YouTube 字幕）作為背景脈絡",
      "直接輸入問題，不需複製貼上頁面內容",
      "在 Gmail 中：點擊 OpenAI 小圖示，可用 AI 草擬信件或轉換成 LinkedIn 貼文等"
    ],
    prompt: `（在目標網頁上開啟後直接提問。範例：「幫我整理這支影片的三大重點」「把這封 Email 改寫成 LinkedIn 貼文」「這篇文章的作者核心論點是什麼？」）`
  },
  {
    id: 16, lessons: [4],
    name: "會議逐字稿 Project（系列會議智慧庫）",
    difficulty: "Intermediate",
    timing: "Lesson 4（Finance Airtable 案例示範）",
    problem: "跨部門反覆開會卻沒有進展，每次都要重新說明背景，解決方案無法累積",
    situation: "針對一個持續進行中的複雜專案（如系統建置、跨部門協作），需要 AI 作為「持續參與的團隊成員」",
    steps: [
      "在 Google Meet / Teams / Zoom 等平台開啟自動轉錄功能",
      "會議結束後，下載逐字稿為 .txt 格式",
      "在 ChatGPT 或 Claude 建立一個專屬 Project（例如：Finance System 2025）",
      "將第一次會議逐字稿上傳為知識文件",
      "每次新會議後，將新逐字稿繼續上傳進同一個 Project",
      "在 Project 對話中可隨時詢問：進度摘要、尚未解決的問題、溝通建議等"
    ],
    prompt: `請根據我上傳的所有會議逐字稿，整理出：① 目前已達成共識的決定 ② 尚未解決的關鍵問題 ③ 各方立場差異 ④ 建議的下一步行動。請用清楚的條列格式輸出，並標注每個結論來自哪一次會議。`
  },
  {
    id: 17, lessons: [4],
    name: "SANE 選擇框架 — 會議轉錄工具選擇器",
    difficulty: "Beginner",
    timing: "Lesson 4（Granola 示範與工具比較）",
    problem: "會議轉錄工具太多（Granola、Otter.ai、Fireflies、Google Meet 原生等），不知道選哪個",
    situation: "想開始使用 AI 轉錄會議，但各平台功能差異讓人難以下手",
    steps: [
      "S（Source）：你的會議都在同一個平台嗎（如 Google Meet），還是跨平台？→ 若單一平台，用原生轉錄即可",
      "A（Attendance）：你想轉錄自己不在場的會議嗎？→ 若是，選有 Bot 的工具（Otter.ai / Fireflies）",
      "N（Needed Destination）：轉錄稿要自動儲存到哪裡？（Google Drive / ChatGPT / Notion）→ 確認工具有對應整合",
      "E（Economics）：現有方案夠用嗎？→ Google Meet 已有免費轉錄，Granola 付費但功能更豐富",
      "還需考慮：你使用的語言是否被工具支援？可將以上條件丟給 AI，請它推薦最適合你的工具"
    ],
    prompt: `根據 SANE 框架幫我選擇最適合的會議轉錄工具。我的情況是：[描述你的會議平台、是否需要錄不在場的會議、想要整合哪些工具、預算限制、使用語言]。請依此分析並給出具體建議。`
  },
  {
    id: 18, lessons: [5],
    name: "Higgs Field — AI 圖像生成（角色一致性）",
    difficulty: "Intermediate",
    timing: "Lesson 5（AI 內容創作工作流）",
    problem: "用 AI 生成自己或角色的圖片，每次風格都不一樣，無法維持一致的視覺形象",
    situation: "想建立 AI 分身或虛擬人物形象，用於社群媒體、課程、品牌內容，需要穩定的角色外觀",
    steps: [
      "前往 Higgs Field（higgsfield.ai）註冊帳號",
      "選擇 Image → Create Image，模型選 Nano Banana Pro（最真實）",
      "比例選 9:16 或 3:4（限動），4K 畫質，一次生成 4 張",
      "點擊加號上傳 2–3 張自己的高清照片（不同角度），輸入角色描述 Prompt，生成角色卡（Character Sheet）",
      "對滿意的角色卡點「Reference」，將其設為後續所有圖片的參考圖，確保外觀一致",
      "每次生成新場景圖時，將角色卡作為 Reference Image 上傳，只需改變場景描述 Prompt"
    ],
    prompt: `Create a professional character sheet for a female/male content creator. She/He appears to be in her/his mid-30s, with [描述髮色、髮型、膚色、眼睛顏色]. Show 4 different angles: front, 3/4 view, side profile, and slight downward angle. Studio lighting, clean white background, photorealistic, 8K quality. Nano Banana Pro model.`
  },
  {
    id: 19, lessons: [5],
    name: "ElevenLabs — AI 語音克隆與設計",
    difficulty: "Intermediate",
    timing: "Lesson 5（AI 內容創作工作流）",
    problem: "想讓影片有自己的聲音，但每次都要親自錄音，費時費力且不一致",
    situation: "建立 AI 影片內容流水線，需要穩定、高品質的 AI 語音，用於配音或自動生成",
    steps: [
      "前往 elevenlabs.io，選擇「Voice Design」（設計新聲音）或「Voice Cloning」（克隆你的聲音）",
      "Voice Cloning：上傳至少 2–5 分鐘的你說話音訊（建議說話自然，非念稿）",
      "生成後存入「My Voices」，進入「Text to Speech」頁面",
      "選擇語音模型：11 V3（最自然，支援情緒標籤）",
      "在腳本中加入情緒標籤如 [laughs]、[sighs]、[fast conversational] 增加自然感",
      "每個腳本至少生成 5 個版本，從中挑選最自然的一個",
      "下載 MP4 音訊備用，準備上傳到 HeyGen"
    ],
    prompt: `（用在 ChatGPT 生成腳本的 Prompt）\n請幫我寫一段 15–22 秒的 Podcast 風格口語腳本，主題是：[你的主題]。風格要非常對話感，像是在跟朋友聊天，不像是在念稿。句子要短，偶爾用「嗯」「你知道嗎」「說真的」等語助詞。適當位置加入情緒標籤如 [laughs] [sighs]。`
  },
  {
    id: 20, lessons: [5, 6],
    name: "HeyGen — AI 說話頭像影片生成",
    difficulty: "Intermediate",
    timing: "Lesson 5–6（AI 內容創作工作流）",
    problem: "有 AI 形象圖和語音，但不知道怎麼合成成真實感的說話影片",
    situation: "要生成可直接發佈到社群的 AI 說話頭像影片，不需要拍攝，不需要出鏡",
    steps: [
      "前往 heygen.com，點擊「Create Video」→ 選擇「Photo to Video」",
      "上傳從 Higgs Field 生成的角色圖（建議：肩膀以上特寫，越近越自然）",
      "上傳 ElevenLabs 生成的 MP4 語音檔",
      "進階設定（Advanced）：選擇「Calm and Composed」預設動作，或留空讓 AI 自動判斷",
      "點擊 Generate，等待影片生成（建議一次生成 2 個版本比較）",
      "如果動作太誇張，重新生成時在進階設定加入：minimal head movement, no hand gestures",
      "最終影片下載後，到手機的 Captions App 加字幕，完成發布"
    ],
    prompt: `（進階動作提示詞範例）\nMaintain a steady, calm gaze. Expression warm and approachable. Minimal head movement. Subtle eye movements only. No hand gestures. Speaking pace feels natural and conversational.`
  },
  {
    id: 21, lessons: [6],
    name: "Notebook LM — 來源基礎 AI 問答",
    difficulty: "Intermediate",
    timing: "Lesson 6（Q&A 幻覺問題解法）",
    problem: "用 Claude / ChatGPT 分析會議或文件，AI 會混入自己的訓練資料和幻覺，輸出不可信",
    situation: "需要 AI 嚴格根據你提供的文件回答，不允許 AI 自由發揮或引入外部資訊",
    steps: [
      "前往 notebooklm.google.com，以 Google 帳號登入",
      "建立新 Notebook，上傳來源文件（PDF、TXT、Google Doc、YouTube 連結等）",
      "在右側聊天框直接提問，AI 只會根據你上傳的來源回答",
      "每個回答都可以點擊引用，確認來自哪段原文",
      "特別適合：會議紀錄分析、課程內容問答、研究報告整理"
    ],
    prompt: `根據上傳的所有資料，告訴我：[你的問題]。請只引用文件中實際出現的內容，並標注每個論點來自哪份文件的哪個部分。若文件中沒有相關資訊，請直接說明，不要自行補充。`
  },
  {
    id: 22, lessons: [6],
    name: "ChatGPT Custom GPT vs Projects — 選擇指南",
    difficulty: "Intermediate",
    timing: "Lesson 6（Custom GPT 與 Projects 差異說明）",
    problem: "搞不清楚什麼時候用 Custom GPT、什麼時候用 Projects，兩個好像很像又不一樣",
    situation: "要建立 AI 助理時，需要判斷哪種架構最適合你的使用情境",
    steps: [
      "用 Projects 的情況：① 需要長期追蹤進度的專案 ② 多人協作同一個 AI 助理 ③ 需要跨對話記憶 ④ 想用「資料夾」管理相關對話",
      "用 Custom GPT 的情況：① 單一功能的專業工具（例如：只做多角度分析） ② 想分享給別人使用 ③ 需要 API Actions 連接外部服務",
      "關鍵差異：Custom GPT 可在對話中用 @ 方式呼叫，可多個 GPT 並用；Projects 是資料夾，重在累積和協作",
      "實用技巧：在任何 ChatGPT 對話中，輸入 @ 可叫出已建立的 Custom GPT 或 Project，無需切換介面",
      "記憶設定：在 Project 設定中可選「Default」（全帳戶記憶）或「Project Only」（僅限本專案記憶）"
    ],
    prompt: `我有這些 AI 助理需求：[列出你的需求]。請幫我分析每個需求應該用 Custom GPT 還是 ChatGPT Projects 來實現，並說明原因和設計建議。`
  },
  {
    id: 23, lessons: [6],
    name: "AI 圖像遮罩修圖（Inpainting）",
    difficulty: "Beginner",
    timing: "Lesson 6（Q&A 修圖示範）",
    problem: "AI 生成的圖片有某個局部不對（多一根手指、多餘物件、細節錯誤），但整體很好",
    situation: "不想重新生成整張圖，只想修改特定區域",
    steps: [
      "在 ChatGPT 開啟生成好的圖片",
      "點擊「Select Area」（遮罩工具），用滑鼠拖曳圈選要修改的區域",
      "在對話框輸入修改指令（例如：remove the microphone、fix the fingers to have 5 fingers）",
      "送出後 AI 只重新生成被圈選的區域，其餘保持不變",
      "Higgs Field 也支援類似功能：在圖片上點擊「Reference」後可描述局部修改"
    ],
    prompt: `（圈選區域後輸入）\nRemove [要移除的物件]. Ensure the result blends naturally with the surrounding area. Maintain the same lighting, style, and texture.`
  },
  {
    id: 24, lessons: [6],
    name: "11 Labs Dubbing Studio — AI 影片配音翻譯",
    difficulty: "Advanced",
    timing: "Lesson 6（語音克隆延伸應用）",
    problem: "有現成影片想翻譯成其他語言，但重新錄音費時費力，外包配音成本高",
    situation: "有課程、行銷影片、YouTube 內容想快速本地化到多個語言市場",
    steps: [
      "前往 elevenlabs.io → 點擊「Dubbing Studio」",
      "上傳影片檔案或貼上 YouTube 連結",
      "選擇目標翻譯語言（支援多語言同時輸出）",
      "AI 自動識別說話者、翻譯字幕、用克隆語音配音，並同步嘴型",
      "可手動編輯翻譯後的字幕和語氣，重新生成特定片段",
      "下載成品，聲音保留原說話者的語調與情緒"
    ],
    prompt: `（此為平台操作流程，無需文字 Prompt。建議先測試短片段，確認音質和嘴型同步效果後，再處理完整影片。）`
  },

  // ── LESSON 7–12 ──
  {
    id: 25, lessons: [7],
    name: "Google Notebook LM — 學習克隆",
    difficulty: "Beginner",
    timing: "Lesson 7（學習克隆）",
    problem: "資訊量爆炸，三小時的 Podcast 沒時間聽完，課程筆記讀了也記不住，學習效率極低",
    situation: "想把任何外部內容（Podcast、課程、書籍）快速轉化為個人化的學習資源",
    steps: [
      "前往 notebooklm.google.com，登入 Google 帳號",
      "點「New Notebook」，上傳來源（YouTube 連結、PDF、Google Doc、文字逐字稿）",
      "Notebook LM 自動產出摘要、重點問答、心智圖",
      "點「Audio Overview」生成兩人對話 Podcast，可下載後以 2x 速度收聽",
      "點「Slide Deck」或「Infographic」生成視覺化學習材料",
      "在筆記本右下角輸入個人目標（如 Lifebook 健康目標），讓 AI 將內容個人化給你"
    ],
    prompt: `（Notebook LM 是互動式筆記本，直接在介面中操作。建議提示：「這是我的目標：[貼入目標]。請分析這份逐字稿，告訴我對我最重要的一個洞見，並給我一個 5 分鐘的實踐方法。」）`
  },
  {
    id: 26, lessons: [7],
    name: "Notebook LM 互動式 Podcast 模式",
    difficulty: "Intermediate",
    timing: "Lesson 7（學習克隆）",
    problem: "AI 生成的 Podcast 聽久了會覺得公式化，缺乏真實對話感，學習效果遞減",
    situation: "想透過主動提問、反駁來加深學習，而不只是被動聆聽",
    steps: [
      "在 Notebook LM 生成 Audio Overview 後，點選「Interactive Mode」",
      "在 Podcast 播放中，直接開口說話（麥克風需開啟）",
      "提問、反駁或要求深挖某個觀點，AI 主持人會即時回應",
      "例如：「你剛才說 Joe Dispenza 具有爭議性，為什麼？」",
      "互動討論可加深記憶，比純被動聆聽提升 3–5 倍學習保留率",
      "結束後可在筆記本中保存對話重點"
    ],
    prompt: `（互動 Podcast 模式在 Notebook LM 介面中直接操作，無需文字提示。核心技巧：主動質疑 AI 的說法，例如「我不同意，因為...」或「能否舉出我能今天就應用的例子？」）`
  },
  {
    id: 27, lessons: [7, 8],
    name: "Notebook LM 個人化學習系統",
    difficulty: "Intermediate",
    timing: "Lesson 7–8（學習克隆）",
    problem: "每次學習都是通用的，聽的 Podcast 或讀的文章和自己的實際目標脫節，難以應用",
    situation: "想把 Lifebook 目標、個人願景與外部知識（Podcast、書籍）整合成個人化課程",
    steps: [
      "針對 Lifebook 的每個生命領域建立獨立 Notebook（如「健康」、「關係」、「財務」）",
      "將相關主題的 Podcast 逐字稿、YouTube 字幕、書籍摘要加入對應 Notebook",
      "上傳你的 Lifebook 目標文件（可下載為 .txt 後上傳）",
      "提示：「分析我的目標與這些內容，找出最重要的一個我必須整合的洞見」",
      "生成個人化 Audio Overview，讓 AI 以你的目標為濾鏡重新詮釋內容",
      "每週更新 Notebook，加入新學到的內容，形成動態知識庫"
    ],
    prompt: `在這個 Notebook 中有我的目標文件和外部知識來源。請分析我的目標，再看這些內容，告訴我：哪一個洞見對我最關鍵？為什麼？給我一個具體的 5 分鐘晨間練習讓我可以立刻開始應用。`
  },
  {
    id: 28, lessons: [9],
    name: "Airtable + AI Field Agent — 自動化資料庫",
    difficulty: "Intermediate",
    timing: "Lesson 9（自動化克隆）",
    problem: "每次要產生 LinkedIn 貼文、翻譯、SEO 關鍵字都要開 ChatGPT，來回複製貼上浪費大量時間",
    situation: "想讓 AI 直接住在你的資料庫裡，自動根據每筆資料產出所需內容",
    steps: [
      "前往 airtable.com，建立免費帳號並開啟 AI 功能（需在工作區設定中啟用）",
      "建立一個 Base（例如「社群媒體貼文管理」）",
      "在表格中新增欄位，點「+」→ 選「Build a field agent」",
      "選擇回應類型（長文字、單選、圖片等）",
      "在「Custom Instructions」輸入提示詞，並用「Insert Field」插入資料庫欄位作為動態變數",
      "範例提示：「你是社群媒體行銷專家，根據以下部落格文章 {blog_post} 和目標受眾 {target_audience} 產生一篇病毒式 LinkedIn 貼文」",
      "點「Create Field」，AI 自動為每筆記錄生成內容"
    ],
    prompt: `你是社群媒體行銷專家，專門創作爆款 LinkedIn 貼文。請閱讀以下部落格文章，提取最有病毒潛力的核心觀點，撰寫一篇吸引創業者和 CEO 的 LinkedIn 貼文，包含強力開場、3 個實用重點和明確行動號召。部落格文章：{blog_post}。目標受眾：{target_audience}。`
  },
  {
    id: 29, lessons: [9, 10],
    name: "Airtable Omni AI — 快速建立內部應用程式",
    difficulty: "Intermediate",
    timing: "Lesson 9–10（自動化克隆）",
    problem: "想為公司或個人建立內部工具（CRM、活動管理、招聘追蹤），但程式開發太貴、太慢",
    situation: "需要一個客製化的資料庫應用程式，讓團隊可以共用、追蹤進度、自動觸發流程",
    steps: [
      "在 Airtable 首頁點左下角「Create」→ 選「Build an app with Omni」",
      "輸入你想建立的應用描述（例如「社群媒體內容管理，包含審批流程和發布排程」）",
      "或匯入現有 Excel/Google Sheet 讓 Omni 自動轉換",
      "Omni 會問幾個澄清問題（使用者是誰？主要工作流程是什麼？）",
      "AI 自動建立表格、欄位、介面和基本自動化",
      "點「Interface」→「Launch」查看應用程式成果，再視需要調整"
    ],
    prompt: `（建議用 PEARL 框架思考你的 App 需要哪些表格：P=人員（People）、E=事件（Events）、A=資產（Assets）、R=結果（Results）、L=日誌（Logs）。再告訴 Omni：「我需要一個 [用途] 的應用，主要使用者是 [誰]，核心工作流程包括 [列出 2–3 個流程]。」）`
  },
  {
    id: 30, lessons: [9, 10],
    name: "Airtable AI Field Agent — 圖片生成與本地化",
    difficulty: "Advanced",
    timing: "Lesson 9–10（自動化克隆）",
    problem: "行銷素材需要本地化到多語言市場，手動更改圖片文字耗費大量設計時間和成本",
    situation: "有大量廣告圖、產品圖需要翻譯成不同語言版本，希望 AI 自動完成",
    steps: [
      "在 Airtable 表格中建立「附件」欄位，上傳原始英文廣告圖",
      "新增另一個欄位 → 選「Build a field agent」→ 欄位類型選「Image」→ 選「Generate image」",
      "選擇 GPT Image 模型（目前 Airtable 支援 OpenAI 圖片模型）",
      "在指令中輸入：「編輯這張圖片 {image_field}，將圖片上的英文文字本地化成 {language} 語言，其他部分保持不變」",
      "插入「語言」欄位作為動態變數，每筆記錄對應不同語言",
      "點生成後，AI 自動產出各語言版本廣告圖並儲存回資料庫"
    ],
    prompt: `編輯輸入圖片，將圖片上的英文文字本地化成 {language} 語言。嚴格要求：僅更改文字內容，不改變圖片其他元素（背景、色彩、版面、圖示）。確保翻譯後的文字風格符合 {language} 的在地表達習慣。`
  },
  {
    id: 31, lessons: [10],
    name: "Airtable PEARL + ICE 框架 — AI 機會識別系統",
    difficulty: "Intermediate",
    timing: "Lesson 10–11（自動化克隆 + 畢業）",
    problem: "不知道從哪裡開始導入 AI，想到很多可能性但不知道優先順序，容易被 FOMO 淹沒",
    situation: "想系統性地識別、評估和排序工作或生活中最值得用 AI 提升的流程",
    steps: [
      "複製 Airtable GAIN/ICE 框架範本（由 Vykintas 提供）",
      "用 GAIN 框架識別機會：G=重複性任務、A=討厭的任務、I=耗資源的任務、N=被忽略的機會",
      "花 15 分鐘腦力激盪，把所有想法記錄到「Identify」頁面",
      "用 ICE 框架為每個機會評分：I=影響力（Impact）、C=清晰度（Clarity）、E=容易度（Ease）各 1–5 分",
      "App 自動計算總分並排序，選出最高分的機會優先執行",
      "執行完成後記錄結果，持續迭代這個識別 → 評估 → 執行循環"
    ],
    prompt: `（此工具是 Airtable 應用程式，直接在介面操作。核心原則：不要想「我要用 AI 改造整個業務」，要聚焦在 1–3 步驟的微型工作流程。ICE 分數最高的任務往往是：你每天重複做、你很討厭做、而且你大概知道如何用 AI 解決的任務。）`
  },
  {
    id: 32, lessons: [10],
    name: "Airtable Zero-shot vs Few-shot 提示技巧",
    difficulty: "Intermediate",
    timing: "Lesson 10（自動化克隆進階）",
    problem: "AI 在 Airtable 中產出的內容格式不一致，有時附上說明、有時沒有，難以自動化處理",
    situation: "想讓 AI Field Agent 的輸出格式完全可預測，方便後續自動化流程使用",
    steps: [
      "在 Airtable AI Field Agent 的「Custom Instructions」中，除了指令外，加入「Response Example」區塊",
      "零樣本（Zero-shot）：只給指令，不提供範例 → 結果格式不穩定",
      "少樣本（Few-shot）：在指令後加入具體輸出範例，例如：「回應範例：Flowwise, YouTube API, Perplexity API, Make（用逗號分隔，不加說明）」",
      "核心原則：Show，不要 Tell。展示你想要的輸出格式，AI 會模仿",
      "測試兩種方式的差異，觀察一致性提升",
      "套用到所有需要固定格式的 Field Agent（標籤提取、分類、評分等）"
    ],
    prompt: `（Few-shot 提示範例結構）
任務：[你的指令]
回應格式：只回傳結果，不加任何說明或前言。
回應範例：[你想要的理想輸出格式]
現在根據以下內容執行：{field_reference}`
  },
  {
    id: 33, lessons: [11],
    name: "AI 克隆整合系統 — 完整工作流程設計",
    difficulty: "Advanced",
    timing: "Lesson 11（畢業展示）",
    problem: "學了很多 AI 工具，但各自獨立使用，沒有形成一個能持續運作、自我強化的系統",
    situation: "想把通訊克隆、學習克隆、自動化克隆整合成一個完整的個人 AI 作業系統",
    steps: [
      "清點你已建立的克隆：通訊分身（Claude/ChatGPT Project）、會議智慧（Granola）、影像克隆（HeyGen）、學習克隆（Notebook LM）、自動化克隆（Airtable）",
      "用 GAIN 框架識別目前工作流中最耗時的環節",
      "設計「資料流」：哪個工具的輸出是另一個工具的輸入？（例如：Granola 會議逐字稿 → Claude Project 分析 → Airtable 追蹤行動項目）",
      "建立一個「AI 系統中控台」Airtable，追蹤各克隆的狀態和成效",
      "每週審查：哪個克隆帶來了最多價值？哪個需要更新知識文件？",
      "持續用 ICE 框架識別下一個值得建立的克隆"
    ],
    prompt: `我想設計一個完整的個人 AI 工作系統。我目前有以下工具：[列出已建立的克隆]。我的主要工作是 [描述你的工作]。最耗時的三件事是 [列出]。請幫我設計一個這些工具之間的資料流程圖，並指出最關鍵的整合點，讓這個系統能夠自我強化。`
  },
  {
    id: 34, lessons: [12],
    name: "Jai AI — 智慧信箱管理系統",
    difficulty: "Intermediate",
    timing: "Lesson 12（Email 自動化克隆）",
    problem: "每天被大量郵件淹沒，花大量時間分類、回覆、追蹤，重要郵件常被埋沒或忘記跟進",
    situation: "想讓 AI 幫你自動標記、分類郵件，並根據你的知識庫自動草擬回覆",
    steps: [
      "前往 jai.ai，建立帳號並連接 Gmail 或 Outlook",
      "設定智慧標籤（Smart Labels）：Action（需行動）、Read（需閱讀）、Store（存檔備查）、Noise（雜訊忽略）",
      "在每個標籤的「Description」中用自然語言描述何時套用（Few-shot：提供具體郵件範例）",
      "設定「Waiting」工作流：每次你發出需對方回應的郵件，自動加上等待標籤並預設追蹤提醒",
      "連接你的工具整合：Google Drive、Airtable、Notion、Slack 等，讓 AI 能取用上下文自動草稿",
      "建立「銷售詢問」工作流：當郵件符合條件時，AI 自動到 Google Drive 讀取定價文件，草擬含正確數字的回覆"
    ],
    prompt: `（Jai AI 的 Workflow 設定邏輯：「當郵件符合 [條件] 時，使用 [工具] 取得相關資訊，然後 [執行動作]」。重要原則：不要讓 AI 自動發送郵件，永遠保留人工審核這一步驟。）`
  },
  {
    id: 35, lessons: [12],
    name: "PAIR 框架 — Email 系統化管理方法",
    difficulty: "Beginner",
    timing: "Lesson 12（Email 自動化克隆）",
    problem: "信箱雜亂無章，重要郵件和垃圾混在一起，每天處理郵件的心理負擔極重",
    situation: "想在導入 AI 工具之前，先建立一套讓收件匣保持整潔的系統性原則",
    steps: [
      "P（Protect 保護）：在 Gmail 取消所有不必要的訂閱（Settings → Manage Subscriptions），建立篩選器讓會議通知、系統郵件直接歸檔不進收件匣",
      "A（Assess 評估）：對每封新郵件問三個問題：有具體行動嗎？消失了會有損失嗎？需要閱讀還是只要存檔？分別標記 Action / Store / Read / Noise",
      "I（Integrate 整合）：連接 Jai AI 或 Gmail 的 AI 功能，讓 AI 根據你設計的標準自動標記",
      "R（Review 審查）：每週固定時間審查標籤系統是否失效，哪些郵件被錯誤分類，更新 AI 的指令",
      "額外技巧：建立「AI 科技」標籤，讓所有電子報自動歸類，只在每週固定的「AI 更新日」統一閱讀",
      "寄出需跟進的郵件後，立刻設定「稍後提醒」（Snooze）作為追蹤備援機制"
    ],
    prompt: `（這是一個操作框架，不需要 AI 提示詞。核心信念：電子郵件是溝通介面，不是資料庫。所有需要儲存的資訊應推送到 Airtable、Notion 或 Google Drive，而不是留在信箱裡。）`
  },
  {
    id: 36, lessons: [12],
    name: "Gmail 整合 AI — 自動提取與推送資料",
    difficulty: "Advanced",
    timing: "Lesson 12（Email 自動化克隆）",
    problem: "收到的發票、合約、待辦事項全部散落在信箱裡，每次要找都要翻找，會計和法律文件管理混亂",
    situation: "想讓 AI 自動從郵件中提取重要資料，推送到正確的系統（雲端硬碟、資料庫、行事曆）",
    steps: [
      "在 Jai AI 的「Workflows」建立「Invoice Handler」工作流",
      "條件設定：「郵件包含發票附件」",
      "選取工具：Google Drive（連接對應資料夾）",
      "行動指令：「將所有發票附件儲存到 Google Drive 的『Invoices/[年份]』資料夾」",
      "類似地，建立「To-Do Extractor」工作流：當郵件包含需要你行動的待辦事項時，自動在 Airtable 或 Asana 新增任務，並附上原始郵件連結",
      "建立「Meeting Request Handler」工作流：當有人提議會面時，AI 查看你的行事曆並草擬包含可用時間的回覆"
    ],
    prompt: `（Jai AI Workflow 行動指令範例）
儲存發票：「Save all invoice attachments to Google Drive folder: Finance/Invoices/2025. Return a confirmation with the file name saved.」
建立待辦：「Extract any action items assigned to me from this email. Create a task in Airtable [base name] with: task name, due date if mentioned, and a link back to this email thread.」`
  },
  {
    id: 37, lessons: [7, 8, 9, 10, 11, 12],
    name: "AI 加速器核心原則 — 選擇基石工具，避免 FOMO",
    difficulty: "Beginner",
    timing: "Lesson 7–12（整體心法）",
    problem: "AI 工具層出不窮，每天都有新的「革命性」工具，不知道該學哪個，反而什麼都沒學好",
    situation: "想建立一套穩定的 AI 工具體系，讓自己持續進步，而不是不斷追逐新工具",
    steps: [
      "選定「基石工具」：AI 對話（ChatGPT 或 Claude 選一個深度使用）、知識管理（Airtable 或 Notion）、視覺內容（HeyGen 或 Kling）、學習（Notebook LM）、Email（Jai AI）",
      "每個類別只用一個工具，不要同時學競品，先把一個用到精通",
      "新工具出現時，用 ICE 框架評估：對我的工作影響力多大？我清楚如何使用嗎？多容易上手？",
      "建立「工具評估暫存區」Airtable，把看到的新工具先存進去，等有具體需求再研究",
      "核心原則：95% 的 AI 能力已足夠大多數任務，剩下的 5% 才是你需要花時間掌握的真正差異化能力",
      "每個月花一天做「AI 系統審查」：哪個工具帶來最多價值？哪個可以停止使用？有什麼新的整合機會？"
    ],
    prompt: `我想系統化管理我的 AI 工具使用。請幫我：1）根據我的工作 [描述工作] 推薦最精簡的工具清單（每個類別最多一個）；2）為每個類別列出我應該掌握的 3 個核心功能；3）建議一個每週 AI 使用習慣養成計畫。目標：不是學最多工具，而是讓 AI 真正嵌入每日工作流。`
  }
];

// ── RENDER ──
const grid = document.getElementById('grid');
const searchInput = document.getElementById('search');
const countBar = document.getElementById('count-bar');
const emptyState = document.getElementById('empty');
let activeFilter = 'all';
let openId = null;

function diffClass(d) {
  if (d === 'Beginner') return 'beginner';
  if (d === 'Intermediate') return 'intermediate';
  return 'advanced';
}

function buildCard(tool) {
  const dc = diffClass(tool.difficulty);
  const isDone = doneIds.has(tool.id);
  const doneClass = isDone ? ' done' : '';

  const stepsHtml = tool.steps.map((s, i) =>
    `<li><span class="step-num">${String(i + 1).padStart(2,'0')}</span>${s}</li>`
  ).join('');

  const tagsHtml = (tool.lessons || []).map(l => {
    const m = lessonMeta[l];
    return m ? `<span class="course-tag ${m.cls}">${m.label}</span>` : '';
  }).join('');

  return `
  <div class="card${doneClass}" id="card-${tool.id}" data-id="${tool.id}" data-difficulty="${tool.difficulty}">
    <div class="card-head" onclick="toggleCard(${tool.id})">
      <span class="card-num">#${String(tool.id).padStart(2,'0')}</span>
      <div class="card-title-wrap">
        <div class="card-title">${tool.name}</div>
        <div class="card-timing">${tool.timing}</div>
      </div>
      <div class="done-check"><svg viewBox="0 0 10 8" fill="none" stroke="white" stroke-width="1.8"><polyline points="1,4 3.8,7 9,1"/></svg></div>
      <span class="badge badge-${dc}">${tool.difficulty}</span>
    </div>
    <div class="card-preview" onclick="toggleCard(${tool.id})">${tool.problem}</div>
    ${tagsHtml ? `<div class="course-tags">${tagsHtml}</div>` : ''}
    <div class="card-footer" onclick="toggleCard(${tool.id})">
      <div class="expand-hint">
        <span>展開詳細內容</span>
        <span class="chevron">▾</span>
      </div>
      <button class="done-btn" onclick="event.stopPropagation(); toggleDone(${tool.id})">${isDone ? '✓ 已完成' : '標記完成'}</button>
    </div>
    <div class="card-detail">
      <div class="detail-grid">
        <div class="detail-section">
          <div class="detail-label">解決問題</div>
          <div class="detail-text">${tool.problem}</div>
        </div>
        <div class="detail-section">
          <div class="detail-label">使用情境</div>
          <div class="detail-text">${tool.situation}</div>
        </div>
        <div class="detail-section full">
          <div class="detail-label">操作步驟</div>
          <ul class="steps-list">${stepsHtml}</ul>
        </div>
        <div class="detail-section full">
          <div class="detail-label">代表 Prompt</div>
          <div class="prompt-box">${tool.prompt}</div>
        </div>
      </div>
      <div class="detail-close">
        <button class="close-btn" onclick="closeCard(${tool.id})">收合 ↑</button>
      </div>
    </div>
  </div>`;
}

function toggleDone(id) {
  if (doneIds.has(id)) {
    doneIds.delete(id);
    showToast('已取消完成標記');
  } else {
    doneIds.add(id);
    showToast('✓ 已標記為完成！');
  }
  saveDone(doneIds);
  render();
}

function render() {
  const q = searchInput.value.trim().toLowerCase();
  const filtered = tools.filter(t => {
    const matchFilter = activeFilter === 'all' || t.difficulty === activeFilter;
    const matchSearch = !q ||
      t.name.toLowerCase().includes(q) ||
      t.problem.toLowerCase().includes(q) ||
      t.situation.toLowerCase().includes(q) ||
      t.steps.some(s => s.toLowerCase().includes(q));
    return matchFilter && matchSearch;
  });

  if (openId && !filtered.find(t => t.id === openId)) openId = null;

  grid.innerHTML = filtered.map(buildCard).join('');

  if (openId) {
    const el = document.getElementById(`card-${openId}`);
    if (el) el.classList.add('open');
  }

  grid.querySelectorAll('.card').forEach((el, i) => {
    el.style.animationDelay = `${i * 30}ms`;
  });

  const doneCount = filtered.filter(t => doneIds.has(t.id)).length;
  countBar.textContent = `顯示 ${filtered.length} / ${tools.length} 個工具${doneCount > 0 ? `　·　已完成 ${doneCount} 個` : ''}`;
  emptyState.style.display = filtered.length === 0 ? 'block' : 'none';
  grid.style.display = filtered.length === 0 ? 'none' : 'grid';
}

function toggleCard(id) {
  if (openId === id) {
    closeCard(id);
  } else {
    if (openId) {
      const prev = document.getElementById(`card-${openId}`);
      if (prev) prev.classList.remove('open');
    }
    openId = id;
    const el = document.getElementById(`card-${id}`);
    if (el) {
      el.classList.add('open');
      setTimeout(() => el.scrollIntoView({ behavior: 'smooth', block: 'nearest' }), 50);
    }
  }
}

function closeCard(id) {
  const el = document.getElementById(`card-${id}`);
  if (el) el.classList.remove('open');
  openId = null;
}

document.querySelectorAll('.pill').forEach(btn => {
  btn.addEventListener('click', () => {
    document.querySelectorAll('.pill').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    activeFilter = btn.dataset.filter;
    openId = null;
    render();
  });
});

let debounce;
searchInput.addEventListener('input', () => {
  clearTimeout(debounce);
  debounce = setTimeout(render, 150);
});

render();
</script>
</body>
</html>
