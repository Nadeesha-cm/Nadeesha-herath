<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Reload Management</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@400;500;600;700;800&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
<script>
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          ink: { 950: '#0B1015', 900: '#121922', 800: '#1A222C', 700: '#212B36', 600: '#2A343F' },
          line: '#2A343E',
          paper: '#ECEFF3',
          muted: '#8B97A4',
          gold: { DEFAULT: '#E3AE4D', dim: '#3C3120', soft: '#F0C877' },
          good: '#4FAE7C',
          bad: '#E1636B',
          amberc: '#E3934D',
          bluec: '#5B8DEF',
          tealc: '#3FB8C9'
        },
        fontFamily: {
          display: ['Sora', 'sans-serif'],
          sans: ['Inter', 'sans-serif']
        }
      }
    }
  }
</script>
<style>
  html, body { background: #0B1015; }
  body { font-family: 'Inter', sans-serif; color: #ECEFF3; }
  h1, h2, h3, .font-display { font-family: 'Sora', sans-serif; }
  .tnum { font-variant-numeric: tabular-nums; font-feature-settings: "tnum" 1; }

  ::-webkit-scrollbar { width: 8px; height: 8px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: #2A343E; border-radius: 4px; }

  .ledger-bg {
    background-image: repeating-linear-gradient(
      to bottom,
      transparent 0px,
      transparent 27px,
      rgba(255,255,255,0.028) 28px
    );
  }

  .receipt-edge { position: relative; }
  .receipt-edge::before {
    content: "";
    position: absolute;
    top: -1px; left: 0; right: 0; height: 8px;
    background-image: radial-gradient(circle at 8px 0px, transparent 4px, #121922 4.5px);
    background-size: 16px 8px;
    background-repeat: repeat-x;
  }

  input:focus-visible, button:focus-visible, select:focus-visible {
    outline: 2px solid #E3AE4D;
    outline-offset: 2px;
  }

  @media (prefers-reduced-motion: no-preference) {
    .reveal { animation: reveal .5s ease both; }
    @keyframes reveal { from { opacity: 0; transform: translateY(6px); } to { opacity: 1; transform: translateY(0); } }
    .unlock-anim { animation: unlock .55s cubic-bezier(.2,.8,.2,1) both; }
    @keyframes unlock { 0% { opacity: 0; transform: scale(.97); } 100% { opacity: 1; transform: scale(1); } }
  }
  @media (prefers-reduced-motion: reduce) {
    .reveal, .unlock-anim { animation: none !important; }
  }

  .nav-btn { transition: background-color .15s ease, color .15s ease; }
  .nav-btn.active { background: #1A222C; color: #ECEFF3; }
  .nav-btn.active .nav-bar { opacity: 1; }
  .nav-bar { opacity: 0; transition: opacity .15s ease; }

  .toast { animation: toastin .25s ease both; }
  @keyframes toastin { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }
</style>
</head>
<body class="bg-ink-950 text-paper min-h-screen">

<!-- ============ LOGIN SCREEN ============ -->
<div id="login-screen" class="min-h-screen w-full flex items-center justify-center relative overflow-hidden ledger-bg">
  <div class="absolute inset-0 pointer-events-none" style="background: radial-gradient(700px 400px at 50% 15%, rgba(227,174,77,0.07), transparent 70%);"></div>

  <div class="relative w-full max-w-sm mx-4">
    <div class="text-center mb-7">
      <div class="inline-flex items-center gap-2 mb-3">
        <svg width="30" height="30" viewBox="0 0 24 24" fill="none"><rect x="2" y="5" width="20" height="14" rx="2" stroke="#E3AE4D" stroke-width="1.6"/><path d="M2 9H22" stroke="#E3AE4D" stroke-width="1.6"/><circle cx="6" cy="14.5" r="1.3" fill="#E3AE4D"/></svg>
        <h1 class="font-display font-bold text-2xl text-paper tracking-tight">Reload Management</h1>
      </div>
      <p class="text-muted text-sm">Cash drawer &amp; airtime ledger for your shop counter</p>
    </div>

    <form id="login-form" class="bg-ink-900 border border-line rounded-lg p-6 unlock-anim">
      <div class="h-1 w-10 bg-gold rounded-full mb-5"></div>
      <label class="block mb-4">
        <span class="text-xs text-muted mb-1.5 block">Username</span>
        <input id="login-username" type="text" autocomplete="username" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm text-paper placeholder-muted/60" placeholder="Owner" />
      </label>
      <label class="block mb-5">
        <span class="text-xs text-muted mb-1.5 block">Password</span>
        <input id="login-password" type="password" autocomplete="current-password" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm text-paper placeholder-muted/60" placeholder="••••••••" />
      </label>
      <div id="login-error" class="text-bad text-xs mb-4 hidden"></div>
      <button type="submit" class="w-full bg-gold hover:bg-gold-soft text-ink-950 font-display font-semibold text-sm rounded-md py-2.5 transition-colors">Log in</button>
    </form>
    <p class="text-center text-muted text-xs mt-4">Data stays on this device only.</p>
  </div>
</div>

<!-- ============ MAIN APP ============ -->
<div id="app" class="hidden min-h-screen md:flex">

  <!-- Sidebar (desktop) -->
  <aside class="hidden md:flex md:flex-col w-56 shrink-0 bg-ink-900 border-r border-line">
    <div class="px-5 py-5 flex items-center gap-2 border-b border-line">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none"><rect x="2" y="5" width="20" height="14" rx="2" stroke="#E3AE4D" stroke-width="1.6"/><path d="M2 9H22" stroke="#E3AE4D" stroke-width="1.6"/><circle cx="6" cy="14.5" r="1.3" fill="#E3AE4D"/></svg>
      <span class="font-display font-semibold text-sm">Reload Management</span>
    </div>
    <nav class="flex-1 py-4 px-2 space-y-1" id="sidebar-nav">
      <button data-page="dashboard" class="nav-btn w-full flex items-center gap-3 px-3 py-2.5 rounded-md text-sm text-muted relative">
        <span class="nav-bar absolute left-0 top-1.5 bottom-1.5 w-0.5 bg-gold rounded-full"></span>
        <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><rect x="3" y="3" width="8" height="8" rx="1.5"/><rect x="13" y="3" width="8" height="5" rx="1.5"/><rect x="13" y="11" width="8" height="10" rx="1.5"/><rect x="3" y="14" width="8" height="7" rx="1.5"/></svg>
        Dashboard
      </button>
      <button data-page="transaction" class="nav-btn w-full flex items-center gap-3 px-3 py-2.5 rounded-md text-sm text-muted relative">
        <span class="nav-bar absolute left-0 top-1.5 bottom-1.5 w-0.5 bg-gold rounded-full"></span>
        <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><path d="M4 8h13M13 4l4 4-4 4"/><path d="M20 16H7M11 12l-4 4 4 4"/></svg>
        New transaction
      </button>
      <button data-page="companies" class="nav-btn w-full flex items-center gap-3 px-3 py-2.5 rounded-md text-sm text-muted relative">
        <span class="nav-bar absolute left-0 top-1.5 bottom-1.5 w-0.5 bg-gold rounded-full"></span>
        <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><path d="M7 3h8l4 4v13a1 1 0 0 1-1 1H7a1 1 0 0 1-1-1V4a1 1 0 0 1 1-1Z"/><path d="M10 9h4M10 13h4M10 17h2"/></svg>
        Companies
      </button>
      <button data-page="reports" class="nav-btn w-full flex items-center gap-3 px-3 py-2.5 rounded-md text-sm text-muted relative">
        <span class="nav-bar absolute left-0 top-1.5 bottom-1.5 w-0.5 bg-gold rounded-full"></span>
        <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><path d="M4 20V10M11 20V4M18 20v-7"/><path d="M2 20h20"/></svg>
        Reports
      </button>
      <button data-page="credits" class="nav-btn w-full flex items-center gap-3 px-3 py-2.5 rounded-md text-sm text-muted relative">
        <span class="nav-bar absolute left-0 top-1.5 bottom-1.5 w-0.5 bg-gold rounded-full"></span>
        <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><path d="M4 4.5h13a2 2 0 0 1 2 2V19a1 1 0 0 1-1 1H6.5A2.5 2.5 0 0 1 4 17.5v-13Z"/><path d="M8 9h8M8 13h5"/></svg>
        Credit book
      </button>
    </nav>
    <div class="px-2 pb-4 space-y-1">
      <button id="settings-btn" class="w-full flex items-center gap-3 px-3 py-2.5 rounded-md text-sm text-muted hover:text-paper">
        <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.7 1.7 0 0 0 .34 1.87l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06a1.7 1.7 0 0 0-1.87-.34 1.7 1.7 0 0 0-1 1.55V21a2 2 0 1 1-4 0v-.09a1.7 1.7 0 0 0-1-1.55 1.7 1.7 0 0 0-1.87.34l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06A1.7 1.7 0 0 0 4.6 15a1.7 1.7 0 0 0-1.55-1H3a2 2 0 1 1 0-4h.09A1.7 1.7 0 0 0 4.6 9a1.7 1.7 0 0 0-.34-1.87l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06a1.7 1.7 0 0 0 1.87.34H9A1.7 1.7 0 0 0 10 3.09V3a2 2 0 1 1 4 0v.09a1.7 1.7 0 0 0 1 1.55 1.7 1.7 0 0 0 1.87-.34l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06A1.7 1.7 0 0 0 19.4 9a1.7 1.7 0 0 0 1.55 1H21a2 2 0 1 1 0 4h-.09a1.7 1.7 0 0 0-1.55 1Z"/></svg>
        Settings
      </button>
      <button id="logout-btn" class="w-full flex items-center gap-3 px-3 py-2.5 rounded-md text-sm text-muted hover:text-bad">
        <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><path d="M9 21H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h4"/><path d="M16 17l5-5-5-5M21 12H9"/></svg>
        Log out
      </button>
    </div>
  </aside>

  <div class="flex-1 min-w-0 flex flex-col pb-16 md:pb-0">
    <!-- Header -->
    <header class="sticky top-0 z-20 bg-ink-950/90 backdrop-blur border-b border-line px-4 md:px-7 py-3 flex items-center justify-between gap-3">
      <div>
        <p class="text-xs text-muted" id="header-date"></p>
        <p class="text-sm font-medium" id="header-clock"></p>
      </div>
      <div class="text-right">
        <p class="text-[11px] text-muted uppercase tracking-wide">Cash in hand</p>
        <p class="font-display font-bold text-lg text-gold tnum" id="header-cash">Rs 0</p>
      </div>
    </header>

    <main class="flex-1 min-w-0 p-4 md:p-7 space-y-6">
      <section id="page-dashboard" class="page space-y-6"></section>
      <section id="page-transaction" class="page hidden space-y-6"></section>
      <section id="page-companies" class="page hidden space-y-6"></section>
      <section id="page-reports" class="page hidden space-y-6"></section>
      <section id="page-credits" class="page hidden space-y-6"></section>
    </main>
  </div>

  <!-- Mobile bottom nav -->
  <nav class="md:hidden fixed bottom-0 inset-x-0 z-30 bg-ink-900 border-t border-line flex items-stretch h-16">
    <button data-page="dashboard" class="mnav-btn flex-1 flex flex-col items-center justify-center gap-0.5 text-muted text-[10px]">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><rect x="3" y="3" width="8" height="8" rx="1.5"/><rect x="13" y="3" width="8" height="5" rx="1.5"/><rect x="13" y="11" width="8" height="10" rx="1.5"/><rect x="3" y="14" width="8" height="7" rx="1.5"/></svg>
      Home
    </button>
    <button data-page="transaction" class="mnav-btn flex-1 flex flex-col items-center justify-center gap-0.5 text-muted text-[10px]">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><path d="M4 8h13M13 4l4 4-4 4"/><path d="M20 16H7M11 12l-4 4 4 4"/></svg>
      Sale
    </button>
    <button data-page="companies" class="mnav-btn flex-1 flex flex-col items-center justify-center gap-0.5 text-muted text-[10px]">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><path d="M7 3h8l4 4v13a1 1 0 0 1-1 1H7a1 1 0 0 1-1-1V4a1 1 0 0 1 1-1Z"/><path d="M10 9h4M10 13h4M10 17h2"/></svg>
      Networks
    </button>
    <button data-page="reports" class="mnav-btn flex-1 flex flex-col items-center justify-center gap-0.5 text-muted text-[10px]">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><path d="M4 20V10M11 20V4M18 20v-7"/><path d="M2 20h20"/></svg>
      Reports
    </button>
    <button data-page="credits" class="mnav-btn flex-1 flex flex-col items-center justify-center gap-0.5 text-muted text-[10px]">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><path d="M4 4.5h13a2 2 0 0 1 2 2V19a1 1 0 0 1-1 1H6.5A2.5 2.5 0 0 1 4 17.5v-13Z"/><path d="M8 9h8M8 13h5"/></svg>
      Credit
    </button>
  </nav>
</div>

<!-- Settings modal -->
<div id="settings-modal" class="hidden fixed inset-0 z-40 items-center justify-center bg-black/60 p-4">
  <div class="bg-ink-900 border border-line rounded-lg max-w-sm w-full p-6">
    <h3 class="font-display font-semibold text-base mb-1">Settings</h3>
    <p class="text-xs text-muted mb-5">Backups are saved as a single JSON file you keep yourself.</p>
    <div class="space-y-2.5">
      <button id="export-btn" class="w-full text-left px-3 py-2.5 rounded-md bg-ink-800 border border-line text-sm hover:border-gold/50">Export backup (.json)</button>
      <label class="block w-full text-left px-3 py-2.5 rounded-md bg-ink-800 border border-line text-sm hover:border-gold/50 cursor-pointer">
        Import backup (.json)
        <input id="import-input" type="file" accept="application/json" class="hidden" />
      </label>
      <button id="reset-btn" class="w-full text-left px-3 py-2.5 rounded-md bg-ink-800 border border-bad/40 text-sm text-bad hover:bg-bad/10">Reset all data</button>
    </div>
    <button id="settings-close" class="mt-5 w-full text-center px-3 py-2.5 rounded-md text-sm text-muted hover:text-paper">Close</button>
  </div>
</div>

<!-- Setup modal -->
<div id="setup-modal" class="hidden fixed inset-0 z-40 items-center justify-center bg-black/60 p-4">
  <div class="bg-ink-900 border border-line rounded-lg max-w-md w-full p-6 max-h-[90vh] overflow-y-auto">
    <h3 class="font-display font-semibold text-base mb-1">Set up your register</h3>
    <p class="text-xs text-muted mb-5">Enter what's in the drawer and each company's balance right now. You can adjust any of this later too.</p>
    <form id="setup-form" class="space-y-4">
      <label class="block">
        <span class="text-xs text-muted mb-1.5 block">Cash in the drawer (Rs)</span>
        <input id="setup-cash" type="number" min="0" step="0.01" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm tnum" />
      </label>
      <div id="setup-companies" class="grid grid-cols-2 gap-3"></div>
      <button type="submit" class="w-full bg-gold hover:bg-gold-soft text-ink-950 font-display font-semibold text-sm rounded-md py-2.5">Save and start</button>
    </form>
  </div>
</div>

<!-- Reconcile modal -->
<div id="reconcile-modal" class="hidden fixed inset-0 z-40 items-center justify-center bg-black/60 p-4">
  <div class="bg-ink-900 border border-line rounded-lg max-w-sm w-full p-6">
    <h3 class="font-display font-semibold text-base mb-1">Count the drawer</h3>
    <p id="reconcile-current" class="text-sm text-muted mb-4"></p>
    <form id="reconcile-form" class="space-y-4">
      <label class="block">
        <span class="text-xs text-muted mb-1.5 block">Cash actually counted (Rs)</span>
        <input id="reconcile-amount" type="number" step="0.01" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm tnum" />
      </label>
      <label class="block">
        <span class="text-xs text-muted mb-1.5 block">Note (optional)</span>
        <input id="reconcile-note" type="text" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm" placeholder="Why the difference, if any" />
      </label>
      <div class="flex gap-2">
        <button type="button" id="reconcile-cancel" class="flex-1 text-sm text-muted rounded-md py-2.5 border border-line">Cancel</button>
        <button type="submit" class="flex-1 bg-gold text-ink-950 font-display font-semibold text-sm rounded-md py-2.5">Save</button>
      </div>
    </form>
  </div>
</div>

<!-- Edit / delete transaction modal (password protected) -->
<div id="txn-action-modal" class="hidden fixed inset-0 z-40 items-center justify-center bg-black/60 p-4">
  <div class="bg-ink-900 border border-line rounded-lg max-w-sm w-full p-6">
    <h3 id="txn-action-title" class="font-display font-semibold text-base mb-1">Edit transaction</h3>
    <p id="txn-action-sub" class="text-xs text-muted mb-4"></p>
    <form id="txn-action-form" class="space-y-4">
      <div id="txn-action-fields" class="space-y-4"></div>
      <label class="block">
        <span class="text-xs text-muted mb-1.5 block">Owner password</span>
        <input id="txn-action-password" type="password" autocomplete="current-password" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm" placeholder="••••••••" />
      </label>
      <div id="txn-action-error" class="text-bad text-xs hidden"></div>
      <div class="flex gap-2">
        <button type="button" id="txn-action-cancel" class="flex-1 text-sm text-muted rounded-md py-2.5 border border-line">Cancel</button>
        <button type="submit" id="txn-action-confirm" class="flex-1 font-display font-semibold text-sm rounded-md py-2.5 bg-gold text-ink-950">Save</button>
      </div>
    </form>
  </div>
</div>

<div id="toast-root" class="fixed bottom-20 md:bottom-6 right-4 z-50 space-y-2"></div>

<script>
/* ============================================================
   STATE
============================================================ */
const STORAGE_KEY = 'reload_register_state_v1';
const AUTH_KEY = 'reload_register_auth';
const CREDENTIALS = { username: 'Owner', password: 'Owner123' };

const DEFAULT_COMPANIES = [
  { id: 'hutch',   name: 'Hutch',   color: '#F58220' },
  { id: 'mobitel', name: 'Mobitel', color: '#00A651' },
  { id: 'dialog',  name: 'Dialog',  color: '#00AEEF' },
  { id: 'airtel',  name: 'Airtel',  color: '#ED1C24' },
];

const TYPE_META = {
  sale:      { label: 'Reload sale',       color: '#4FAE7C' },
  credit:    { label: 'Reload on credit',  color: '#E3934D' },
  dealer:    { label: 'Dealer top-up',     color: '#5B8DEF' },
  settle:    { label: 'Credit collected',  color: '#3FB8C9' },
  adjust:    { label: 'Balance adjustment', color: '#8B97A4' },
  reconcile: { label: 'Cash count adjustment', color: '#8B97A4' },
};

function uid() { return Date.now().toString(36) + Math.random().toString(36).slice(2, 8); }

function dateKey(d = new Date()) {
  const y = d.getFullYear(), m = String(d.getMonth() + 1).padStart(2, '0'), day = String(d.getDate()).padStart(2, '0');
  return `${y}-${m}-${day}`;
}
function prettyDate(key) {
  if (!key) return '';
  const [y, m, d] = key.split('-').map(Number);
  return new Date(y, m - 1, d).toLocaleDateString('en-GB', { day: 'numeric', month: 'short', year: 'numeric' });
}
function formatCurrency(n) {
  n = Number(n) || 0;
  const isWhole = Math.abs(n - Math.round(n)) < 0.001;
  return 'Rs ' + n.toLocaleString('en-LK', { minimumFractionDigits: isWhole ? 0 : 2, maximumFractionDigits: 2 });
}
function slugify(name) {
  return (name || '').toLowerCase().trim().replace(/[^a-z0-9]+/g, '-').replace(/(^-|-$)/g, '') || 'company';
}

function defaultState() {
  return {
    companies: DEFAULT_COMPANIES.map(c => ({ ...c, balance: 0, archived: false })),
    cash: 0,
    setupDone: false,
    setupDate: null,
    transactions: [],
    credits: [],
  };
}

function loadState() {
  try {
    const raw = localStorage.getItem(STORAGE_KEY);
    if (!raw) return defaultState();
    const parsed = JSON.parse(raw);
    if (!parsed.companies || !Array.isArray(parsed.companies)) return defaultState();
    parsed.companies.forEach(c => { if (c.archived === undefined) c.archived = false; });
    if (!parsed.transactions) parsed.transactions = [];
    if (!parsed.credits) parsed.credits = [];
    if (parsed.setupDone === undefined) {
      const hadActivity = parsed.transactions.length > 0 || (parsed.days && parsed.days.length > 0) || Number(parsed.cash) > 0;
      parsed.setupDone = !!hadActivity;
      if (!parsed.setupDate) parsed.setupDate = dateKey();
    }
    delete parsed.days;
    return parsed;
  } catch (e) { return defaultState(); }
}
function saveState() { localStorage.setItem(STORAGE_KEY, JSON.stringify(state)); }
function getCompany(id) { return state.companies.find(c => c.id === id); }

let state = loadState();

/* ============================================================
   CORE LEDGER OPERATIONS (continuous double-entry — no daily gate)
============================================================ */
function completeSetup(cash, balances) {
  state.cash = Number(cash) || 0;
  state.companies.forEach(c => { if (balances[c.id] !== undefined) c.balance = Number(balances[c.id]) || 0; });
  state.setupDone = true;
  state.setupDate = dateKey();
  saveState();
}

function addTransaction({ type, companyId, companyAmount, amount, customer, note }) {
  if (!state.setupDone) return { ok: false, msg: 'Set up your starting cash and balances first.' };
  const company = getCompany(companyId);
  let creditId = null;
  let cAmt, amt;

  if (type === 'sale' || type === 'credit') {
    cAmt = Number(companyAmount);
    amt = Number(amount);
    if (!company) return { ok: false, msg: 'Choose a reload company.' };
    if (!cAmt || cAmt <= 0) return { ok: false, msg: 'Enter the reload value to deduct from the company balance.' };
    if (!amt || amt <= 0) return { ok: false, msg: type === 'sale' ? 'Enter the amount to collect from the customer.' : 'Enter the amount the customer will owe.' };
    if (cAmt > company.balance + 0.001) return { ok: false, msg: `${company.name} only has ${formatCurrency(company.balance)} left. Top up from the dealer first.` };
    company.balance -= cAmt;
    if (type === 'sale') {
      state.cash += amt;
    } else {
      if (!customer || !customer.trim()) return { ok: false, msg: "Enter the customer's name for a credit sale." };
      creditId = uid();
      state.credits.push({ id: creditId, customer: customer.trim(), companyId, amount: amt, dateKey: dateKey(), remaining: amt, status: 'open' });
    }
  } else if (type === 'dealer') {
    amt = Number(amount);
    cAmt = amt;
    if (!company) return { ok: false, msg: 'Choose a reload company.' };
    if (!amt || amt <= 0) return { ok: false, msg: 'Enter an amount greater than zero.' };
    if (amt > state.cash + 0.001) return { ok: false, msg: `Cash in hand is only ${formatCurrency(state.cash)}.` };
    state.cash -= amt;
    company.balance += cAmt;
  } else {
    return { ok: false, msg: 'Unknown transaction type.' };
  }

  state.transactions.push({
    id: uid(), ts: Date.now(), dateKey: dateKey(), type, companyId: companyId || null,
    amount: amt, companyAmount: cAmt, customer: customer ? customer.trim() : '', note: note ? note.trim() : '', creditId,
  });
  saveState();
  return { ok: true };
}

function settleCredit(creditId, payAmount) {
  if (!state.setupDone) return { ok: false, msg: 'Set up your starting cash and balances first.' };
  const credit = state.credits.find(c => c.id === creditId);
  if (!credit) return { ok: false, msg: 'Credit record not found.' };
  payAmount = Number(payAmount);
  if (!payAmount || payAmount <= 0) return { ok: false, msg: 'Enter a payment amount greater than zero.' };
  const amt = Math.min(payAmount, credit.remaining);
  credit.remaining = Math.round((credit.remaining - amt) * 100) / 100;
  if (credit.remaining <= 0.009) { credit.remaining = 0; credit.status = 'paid'; }
  state.cash += amt;
  state.transactions.push({
    id: uid(), ts: Date.now(), dateKey: dateKey(), type: 'settle', companyId: credit.companyId,
    amount: amt, customer: credit.customer, note: 'Credit settlement', creditId: credit.id,
  });
  saveState();
  return { ok: true, amt };
}

/* ============================================================
   EDIT / DELETE TRANSACTIONS (password-protected)
============================================================ */
function findCreditForTxn(t) { return t.creditId ? state.credits.find(c => c.id === t.creditId) : null; }
function companySide(t) { return t.companyAmount != null ? t.companyAmount : t.amount; }

function reverseAndUnlink(t) {
  const company = t.companyId ? getCompany(t.companyId) : null;
  if (t.type === 'sale') {
    state.cash -= t.amount;
    if (company) company.balance += companySide(t);
  } else if (t.type === 'credit') {
    const credit = findCreditForTxn(t);
    if (credit && Math.abs(credit.remaining - credit.amount) > 0.009) {
      return { ok: false, msg: 'This credit already has a payment collected against it — settle it fully first.' };
    }
    if (company) company.balance += companySide(t);
    if (credit) state.credits = state.credits.filter(c => c.id !== credit.id);
  } else if (t.type === 'dealer') {
    state.cash += t.amount;
    if (company) company.balance -= companySide(t);
  } else if (t.type === 'settle') {
    const credit = findCreditForTxn(t);
    if (!credit) return { ok: false, msg: "Can't find the linked credit record for this payment." };
    state.cash -= t.amount;
    credit.remaining = Math.min(credit.amount, Math.round((credit.remaining + t.amount) * 100) / 100);
    credit.status = credit.remaining > 0.009 ? 'open' : 'paid';
  } else if (t.type === 'adjust') {
    if (company) company.balance -= t.amount;
  } else if (t.type === 'reconcile') {
    state.cash -= t.amount;
  }
  return { ok: true };
}

function deleteTransaction(id, password) {
  if (password !== CREDENTIALS.password) return { ok: false, msg: 'Incorrect password.' };
  const idx = state.transactions.findIndex(t => t.id === id);
  if (idx === -1) return { ok: false, msg: 'Transaction not found.' };
  const snapshot = JSON.parse(JSON.stringify(state));
  const rev = reverseAndUnlink(state.transactions[idx]);
  if (!rev.ok) { state = snapshot; return rev; }
  state.transactions.splice(idx, 1);
  saveState();
  return { ok: true };
}

function editTransaction(id, password, newAmount, newCompanyAmount, newCustomer, newNote) {
  if (password !== CREDENTIALS.password) return { ok: false, msg: 'Incorrect password.' };
  const t = state.transactions.find(x => x.id === id);
  if (!t) return { ok: false, msg: 'Transaction not found.' };
  newAmount = Number(newAmount);
  const isSigned = t.type === 'adjust' || t.type === 'reconcile';
  if (isSigned ? !newAmount : (!newAmount || newAmount <= 0)) {
    return { ok: false, msg: isSigned ? 'Enter a non-zero amount.' : 'Enter an amount greater than zero.' };
  }
  const needsCompanyAmount = t.type === 'sale' || t.type === 'credit' || t.type === 'dealer';
  let newCAmt = t.type === 'dealer' ? newAmount : Number(newCompanyAmount);
  if (needsCompanyAmount && (!newCAmt || newCAmt <= 0)) {
    return { ok: false, msg: 'Enter the reload value affecting the company balance.' };
  }

  const snapshot = JSON.parse(JSON.stringify(state));
  const rev = reverseAndUnlink(t);
  if (!rev.ok) { state = snapshot; return rev; }

  const tRef = state.transactions.find(x => x.id === id);
  const company = tRef.companyId ? getCompany(tRef.companyId) : null;

  if (tRef.type === 'sale' || tRef.type === 'credit') {
    if (company && newCAmt > company.balance + 0.001) { state = snapshot; return { ok: false, msg: `${company.name} only has ${formatCurrency(company.balance)} available.` }; }
    if (company) company.balance -= newCAmt;
    if (tRef.type === 'sale') {
      state.cash += newAmount;
    } else {
      if (!newCustomer || !newCustomer.trim()) { state = snapshot; return { ok: false, msg: "Enter the customer's name." }; }
      const creditId = uid();
      tRef.creditId = creditId;
      tRef.customer = newCustomer.trim();
      state.credits.push({ id: creditId, customer: newCustomer.trim(), companyId: tRef.companyId, amount: newAmount, dateKey: tRef.dateKey, remaining: newAmount, status: 'open' });
    }
    tRef.companyAmount = newCAmt;
  } else if (tRef.type === 'dealer') {
    if (newAmount > state.cash + 0.001) { state = snapshot; return { ok: false, msg: `Cash in hand is only ${formatCurrency(state.cash)}.` }; }
    state.cash -= newAmount;
    if (company) company.balance += newCAmt;
    tRef.companyAmount = newCAmt;
  } else if (tRef.type === 'settle') {
    const credit = findCreditForTxn(tRef);
    if (!credit) { state = snapshot; return { ok: false, msg: "Can't find the linked credit record." }; }
    if (newAmount > credit.remaining + 0.001) { state = snapshot; return { ok: false, msg: `Only ${formatCurrency(credit.remaining)} is owed on this credit.` }; }
    state.cash += newAmount;
    credit.remaining = Math.round((credit.remaining - newAmount) * 100) / 100;
    credit.status = credit.remaining <= 0.009 ? 'paid' : 'open';
  } else if (tRef.type === 'adjust') {
    if (company) company.balance += newAmount;
  } else if (tRef.type === 'reconcile') {
    state.cash += newAmount;
  }

  tRef.amount = newAmount;
  if (newNote !== undefined) tRef.note = newNote.trim();
  saveState();
  return { ok: true };
}

function reconcileCash(counted, note) {
  counted = Number(counted);
  if (isNaN(counted)) return { ok: false, msg: 'Enter the counted cash amount.' };
  const delta = Math.round((counted - state.cash) * 100) / 100;
  state.cash = counted;
  state.transactions.push({ id: uid(), ts: Date.now(), dateKey: dateKey(), type: 'reconcile', companyId: null, amount: delta, customer: '', note: note || 'Cash count' });
  saveState();
  return { ok: true, delta };
}

function addCompany(name, color, startingBalance) {
  name = (name || '').trim();
  if (!name) return { ok: false, msg: 'Enter a company name.' };
  let id = slugify(name);
  if (getCompany(id)) id = id + '-' + uid().slice(0, 4);
  const bal = Number(startingBalance) || 0;
  state.companies.push({ id, name, color: color || '#E3AE4D', balance: bal, archived: false });
  if (state.setupDone && bal !== 0) {
    state.transactions.push({ id: uid(), ts: Date.now(), dateKey: dateKey(), type: 'adjust', companyId: id, amount: bal, customer: '', note: 'Opening balance for new company' });
  }
  saveState();
  return { ok: true };
}
function updateCompanyMeta(id, name, color) {
  const c = getCompany(id); if (!c) return;
  if (name && name.trim()) c.name = name.trim();
  if (color) c.color = color;
  saveState();
}
function adjustCompanyBalance(id, delta, note) {
  const c = getCompany(id); if (!c) return { ok: false, msg: 'Company not found.' };
  delta = Number(delta);
  if (!delta) return { ok: false, msg: 'Enter a non-zero amount.' };
  c.balance += delta;
  state.transactions.push({ id: uid(), ts: Date.now(), dateKey: dateKey(), type: 'adjust', companyId: id, amount: delta, customer: '', note: note || 'Manual adjustment' });
  saveState();
  return { ok: true };
}
function setArchived(id, val) { const c = getCompany(id); if (c) { c.archived = val; saveState(); } }

/* ============================================================
   AGGREGATION
============================================================ */
function txnsBetween(fromKey, toKey) { return state.transactions.filter(t => t.dateKey >= fromKey && t.dateKey <= toKey); }
function summarize(txns) {
  const s = { sale: 0, credit: 0, dealer: 0, settle: 0, margin: 0, count: txns.length, perCompany: {} };
  state.companies.forEach(c => { s.perCompany[c.id] = { sold: 0, topup: 0 }; });
  txns.forEach(t => {
    s[t.type] = (s[t.type] || 0) + t.amount;
    if (t.type === 'sale' || t.type === 'credit') s.margin += (t.amount - companySide(t));
    if (t.companyId && s.perCompany[t.companyId]) {
      if (t.type === 'sale' || t.type === 'credit') s.perCompany[t.companyId].sold += companySide(t);
      if (t.type === 'dealer') s.perCompany[t.companyId].topup += t.amount;
    }
  });
  s.margin = Math.round(s.margin * 100) / 100;
  s.cashIn = s.sale + s.settle;
  s.cashOut = s.dealer;
  s.netCash = s.cashIn - s.cashOut;
  return s;
}
function addDays(key, n) {
  const [y, m, d] = key.split('-').map(Number);
  const dt = new Date(y, m - 1, d + n);
  return dateKey(dt);
}
function startOfWeek(key) {
  const [y, m, d] = key.split('-').map(Number);
  const dt = new Date(y, m - 1, d);
  const day = (dt.getDay() + 6) % 7;
  dt.setDate(dt.getDate() - day);
  return dateKey(dt);
}
function monthRange(year, month) {
  const first = dateKey(new Date(year, month, 1));
  const last = dateKey(new Date(year, month + 1, 0));
  return [first, last];
}

/* ============================================================
   UI HELPERS
============================================================ */
function toast(msg, type = 'good') {
  const root = document.getElementById('toast-root');
  const el = document.createElement('div');
  const color = type === 'good' ? 'border-good/40 text-good' : 'border-bad/40 text-bad';
  el.className = `toast bg-ink-900 border ${color} rounded-md px-4 py-2.5 text-sm shadow-lg max-w-xs`;
  el.textContent = msg;
  root.appendChild(el);
  setTimeout(() => { el.style.opacity = '0'; el.style.transition = 'opacity .3s'; setTimeout(() => el.remove(), 300); }, 2800);
}

function barChartSVG(data, opts = {}) {
  const w = opts.width || 680, h = opts.height || 200, pad = 30;
  const max = Math.max(1, ...data.map(d => d.value));
  const n = Math.max(1, data.length);
  const bw = (w - pad * 2) / n;
  let bars = '', labels = '';
  data.forEach((d, i) => {
    const bh = max > 0 ? (d.value / max) * (h - pad * 2 - 14) : 0;
    const x = pad + i * bw + bw * 0.2;
    const bwid = bw * 0.6;
    const y = h - pad - bh;
    bars += `<rect x="${x.toFixed(1)}" y="${y.toFixed(1)}" width="${bwid.toFixed(1)}" height="${bh.toFixed(1)}" rx="3" fill="${d.color || '#E3AE4D'}" opacity="0.92"><title>${d.label}: ${formatCurrency(d.value)}</title></rect>`;
    if (n <= 32) labels += `<text x="${(x + bwid / 2).toFixed(1)}" y="${h - 10}" font-size="9.5" fill="#8B97A4" text-anchor="middle" font-family="Inter">${d.label}</text>`;
  });
  return `<svg viewBox="0 0 ${w} ${h}" class="w-full h-auto">
    <line x1="${pad}" y1="${h - pad}" x2="${w - pad}" y2="${h - pad}" stroke="#2A343E" stroke-width="1"/>
    ${bars}${labels}
  </svg>`;
}

function companyOptions(selectedId) {
  return state.companies.filter(c => !c.archived).map(c => `<option value="${c.id}" ${c.id === selectedId ? 'selected' : ''}>${c.name} — ${formatCurrency(c.balance)} left</option>`).join('');
}

/* ============================================================
   PAGE: DASHBOARD
============================================================ */
function renderDashboard() {
  const el = document.getElementById('page-dashboard');
  const today = dateKey();
  const todayTxns = state.transactions.filter(t => t.dateKey === today);
  const s = summarize(todayTxns);
  const openCreditsTotal = state.credits.filter(c => c.status === 'open').reduce((a, c) => a + c.remaining, 0);
  const activeCompanies = state.companies.filter(c => !c.archived);

  el.innerHTML = `
    <div class="reveal">
      ${!state.setupDone ? `
        <div class="bg-ink-900 border border-gold/30 rounded-lg px-4 py-3 mb-6 flex items-center justify-between gap-3 flex-wrap">
          <p class="text-sm text-gold-soft">Set your starting cash and reload balances to begin.</p>
          <button onclick="openSetupModal()" class="text-xs font-medium bg-gold text-ink-950 rounded-md px-3 py-1.5 whitespace-nowrap">Set up now</button>
        </div>` : ''}

      <div class="bg-ink-900 border border-line rounded-lg p-6 mb-6">
        <p class="text-xs text-muted uppercase tracking-wide mb-1">Cash in hand</p>
        <p id="dash-cash" class="font-display font-extrabold text-4xl md:text-5xl text-gold tnum">${formatCurrency(state.cash)}</p>
        <p class="text-xs text-muted mt-2">${state.setupDone ? `Running since ${prettyDate(state.setupDate)}` : 'Not set up yet'}</p>
      </div>

      <p class="text-xs text-muted uppercase tracking-wide mb-2">Reload balances</p>
      <div class="grid grid-cols-2 md:grid-cols-4 gap-3 mb-6">
        ${activeCompanies.map(c => `
          <div class="bg-ink-900 border border-line rounded-lg pl-3 pr-4 py-3 flex items-center gap-3" style="border-left: 3px solid ${c.color}">
            <div class="w-8 h-8 rounded-full flex items-center justify-center text-xs font-bold shrink-0" style="background:${c.color}22; color:${c.color}">${c.name[0]}</div>
            <div class="min-w-0">
              <p class="text-xs text-muted truncate">${c.name}</p>
              <p class="font-display font-semibold text-sm tnum">${formatCurrency(c.balance)}</p>
            </div>
          </div>
        `).join('')}
        <button onclick="showPage('companies')" class="border border-dashed border-line rounded-lg flex items-center justify-center gap-2 text-xs text-muted hover:text-gold hover:border-gold/50 py-3">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12h14"/></svg>
          Add company
        </button>
      </div>

      <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-6">
        <div class="bg-ink-900 border border-line rounded-lg p-4">
          <p class="text-xs text-muted mb-1">Sold today (cash)</p>
          <p class="font-display font-semibold text-xl text-good tnum">${formatCurrency(s.sale)}</p>
        </div>
        <div class="bg-ink-900 border border-line rounded-lg p-4">
          <p class="text-xs text-muted mb-1">Given on credit today</p>
          <p class="font-display font-semibold text-xl text-amberc tnum">${formatCurrency(s.credit)}</p>
        </div>
        <div class="bg-ink-900 border border-line rounded-lg p-4">
          <p class="text-xs text-muted mb-1">Margin earned today</p>
          <p class="font-display font-semibold text-xl text-gold tnum">${formatCurrency(s.margin)}</p>
        </div>
        <div class="bg-ink-900 border border-line rounded-lg p-4">
          <p class="text-xs text-muted mb-1">Total credit outstanding</p>
          <p class="font-display font-semibold text-xl text-bad tnum">${formatCurrency(openCreditsTotal)}</p>
        </div>
      </div>

      <div class="flex flex-wrap gap-2.5 mb-6">
        <button onclick="showPage('transaction')" class="text-sm bg-ink-800 border border-line hover:border-gold/50 rounded-md px-4 py-2">Record a sale</button>
        <button onclick="openReconcileModal()" class="text-sm bg-ink-800 border border-line hover:border-gold/50 rounded-md px-4 py-2">Count cash</button>
        <button onclick="showPage('companies')" class="text-sm bg-ink-800 border border-line hover:border-gold/50 rounded-md px-4 py-2">Manage companies</button>
        <button onclick="showPage('credits')" class="text-sm bg-ink-800 border border-line hover:border-gold/50 rounded-md px-4 py-2">Credit book</button>
      </div>

      <div class="bg-ink-900 border border-line rounded-lg receipt-edge overflow-hidden">
        <div class="px-4 py-3 border-b border-line flex items-center justify-between">
          <p class="text-sm font-medium">Today's activity</p>
          <button onclick="showPage('reports')" class="text-xs text-muted hover:text-gold">See full reports</button>
        </div>
        ${renderTxnList(todayTxns.slice().reverse().slice(0, 8))}
      </div>
    </div>
  `;
}

function renderTxnList(txns) {
  if (!txns.length) return `<p class="text-sm text-muted text-center py-8">No transactions yet.</p>`;
  return `<div class="divide-y divide-line">
    ${txns.map(t => {
      const meta = TYPE_META[t.type];
      const company = t.companyId ? getCompany(t.companyId) : null;
      let sign, signColor, amt;
      if (t.type === 'dealer') { sign = '−'; signColor = 'text-bad'; amt = t.amount; }
      else if (t.type === 'sale') { sign = '+'; signColor = 'text-good'; amt = t.amount; }
      else if (t.type === 'credit') { sign = '+'; signColor = 'text-amberc'; amt = t.amount; }
      else if (t.type === 'settle') { sign = '+'; signColor = 'text-tealc'; amt = t.amount; }
      else { sign = t.amount >= 0 ? '+' : '−'; signColor = t.amount >= 0 ? 'text-good' : 'text-bad'; amt = Math.abs(t.amount); }
      const hasMargin = (t.type === 'sale' || t.type === 'credit') && t.companyAmount != null && Math.abs(t.companyAmount - t.amount) > 0.009;
      const marginBit = hasMargin ? `Company ${formatCurrency(t.companyAmount)} · Margin ${formatCurrency(t.amount - t.companyAmount)} · ` : '';
      return `<div class="px-4 py-3 flex items-center justify-between gap-3">
        <div class="min-w-0 flex items-center gap-3">
          <span class="w-2 h-2 rounded-full shrink-0" style="background:${meta.color}"></span>
          <div class="min-w-0">
            <p class="text-sm truncate">${meta.label}${company ? ' · ' + company.name : ''}</p>
            <p class="text-xs text-muted truncate">${t.customer ? t.customer + ' · ' : ''}${marginBit}${t.note ? t.note + ' · ' : ''}${new Date(t.ts).toLocaleTimeString('en-GB', { hour: '2-digit', minute: '2-digit' })}</p>
          </div>
        </div>
        <div class="flex items-center gap-1.5 shrink-0">
          <p class="text-sm font-medium tnum ${signColor}">${sign} ${formatCurrency(amt)}</p>
          <button class="txn-edit-btn p-1 rounded hover:bg-ink-800 text-muted hover:text-gold" data-txn="${t.id}" title="Edit" aria-label="Edit transaction">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 20h9"/><path d="M16.5 3.5a2.12 2.12 0 0 1 3 3L7 19l-4 1 1-4Z"/></svg>
          </button>
          <button class="txn-delete-btn p-1 rounded hover:bg-bad/10 text-muted hover:text-bad" data-txn="${t.id}" title="Delete" aria-label="Delete transaction">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 6h18"/><path d="M8 6V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/><path d="M19 6l-1 14a2 2 0 0 1-2 2H8a2 2 0 0 1-2-2L5 6"/></svg>
          </button>
        </div>
      </div>`;
    }).join('')}
  </div>`;
}

/* ============================================================
   PAGE: TRANSACTION
============================================================ */
let txnType = 'sale';
function renderTransactionPage() {
  const el = document.getElementById('page-transaction');

  if (!state.setupDone) {
    el.innerHTML = `<div class="reveal bg-ink-900 border border-line rounded-lg p-8 text-center">
      <p class="text-sm text-muted mb-4">Set up your starting cash and balances first.</p>
      <button onclick="openSetupModal()" class="text-sm bg-gold text-ink-950 rounded-md px-4 py-2 font-medium">Set up now</button>
    </div>`;
    return;
  }

  const tabs = [
    { id: 'sale', label: 'Customer sale (cash)' },
    { id: 'credit', label: 'Customer sale (credit)' },
    { id: 'dealer', label: 'Dealer top-up' },
  ];

  el.innerHTML = `
    <div class="reveal max-w-xl">
      <h2 class="font-display font-semibold text-lg mb-4">New transaction</h2>
      <div class="flex gap-2 mb-5 flex-wrap">
        ${tabs.map(t => `<button data-ttype="${t.id}" class="ttab text-xs px-3 py-2 rounded-md border ${txnType === t.id ? 'bg-gold text-ink-950 border-gold font-medium' : 'bg-ink-900 border-line text-muted'}">${t.label}</button>`).join('')}
      </div>

      <form id="txn-form" class="bg-ink-900 border border-line rounded-lg p-5 space-y-4">
        <label class="block">
          <span class="text-xs text-muted mb-1.5 block">Reload company</span>
          <select id="txn-company" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm">
            ${companyOptions()}
          </select>
        </label>
        ${txnType === 'dealer' ? `
        <label class="block">
          <span class="text-xs text-muted mb-1.5 block">Amount (Rs)</span>
          <input id="txn-amount" type="number" min="1" step="0.01" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm tnum" placeholder="0.00" />
        </label>` : `
        <label class="block">
          <span class="text-xs text-muted mb-1.5 block">Reload value (deducted from company balance)</span>
          <input id="txn-company-amount" type="number" min="0.01" step="0.01" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm tnum" placeholder="e.g. 797" />
        </label>
        <label class="block">
          <span class="text-xs text-muted mb-1.5 block">${txnType === 'sale' ? 'Amount to collect from customer (Rs)' : 'Amount the customer will owe (Rs)'}</span>
          <input id="txn-amount" type="number" min="0.01" step="0.01" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm tnum" placeholder="e.g. 800" />
        </label>
        <p id="txn-margin-preview" class="text-xs text-muted -mt-2"></p>
        `}
        ${txnType === 'credit' ? `
        <label class="block">
          <span class="text-xs text-muted mb-1.5 block">Customer name</span>
          <input id="txn-customer" type="text" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm" placeholder="Who is taking this on credit?" />
        </label>` : ''}
        <label class="block">
          <span class="text-xs text-muted mb-1.5 block">Note (optional)</span>
          <input id="txn-note" type="text" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm" placeholder="Any extra detail" />
        </label>
        <div id="txn-error" class="text-bad text-xs hidden"></div>
        <button type="submit" class="w-full bg-gold hover:bg-gold-soft text-ink-950 font-display font-semibold text-sm rounded-md py-2.5">
          ${txnType === 'sale' ? 'Record cash sale' : txnType === 'credit' ? 'Record credit sale' : 'Record dealer top-up'}
        </button>
      </form>
    </div>
  `;

  el.querySelectorAll('.ttab').forEach(btn => btn.addEventListener('click', () => { txnType = btn.dataset.ttype; renderTransactionPage(); }));

  if (txnType !== 'dealer') {
    const updateMarginPreview = () => {
      const cAmt = Number(document.getElementById('txn-company-amount').value) || 0;
      const amt = Number(document.getElementById('txn-amount').value) || 0;
      const preview = document.getElementById('txn-margin-preview');
      if (!cAmt && !amt) { preview.textContent = ''; return; }
      const margin = Math.round((amt - cAmt) * 100) / 100;
      preview.textContent = `Margin: ${margin >= 0 ? '+' : ''}${formatCurrency(margin)}`;
      preview.className = 'text-xs -mt-2 ' + (margin >= 0 ? 'text-good' : 'text-bad');
    };
    document.getElementById('txn-company-amount').addEventListener('input', updateMarginPreview);
    document.getElementById('txn-amount').addEventListener('input', updateMarginPreview);
  }

  document.getElementById('txn-form').addEventListener('submit', (e) => {
    e.preventDefault();
    const companyId = document.getElementById('txn-company').value;
    const amount = document.getElementById('txn-amount').value;
    const companyAmount = txnType === 'dealer' ? amount : document.getElementById('txn-company-amount').value;
    const customer = txnType === 'credit' ? document.getElementById('txn-customer').value : '';
    const note = document.getElementById('txn-note').value;
    const res = addTransaction({ type: txnType, companyId, companyAmount, amount, customer, note });
    const errEl = document.getElementById('txn-error');
    if (!res.ok) { errEl.textContent = res.msg; errEl.classList.remove('hidden'); return; }
    errEl.classList.add('hidden');
    toast(txnType === 'dealer' ? 'Top-up recorded' : 'Sale recorded');
    renderTransactionPage();
    updateHeader();
  });
}

/* ============================================================
   PAGE: COMPANIES (manage / add new networks)
============================================================ */
function renderCompaniesPage() {
  const el = document.getElementById('page-companies');
  const active = state.companies.filter(c => !c.archived);
  const archived = state.companies.filter(c => c.archived);

  el.innerHTML = `
    <div class="reveal">
      <h2 class="font-display font-semibold text-lg mb-1">Reload companies</h2>
      <p class="text-sm text-muted mb-5">Add any network you sell reload for — Hutch, Mobitel, Dialog, Airtel, or a new one whenever you start selling it.</p>

      <div class="bg-ink-900 border border-line rounded-lg divide-y divide-line mb-6">
        ${active.length ? active.map(c => `
          <div class="px-4 py-3 flex items-center justify-between gap-3 flex-wrap">
            <div class="flex items-center gap-3 min-w-0">
              <span class="w-3 h-3 rounded-full shrink-0" style="background:${c.color}"></span>
              <div class="min-w-0">
                <p class="text-sm font-medium truncate">${c.name}</p>
                <p class="text-xs text-muted tnum">Balance: ${formatCurrency(c.balance)}</p>
              </div>
            </div>
            <div class="flex items-center gap-2">
              <button data-edit="${c.id}" class="edit-co-btn text-xs bg-ink-800 border border-line rounded-md px-3 py-1.5 hover:border-gold/50">Edit</button>
              <button data-adjust="${c.id}" class="adjust-co-btn text-xs bg-ink-800 border border-line rounded-md px-3 py-1.5 hover:border-gold/50">Adjust balance</button>
              <button data-archive="${c.id}" class="archive-co-btn text-xs text-bad rounded-md px-3 py-1.5 border border-bad/30 hover:bg-bad/10">Archive</button>
            </div>
          </div>`).join('') : `<p class="text-sm text-muted text-center py-8">No companies yet — add your first one below.</p>`}
      </div>

      <details class="mb-6" open>
        <summary class="text-sm text-muted cursor-pointer select-none mb-3">Add a new company</summary>
        <form id="add-co-form" class="bg-ink-900 border border-line rounded-lg p-5 space-y-4 max-w-md">
          <label class="block">
            <span class="text-xs text-muted mb-1.5 block">Company name</span>
            <input id="co-name" type="text" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm" placeholder="e.g. Lyca Mobile" />
          </label>
          <label class="block">
            <span class="text-xs text-muted mb-1.5 block">Colour</span>
            <input id="co-color" type="color" value="#5B8DEF" class="w-16 h-10 bg-ink-800 border border-line rounded-md p-1" />
          </label>
          <label class="block">
            <span class="text-xs text-muted mb-1.5 block">Starting balance (Rs)</span>
            <input id="co-balance" type="number" min="0" step="0.01" value="0" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm tnum" />
          </label>
          <div id="co-error" class="text-bad text-xs hidden"></div>
          <button type="submit" class="w-full bg-gold hover:bg-gold-soft text-ink-950 font-display font-semibold text-sm rounded-md py-2.5">Add company</button>
        </form>
      </details>

      ${archived.length ? `
      <details>
        <summary class="text-sm text-muted cursor-pointer select-none mb-3">Archived companies (${archived.length})</summary>
        <div class="bg-ink-900 border border-line rounded-lg divide-y divide-line max-w-md">
          ${archived.map(c => `
            <div class="px-4 py-3 flex items-center justify-between gap-3">
              <span class="text-sm text-muted">${c.name}</span>
              <button data-restore="${c.id}" class="restore-co-btn text-xs bg-ink-800 border border-line rounded-md px-3 py-1.5 hover:border-gold/50">Restore</button>
            </div>`).join('')}
        </div>
      </details>` : ''}
    </div>

    <div id="edit-co-modal" class="hidden fixed inset-0 z-40 items-center justify-center bg-black/60 p-4">
      <div class="bg-ink-900 border border-line rounded-lg max-w-sm w-full p-6">
        <h3 class="font-display font-semibold text-base mb-4">Edit company</h3>
        <form id="edit-co-form" class="space-y-4">
          <input type="hidden" id="edit-co-id" />
          <label class="block">
            <span class="text-xs text-muted mb-1.5 block">Name</span>
            <input id="edit-co-name" type="text" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm" />
          </label>
          <label class="block">
            <span class="text-xs text-muted mb-1.5 block">Colour</span>
            <input id="edit-co-color" type="color" class="w-16 h-10 bg-ink-800 border border-line rounded-md p-1" />
          </label>
          <div class="flex gap-2">
            <button type="button" id="edit-co-cancel" class="flex-1 text-sm text-muted rounded-md py-2.5 border border-line">Cancel</button>
            <button type="submit" class="flex-1 bg-gold text-ink-950 font-display font-semibold text-sm rounded-md py-2.5">Save</button>
          </div>
        </form>
      </div>
    </div>

    <div id="adjust-co-modal" class="hidden fixed inset-0 z-40 items-center justify-center bg-black/60 p-4">
      <div class="bg-ink-900 border border-line rounded-lg max-w-sm w-full p-6">
        <h3 class="font-display font-semibold text-base mb-1">Adjust balance</h3>
        <p id="adjust-co-info" class="text-sm text-muted mb-4"></p>
        <form id="adjust-co-form" class="space-y-4">
          <input type="hidden" id="adjust-co-id" />
          <label class="block">
            <span class="text-xs text-muted mb-1.5 block">Change amount (Rs) — use a minus sign to reduce</span>
            <input id="adjust-co-amount" type="number" step="0.01" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm tnum" placeholder="e.g. -200 or 500" />
          </label>
          <label class="block">
            <span class="text-xs text-muted mb-1.5 block">Reason</span>
            <input id="adjust-co-note" type="text" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm" placeholder="e.g. stock recount" />
          </label>
          <div id="adjust-co-error" class="text-bad text-xs hidden"></div>
          <div class="flex gap-2">
            <button type="button" id="adjust-co-cancel" class="flex-1 text-sm text-muted rounded-md py-2.5 border border-line">Cancel</button>
            <button type="submit" class="flex-1 bg-gold text-ink-950 font-display font-semibold text-sm rounded-md py-2.5">Save</button>
          </div>
        </form>
      </div>
    </div>
  `;

  document.getElementById('add-co-form').addEventListener('submit', (e) => {
    e.preventDefault();
    const name = document.getElementById('co-name').value;
    const color = document.getElementById('co-color').value;
    const bal = document.getElementById('co-balance').value;
    const res = addCompany(name, color, bal);
    const err = document.getElementById('co-error');
    if (!res.ok) { err.textContent = res.msg; err.classList.remove('hidden'); return; }
    toast('Company added');
    renderCompaniesPage(); renderDashboard();
  });

  el.querySelectorAll('.edit-co-btn').forEach(btn => btn.addEventListener('click', () => {
    const c = getCompany(btn.dataset.edit);
    document.getElementById('edit-co-id').value = c.id;
    document.getElementById('edit-co-name').value = c.name;
    document.getElementById('edit-co-color').value = c.color;
    const modal = document.getElementById('edit-co-modal'); modal.classList.remove('hidden'); modal.classList.add('flex');
  }));
  document.getElementById('edit-co-cancel')?.addEventListener('click', () => { document.getElementById('edit-co-modal').classList.add('hidden'); document.getElementById('edit-co-modal').classList.remove('flex'); });
  document.getElementById('edit-co-form')?.addEventListener('submit', (e) => {
    e.preventDefault();
    updateCompanyMeta(document.getElementById('edit-co-id').value, document.getElementById('edit-co-name').value, document.getElementById('edit-co-color').value);
    document.getElementById('edit-co-modal').classList.add('hidden'); document.getElementById('edit-co-modal').classList.remove('flex');
    toast('Company updated');
    renderCompaniesPage(); renderDashboard();
  });

  el.querySelectorAll('.adjust-co-btn').forEach(btn => btn.addEventListener('click', () => {
    const c = getCompany(btn.dataset.adjust);
    document.getElementById('adjust-co-id').value = c.id;
    document.getElementById('adjust-co-info').textContent = `${c.name} — current balance ${formatCurrency(c.balance)}`;
    document.getElementById('adjust-co-amount').value = '';
    document.getElementById('adjust-co-note').value = '';
    const modal = document.getElementById('adjust-co-modal'); modal.classList.remove('hidden'); modal.classList.add('flex');
  }));
  document.getElementById('adjust-co-cancel')?.addEventListener('click', () => { document.getElementById('adjust-co-modal').classList.add('hidden'); document.getElementById('adjust-co-modal').classList.remove('flex'); });
  document.getElementById('adjust-co-form')?.addEventListener('submit', (e) => {
    e.preventDefault();
    const id = document.getElementById('adjust-co-id').value;
    const amt = document.getElementById('adjust-co-amount').value;
    const note = document.getElementById('adjust-co-note').value;
    const res = adjustCompanyBalance(id, amt, note);
    const err = document.getElementById('adjust-co-error');
    if (!res.ok) { err.textContent = res.msg; err.classList.remove('hidden'); return; }
    document.getElementById('adjust-co-modal').classList.add('hidden'); document.getElementById('adjust-co-modal').classList.remove('flex');
    toast('Balance adjusted');
    renderCompaniesPage(); renderDashboard();
  });

  el.querySelectorAll('.archive-co-btn').forEach(btn => btn.addEventListener('click', () => {
    if (!confirm('Archive this company? It will be hidden from sales but its history stays in reports.')) return;
    setArchived(btn.dataset.archive, true);
    renderCompaniesPage(); renderDashboard();
  }));
  el.querySelectorAll('.restore-co-btn').forEach(btn => btn.addEventListener('click', () => {
    setArchived(btn.dataset.restore, false);
    renderCompaniesPage(); renderDashboard();
  }));
}

/* ============================================================
   PAGE: REPORTS
============================================================ */
let reportTab = 'daily';
let reportAnchor = { daily: dateKey(), weekly: startOfWeek(dateKey()), monthly: dateKey().slice(0, 7), yearly: String(new Date().getFullYear()) };

function renderReportsPage() {
  const el = document.getElementById('page-reports');
  const tabs = [['daily', 'Daily'], ['weekly', 'Weekly'], ['monthly', 'Monthly'], ['yearly', 'Yearly']];

  el.innerHTML = `
    <div class="reveal">
      <h2 class="font-display font-semibold text-lg mb-4">Reports</h2>
      <div class="flex gap-2 mb-5 flex-wrap">
        ${tabs.map(([id, label]) => `<button data-rtab="${id}" class="rtab text-xs px-3 py-2 rounded-md border ${reportTab === id ? 'bg-gold text-ink-950 border-gold font-medium' : 'bg-ink-900 border-line text-muted'}">${label}</button>`).join('')}
      </div>
      <div id="report-body"></div>
    </div>
  `;
  el.querySelectorAll('.rtab').forEach(btn => btn.addEventListener('click', () => { reportTab = btn.dataset.rtab; renderReportsPage(); }));
  renderReportBody();
}

function reportRangeLabel() {
  if (reportTab === 'daily') return prettyDate(reportAnchor.daily);
  if (reportTab === 'weekly') { const end = addDays(reportAnchor.weekly, 6); return `${prettyDate(reportAnchor.weekly)} – ${prettyDate(end)}`; }
  if (reportTab === 'monthly') { const [y, m] = reportAnchor.monthly.split('-').map(Number); return new Date(y, m - 1, 1).toLocaleDateString('en-GB', { month: 'long', year: 'numeric' }); }
  return reportAnchor.yearly;
}

function shiftReport(dir) {
  if (reportTab === 'daily') reportAnchor.daily = addDays(reportAnchor.daily, dir);
  else if (reportTab === 'weekly') reportAnchor.weekly = addDays(reportAnchor.weekly, dir * 7);
  else if (reportTab === 'monthly') {
    let [y, m] = reportAnchor.monthly.split('-').map(Number);
    m += dir; if (m < 1) { m = 12; y--; } if (m > 12) { m = 1; y++; }
    reportAnchor.monthly = `${y}-${String(m).padStart(2, '0')}`;
  } else { reportAnchor.yearly = String(Number(reportAnchor.yearly) + dir); }
  renderReportBody();
}

function renderReportBody() {
  const body = document.getElementById('report-body');
  let fromKey, toKey, chartData = [], txns = [];
  const activeCompanies = state.companies.filter(c => !c.archived);

  if (reportTab === 'daily') {
    fromKey = toKey = reportAnchor.daily;
    txns = txnsBetween(fromKey, toKey);
    chartData = activeCompanies.map(c => {
      const cs = summarize(txns.filter(t => t.companyId === c.id));
      return { label: c.name, value: cs.perCompany[c.id].sold, color: c.color };
    });
  } else if (reportTab === 'weekly') {
    fromKey = reportAnchor.weekly; toKey = addDays(fromKey, 6);
    txns = txnsBetween(fromKey, toKey);
    chartData = Array.from({ length: 7 }, (_, i) => {
      const k = addDays(fromKey, i);
      const day = summarize(txnsBetween(k, k));
      return { label: k.slice(8, 10) + '/' + k.slice(5, 7), value: Object.values(day.perCompany).reduce((a, p) => a + p.sold, 0), color: '#E3AE4D' };
    });
  } else if (reportTab === 'monthly') {
    const [y, m] = reportAnchor.monthly.split('-').map(Number);
    [fromKey, toKey] = monthRange(y, m - 1);
    txns = txnsBetween(fromKey, toKey);
    const days = Number(toKey.slice(8, 10));
    chartData = Array.from({ length: days }, (_, i) => {
      const k = `${reportAnchor.monthly}-${String(i + 1).padStart(2, '0')}`;
      const day = summarize(txnsBetween(k, k));
      return { label: String(i + 1), value: Object.values(day.perCompany).reduce((a, p) => a + p.sold, 0), color: '#E3AE4D' };
    });
  } else {
    const y = Number(reportAnchor.yearly);
    fromKey = `${y}-01-01`; toKey = `${y}-12-31`;
    txns = txnsBetween(fromKey, toKey);
    chartData = Array.from({ length: 12 }, (_, i) => {
      const [f, t] = monthRange(y, i);
      const mon = summarize(txnsBetween(f, t));
      return { label: new Date(y, i, 1).toLocaleDateString('en-GB', { month: 'short' }), value: Object.values(mon.perCompany).reduce((a, p) => a + p.sold, 0), color: '#E3AE4D' };
    });
  }

  const s = summarize(txns);
  const companyCards = state.companies.filter(c => !c.archived || s.perCompany[c.id].sold || s.perCompany[c.id].topup);

  body.innerHTML = `
    <div class="flex items-center justify-between mb-4 bg-ink-900 border border-line rounded-lg px-4 py-2.5">
      <button onclick="shiftReport(-1)" class="p-1.5 rounded-md hover:bg-ink-800 text-muted hover:text-paper" aria-label="Previous period">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M15 18l-6-6 6-6"/></svg>
      </button>
      <p class="text-sm font-medium">${reportRangeLabel()}</p>
      <button onclick="shiftReport(1)" class="p-1.5 rounded-md hover:bg-ink-800 text-muted hover:text-paper" aria-label="Next period">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 18l6-6-6-6"/></svg>
      </button>
    </div>

    <div class="grid grid-cols-2 md:grid-cols-5 gap-3 mb-5">
      <div class="bg-ink-900 border border-line rounded-lg p-3"><p class="text-xs text-muted mb-1">Sold (cash)</p><p class="font-display font-semibold text-good tnum">${formatCurrency(s.sale)}</p></div>
      <div class="bg-ink-900 border border-line rounded-lg p-3"><p class="text-xs text-muted mb-1">Sold (credit)</p><p class="font-display font-semibold text-amberc tnum">${formatCurrency(s.credit)}</p></div>
      <div class="bg-ink-900 border border-line rounded-lg p-3"><p class="text-xs text-muted mb-1">Margin earned</p><p class="font-display font-semibold text-gold tnum">${formatCurrency(s.margin)}</p></div>
      <div class="bg-ink-900 border border-line rounded-lg p-3"><p class="text-xs text-muted mb-1">Dealer top-ups</p><p class="font-display font-semibold text-bluec tnum">${formatCurrency(s.dealer)}</p></div>
      <div class="bg-ink-900 border border-line rounded-lg p-3"><p class="text-xs text-muted mb-1">Credit collected</p><p class="font-display font-semibold text-tealc tnum">${formatCurrency(s.settle)}</p></div>
    </div>

    <div class="bg-ink-900 border border-line rounded-lg p-4 mb-5">
      <p class="text-xs text-muted uppercase tracking-wide mb-3">Reload sold ${reportTab === 'daily' ? 'by company' : 'over time'}</p>
      ${barChartSVG(chartData)}
    </div>

    <div class="grid grid-cols-2 md:grid-cols-4 gap-3 mb-5">
      ${companyCards.map(c => `
        <div class="bg-ink-900 border border-line rounded-lg pl-3 pr-3 py-2.5" style="border-left:3px solid ${c.color}">
          <p class="text-xs text-muted">${c.name}</p>
          <p class="text-sm tnum">Sold ${formatCurrency(s.perCompany[c.id].sold)}</p>
          <p class="text-xs text-muted tnum">Top-up ${formatCurrency(s.perCompany[c.id].topup)}</p>
        </div>`).join('')}
    </div>

    <div class="bg-ink-900 border border-line rounded-lg receipt-edge overflow-hidden">
      <div class="px-4 py-3 border-b border-line flex items-center justify-between">
        <p class="text-sm font-medium">Transactions (${txns.length})</p>
      </div>
      <div class="max-h-96 overflow-y-auto">
        ${renderTxnList(txns.slice().reverse())}
      </div>
    </div>
  `;
}

/* ============================================================
   PAGE: CREDIT BOOK
============================================================ */
let creditFilter = 'open';
function renderCreditsPage() {
  const el = document.getElementById('page-credits');
  const list = state.credits.filter(c => creditFilter === 'all' || c.status === creditFilter).slice().reverse();
  const totalOpen = state.credits.filter(c => c.status === 'open').reduce((a, c) => a + c.remaining, 0);

  el.innerHTML = `
    <div class="reveal">
      <h2 class="font-display font-semibold text-lg mb-1">Credit book</h2>
      <p class="text-sm text-muted mb-5">Customers who took reload now, to pay later.</p>

      <div class="bg-ink-900 border border-line rounded-lg p-5 mb-5">
        <p class="text-xs text-muted uppercase tracking-wide mb-1">Total outstanding</p>
        <p class="font-display font-bold text-3xl text-bad tnum">${formatCurrency(totalOpen)}</p>
      </div>

      <div class="flex gap-2 mb-4">
        ${[['open', 'Outstanding'], ['paid', 'Paid'], ['all', 'All']].map(([id, label]) => `<button data-cf="${id}" class="cftab text-xs px-3 py-2 rounded-md border ${creditFilter === id ? 'bg-gold text-ink-950 border-gold font-medium' : 'bg-ink-900 border-line text-muted'}">${label}</button>`).join('')}
      </div>

      <div class="bg-ink-900 border border-line rounded-lg divide-y divide-line">
        ${list.length ? list.map(c => {
          const company = getCompany(c.companyId);
          return `<div class="px-4 py-3 flex items-center justify-between gap-3 flex-wrap">
            <div>
              <p class="text-sm font-medium">${c.customer}</p>
              <p class="text-xs text-muted">${company ? company.name : ''} · given ${prettyDate(c.dateKey)}${c.status === 'paid' ? ' · <span class="text-good">paid in full</span>' : ''}</p>
            </div>
            <div class="flex items-center gap-3">
              <p class="text-sm tnum ${c.status === 'open' ? 'text-bad' : 'text-muted line-through'}">${formatCurrency(c.remaining || c.amount)}</p>
              ${c.status === 'open' ? `<button data-settle="${c.id}" class="settle-btn text-xs bg-gold text-ink-950 rounded-md px-3 py-1.5 font-medium">Collect</button>` : ''}
            </div>
          </div>`;
        }).join('') : `<p class="text-sm text-muted text-center py-8">Nothing here.</p>`}
      </div>
    </div>

    <div id="settle-modal" class="hidden fixed inset-0 z-40 items-center justify-center bg-black/60 p-4">
      <div class="bg-ink-900 border border-line rounded-lg max-w-sm w-full p-6">
        <h3 class="font-display font-semibold text-base mb-4">Collect payment</h3>
        <form id="settle-form" class="space-y-4">
          <input type="hidden" id="settle-credit-id" />
          <p id="settle-info" class="text-sm text-muted"></p>
          <label class="block">
            <span class="text-xs text-muted mb-1.5 block">Amount received (Rs)</span>
            <input id="settle-amount" type="number" min="0.01" step="0.01" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm tnum" />
          </label>
          <div class="flex gap-2">
            <button type="button" id="settle-cancel" class="flex-1 text-sm text-muted rounded-md py-2.5 border border-line">Cancel</button>
            <button type="submit" class="flex-1 bg-gold text-ink-950 font-display font-semibold text-sm rounded-md py-2.5">Confirm</button>
          </div>
        </form>
      </div>
    </div>
  `;

  el.querySelectorAll('.cftab').forEach(btn => btn.addEventListener('click', () => { creditFilter = btn.dataset.cf; renderCreditsPage(); }));

  el.querySelectorAll('.settle-btn').forEach(btn => btn.addEventListener('click', () => {
    const credit = state.credits.find(c => c.id === btn.dataset.settle);
    document.getElementById('settle-credit-id').value = credit.id;
    document.getElementById('settle-info').textContent = `${credit.customer} owes ${formatCurrency(credit.remaining)}`;
    document.getElementById('settle-amount').value = credit.remaining;
    const modal = document.getElementById('settle-modal');
    modal.classList.remove('hidden'); modal.classList.add('flex');
  }));
  document.getElementById('settle-cancel')?.addEventListener('click', () => {
    const modal = document.getElementById('settle-modal');
    modal.classList.add('hidden'); modal.classList.remove('flex');
  });
  document.getElementById('settle-form')?.addEventListener('submit', (e) => {
    e.preventDefault();
    const id = document.getElementById('settle-credit-id').value;
    const amt = document.getElementById('settle-amount').value;
    const res = settleCredit(id, amt);
    if (!res.ok) { toast(res.msg, 'bad'); return; }
    toast(`Collected ${formatCurrency(res.amt)}`);
    document.getElementById('settle-modal').classList.add('hidden');
    renderCreditsPage(); renderDashboard(); updateHeader();
  });
}

/* ============================================================
   NAVIGATION / HEADER / CLOCK
============================================================ */
const RENDERERS = { dashboard: renderDashboard, transaction: renderTransactionPage, companies: renderCompaniesPage, reports: renderReportsPage, credits: renderCreditsPage };
let currentPage = 'dashboard';

function showPage(name) {
  currentPage = name;
  document.querySelectorAll('.page').forEach(p => p.classList.add('hidden'));
  document.getElementById('page-' + name).classList.remove('hidden');
  document.querySelectorAll('.nav-btn').forEach(b => b.classList.toggle('active', b.dataset.page === name));
  document.querySelectorAll('.mnav-btn').forEach(b => b.classList.toggle('text-gold', b.dataset.page === name));
  document.querySelectorAll('.mnav-btn').forEach(b => b.classList.toggle('text-muted', b.dataset.page !== name));
  RENDERERS[name]();
}
function refreshCurrentPage() { RENDERERS[currentPage](); }

function updateHeader() { document.getElementById('header-cash').textContent = formatCurrency(state.cash); }
function tickClock() {
  const now = new Date();
  document.getElementById('header-date').textContent = now.toLocaleDateString('en-GB', { weekday: 'long', day: 'numeric', month: 'long', year: 'numeric' });
  document.getElementById('header-clock').textContent = now.toLocaleTimeString('en-GB', { hour: '2-digit', minute: '2-digit', second: '2-digit' });
}

/* ============================================================
   SETUP MODAL / RECONCILE MODAL
============================================================ */
function openSetupModal() {
  document.getElementById('setup-cash').value = state.cash || '';
  const wrap = document.getElementById('setup-companies');
  wrap.innerHTML = state.companies.filter(c => !c.archived).map(c => `
    <label class="block">
      <span class="text-xs mb-1.5 flex items-center gap-1.5"><span class="w-2 h-2 rounded-full" style="background:${c.color}"></span>${c.name}</span>
      <input data-company="${c.id}" type="number" min="0" step="0.01" value="${c.balance || 0}" class="su-company w-full bg-ink-800 border border-line rounded-md px-3 py-2 text-sm tnum" />
    </label>`).join('');
  const modal = document.getElementById('setup-modal');
  modal.classList.remove('hidden'); modal.classList.add('flex');
}
document.getElementById('setup-form').addEventListener('submit', (e) => {
  e.preventDefault();
  const cash = document.getElementById('setup-cash').value;
  const balances = {};
  document.querySelectorAll('.su-company').forEach(inp => balances[inp.dataset.company] = inp.value);
  completeSetup(cash, balances);
  document.getElementById('setup-modal').classList.add('hidden'); document.getElementById('setup-modal').classList.remove('flex');
  toast('Register set up');
  showPage('dashboard'); updateHeader();
});

function openReconcileModal() {
  document.getElementById('reconcile-amount').value = state.cash;
  document.getElementById('reconcile-note').value = '';
  document.getElementById('reconcile-current').textContent = `Currently showing ${formatCurrency(state.cash)} in the system.`;
  const modal = document.getElementById('reconcile-modal');
  modal.classList.remove('hidden'); modal.classList.add('flex');
}
document.getElementById('reconcile-cancel').addEventListener('click', () => {
  document.getElementById('reconcile-modal').classList.add('hidden'); document.getElementById('reconcile-modal').classList.remove('flex');
});
document.getElementById('reconcile-form').addEventListener('submit', (e) => {
  e.preventDefault();
  const counted = document.getElementById('reconcile-amount').value;
  const note = document.getElementById('reconcile-note').value;
  const res = reconcileCash(counted, note);
  if (!res.ok) { toast(res.msg, 'bad'); return; }
  document.getElementById('reconcile-modal').classList.add('hidden'); document.getElementById('reconcile-modal').classList.remove('flex');
  if (Math.abs(res.delta) > 0.009) toast(`Cash adjusted by ${res.delta > 0 ? '+' : ''}${formatCurrency(res.delta)}`, res.delta < 0 ? 'bad' : 'good');
  else toast('Cash matches — no adjustment needed');
  renderDashboard(); updateHeader();
});

/* ============================================================
   EDIT / DELETE TRANSACTION MODAL
============================================================ */
let pendingTxn = null;

function openTxnAction(id, mode) {
  const t = state.transactions.find(x => x.id === id);
  if (!t) return;
  pendingTxn = { id, mode };
  const meta = TYPE_META[t.type];
  const company = t.companyId ? getCompany(t.companyId) : null;
  const title = document.getElementById('txn-action-title');
  const sub = document.getElementById('txn-action-sub');
  const fields = document.getElementById('txn-action-fields');
  const confirmBtn = document.getElementById('txn-action-confirm');
  document.getElementById('txn-action-error').classList.add('hidden');
  document.getElementById('txn-action-password').value = '';

  if (mode === 'delete') {
    title.textContent = 'Delete transaction';
    sub.textContent = `${meta.label}${company ? ' · ' + company.name : ''} — ${formatCurrency(Math.abs(t.amount))}`;
    fields.innerHTML = `<p class="text-sm text-muted">This removes the entry and reverses its effect on cash and balances. This can't be undone.</p>`;
    confirmBtn.textContent = 'Delete';
    confirmBtn.className = 'flex-1 font-display font-semibold text-sm rounded-md py-2.5 bg-bad/20 text-bad border border-bad/40';
  } else {
    title.textContent = 'Edit transaction';
    sub.textContent = `${meta.label}${company ? ' · ' + company.name : ''}`;
    const showCustomer = t.type === 'credit' || t.type === 'settle';
    const showCompanyAmount = t.type === 'sale' || t.type === 'credit';
    const amountLabel = (t.type === 'adjust' || t.type === 'reconcile') ? 'Amount (Rs) — use a minus sign to reduce'
      : t.type === 'sale' ? 'Amount collected from customer (Rs)'
      : t.type === 'credit' ? 'Amount the customer owes (Rs)'
      : 'Amount (Rs)';
    fields.innerHTML = `
      ${showCompanyAmount ? `<label class="block">
        <span class="text-xs text-muted mb-1.5 block">Reload value (deducted from company balance)</span>
        <input id="txn-action-company-amount" type="number" step="0.01" value="${t.companyAmount != null ? t.companyAmount : t.amount}" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm tnum" />
      </label>` : ''}
      <label class="block">
        <span class="text-xs text-muted mb-1.5 block">${amountLabel}</span>
        <input id="txn-action-amount" type="number" step="0.01" value="${t.amount}" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm tnum" />
      </label>
      ${showCustomer ? `<label class="block">
        <span class="text-xs text-muted mb-1.5 block">Customer name</span>
        <input id="txn-action-customer" type="text" value="${t.customer || ''}" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm" />
      </label>` : ''}
      <label class="block">
        <span class="text-xs text-muted mb-1.5 block">Note</span>
        <input id="txn-action-note" type="text" value="${t.note || ''}" class="w-full bg-ink-800 border border-line rounded-md px-3 py-2.5 text-sm" />
      </label>
    `;
    confirmBtn.textContent = 'Save changes';
    confirmBtn.className = 'flex-1 font-display font-semibold text-sm rounded-md py-2.5 bg-gold text-ink-950';
  }

  const modal = document.getElementById('txn-action-modal');
  modal.classList.remove('hidden'); modal.classList.add('flex');
}

document.addEventListener('click', (e) => {
  const editBtn = e.target.closest('.txn-edit-btn');
  if (editBtn) { openTxnAction(editBtn.dataset.txn, 'edit'); return; }
  const delBtn = e.target.closest('.txn-delete-btn');
  if (delBtn) { openTxnAction(delBtn.dataset.txn, 'delete'); return; }
});

document.getElementById('txn-action-cancel').addEventListener('click', () => {
  document.getElementById('txn-action-modal').classList.add('hidden');
  document.getElementById('txn-action-modal').classList.remove('flex');
  pendingTxn = null;
});

document.getElementById('txn-action-form').addEventListener('submit', (e) => {
  e.preventDefault();
  if (!pendingTxn) return;
  const password = document.getElementById('txn-action-password').value;
  const errEl = document.getElementById('txn-action-error');
  let res;
  if (pendingTxn.mode === 'delete') {
    res = deleteTransaction(pendingTxn.id, password);
  } else {
    const amount = document.getElementById('txn-action-amount').value;
    const companyAmountEl = document.getElementById('txn-action-company-amount');
    const companyAmount = companyAmountEl ? companyAmountEl.value : undefined;
    const customerEl = document.getElementById('txn-action-customer');
    const customer = customerEl ? customerEl.value : undefined;
    const note = document.getElementById('txn-action-note').value;
    res = editTransaction(pendingTxn.id, password, amount, companyAmount, customer, note);
  }
  if (!res.ok) { errEl.textContent = res.msg; errEl.classList.remove('hidden'); return; }
  document.getElementById('txn-action-modal').classList.add('hidden');
  document.getElementById('txn-action-modal').classList.remove('flex');
  toast(pendingTxn.mode === 'delete' ? 'Transaction deleted' : 'Transaction updated');
  pendingTxn = null;
  refreshCurrentPage();
  updateHeader();
});

/* ============================================================
   LOGIN / LOGOUT
============================================================ */
document.getElementById('login-form').addEventListener('submit', (e) => {
  e.preventDefault();
  const u = document.getElementById('login-username').value.trim();
  const p = document.getElementById('login-password').value;
  const errEl = document.getElementById('login-error');
  if (u === CREDENTIALS.username && p === CREDENTIALS.password) {
    errEl.classList.add('hidden');
    localStorage.setItem(AUTH_KEY, '1');
    enterApp();
  } else {
    errEl.textContent = 'Wrong username or password.';
    errEl.classList.remove('hidden');
  }
});

function enterApp() {
  document.getElementById('login-screen').classList.add('hidden');
  const app = document.getElementById('app');
  app.classList.remove('hidden');
  app.classList.add('unlock-anim');
  showPage('dashboard');
  updateHeader();
  tickClock();
  if (!state.setupDone) openSetupModal();
}

document.getElementById('logout-btn').addEventListener('click', () => {
  localStorage.removeItem(AUTH_KEY);
  document.getElementById('app').classList.add('hidden');
  document.getElementById('login-screen').classList.remove('hidden');
  document.getElementById('login-username').value = '';
  document.getElementById('login-password').value = '';
});

document.getElementById('sidebar-nav').addEventListener('click', (e) => {
  const btn = e.target.closest('.nav-btn'); if (btn) showPage(btn.dataset.page);
});
document.querySelectorAll('.mnav-btn').forEach(btn => btn.addEventListener('click', () => showPage(btn.dataset.page)));

/* ============================================================
   SETTINGS: EXPORT / IMPORT / RESET
============================================================ */
const settingsModal = document.getElementById('settings-modal');
document.getElementById('settings-btn').addEventListener('click', () => { settingsModal.classList.remove('hidden'); settingsModal.classList.add('flex'); });
document.getElementById('settings-close').addEventListener('click', () => { settingsModal.classList.add('hidden'); settingsModal.classList.remove('flex'); });

document.getElementById('export-btn').addEventListener('click', () => {
  const blob = new Blob([JSON.stringify(state, null, 2)], { type: 'application/json' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url; a.download = `reload-register-backup-${dateKey()}.json`;
  a.click();
  URL.revokeObjectURL(url);
});

document.getElementById('import-input').addEventListener('change', (e) => {
  const file = e.target.files[0]; if (!file) return;
  const reader = new FileReader();
  reader.onload = () => {
    try {
      const parsed = JSON.parse(reader.result);
      if (!parsed.companies || !parsed.transactions) throw new Error('bad file');
      parsed.companies.forEach(c => { if (c.archived === undefined) c.archived = false; });
      if (parsed.setupDone === undefined) parsed.setupDone = true;
      if (!parsed.credits) parsed.credits = [];
      state = parsed; saveState();
      toast('Backup restored');
      settingsModal.classList.add('hidden'); settingsModal.classList.remove('flex');
      showPage('dashboard'); updateHeader();
    } catch (err) { toast('Could not read that file', 'bad'); }
  };
  reader.readAsText(file);
});

document.getElementById('reset-btn').addEventListener('click', () => {
  if (!confirm('This clears every transaction, balance and credit record on this device. Continue?')) return;
  if (!confirm('Are you absolutely sure? This cannot be undone.')) return;
  state = defaultState(); saveState();
  toast('All data cleared');
  settingsModal.classList.add('hidden'); settingsModal.classList.remove('flex');
  showPage('dashboard'); updateHeader();
});

/* ============================================================
   BOOT
============================================================ */
setInterval(tickClock, 1000);
if (localStorage.getItem(AUTH_KEY) === '1') enterApp();
</script>
</body>
</html>
