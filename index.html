<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <meta name="theme-color" content="#0a0a0a">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black">
  <meta name="format-detection" content="telephone=no">
  <title>Expiry Tracker</title>
  <link rel="manifest" href="manifest.json">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <script src="https://unpkg.com/html5-qrcode@2.3.8/html5-qrcode.min.js"></script>
  <style>
    :root {
      --primary: #00bcd4;
      --primary-dark: #00838f;
      --primary-light: #4dd0e1;
      --bg-dark: #0a0a0a;
      --bg-card: #111111;
      --bg-card-hover: #1a1a1a;
      --bg-input: #1c1c1c;
      --text-primary: #ffffff;
      --text-secondary: #a0a0a0;
      --text-muted: #666666;
      --border-color: #2a2a2a;
      --success: #00e676;
      --warning: #ffab00;
      --danger: #ff5252;
      --expired: #ff1744;
      --expiring: #ff9100;
      --ok: #00e676;
      --api: #a78bfa;
      --radius-sm: 8px;
      --radius-md: 12px;
      --radius-lg: 16px;
      --radius-xl: 24px;
      --shadow: 0 4px 24px rgba(0, 188, 212, 0.15);
      --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
    html, body { height: 100%; overflow: hidden; }
    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      background: var(--bg-dark);
      color: var(--text-primary);
      line-height: 1.5;
      -webkit-font-smoothing: antialiased;
    }

    /* Splash Screen */
    #splashScreen {
      position: fixed; inset: 0; background: var(--bg-dark);
      display: flex; flex-direction: column; align-items: center; justify-content: center;
      z-index: 9999; transition: opacity 0.5s ease, visibility 0.5s ease;
    }
    #splashScreen.hide { opacity: 0; visibility: hidden; }
    .splash-logo { width: 120px; height: 120px; margin-bottom: 24px; }
    .splash-pill {
      width: 100%; height: 100%;
      background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
      border-radius: 60px; animation: pillPulse 2s ease-in-out infinite;
      display: flex; align-items: center; justify-content: center;
      font-size: 48px; box-shadow: var(--shadow);
    }
    @keyframes pillPulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.05); }
    }
    .splash-title {
      font-size: 28px; font-weight: 700;
      background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      margin-bottom: 8px; animation: fadeInUp 0.8s ease 0.3s both;
    }
    .splash-tagline { font-size: 14px; color: var(--text-secondary); margin-bottom: 4px; animation: fadeInUp 0.8s ease 0.5s both; }
    .splash-brand { font-size: 12px; color: var(--text-muted); animation: fadeInUp 0.8s ease 0.7s both; }
    .splash-brand span { color: var(--primary); font-weight: 600; }
    .splash-loader { width: 200px; height: 3px; background: var(--bg-card); border-radius: 3px; margin-top: 32px; overflow: hidden; }
    .splash-loader-bar { height: 100%; background: linear-gradient(90deg, var(--primary), var(--primary-light)); animation: loadProgress 2s ease-out forwards; }
    @keyframes loadProgress { 0% { width: 0%; } 100% { width: 100%; } }
    @keyframes fadeInUp { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

    /* App Container */
    #app { height: 100%; display: flex; flex-direction: column; opacity: 0; transition: opacity 0.5s ease; }
    #app.show { opacity: 1; }

    /* Header */
    .header {
      background: linear-gradient(135deg, rgba(0, 188, 212, 0.1) 0%, rgba(38, 198, 218, 0.05) 100%);
      border-bottom: 1px solid var(--border-color);
      padding: 12px 16px; display: flex; align-items: center; justify-content: space-between;
      backdrop-filter: blur(20px);
    }
    .header-left { display: flex; align-items: center; gap: 12px; }
    .header-logo {
      width: 36px; height: 36px;
      background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
      border-radius: 10px; display: flex; align-items: center; justify-content: center;
      font-size: 20px; box-shadow: var(--shadow);
    }
    .header-title {
      font-size: 18px; font-weight: 700;
      background: linear-gradient(135deg, var(--primary) 0%, #fff 100%);
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    }
    .header-btn {
      width: 40px; height: 40px; border: none; background: var(--bg-card);
      border-radius: var(--radius-md); color: var(--text-primary);
      font-size: 18px; cursor: pointer; transition: var(--transition);
    }
    .header-btn:active { transform: scale(0.95); background: var(--primary); }

    /* Main Content */
    .main-content { flex: 1; overflow-y: auto; padding: 16px; -webkit-overflow-scrolling: touch; }

    /* Input Section */
    .input-section {
      background: var(--bg-card); border-radius: var(--radius-lg);
      padding: 16px; margin-bottom: 16px; border: 1px solid var(--border-color);
    }
    .input-section-title {
      font-size: 12px; font-weight: 600; color: var(--primary);
      text-transform: uppercase; letter-spacing: 1px; margin-bottom: 12px;
      display: flex; align-items: center; gap: 8px; cursor: pointer;
    }
    .toggle-icon { margin-left: auto; transition: var(--transition); }
    .toggle-icon.collapsed { transform: rotate(-90deg); }
    
    .barcode-input {
      width: 100%; background: var(--bg-input); border: 2px solid var(--border-color);
      border-radius: var(--radius-md); padding: 16px; font-size: 16px;
      color: var(--text-primary); font-family: 'SF Mono', 'Fira Code', monospace;
      transition: var(--transition); outline: none;
    }
    .barcode-input:focus { border-color: var(--primary); box-shadow: 0 0 0 4px rgba(0, 188, 212, 0.2); }
    .barcode-input::placeholder { color: var(--text-muted); }
    .input-hint { font-size: 11px; color: var(--text-muted); margin-top: 8px; display: flex; align-items: center; gap: 4px; }

    /* Bulk Paste Area */
    .bulk-area-wrapper { display: block; transition: var(--transition); }
    .bulk-area-wrapper.hidden { display: none; }
    .bulk-input {
      width: 100%; background: var(--bg-input); border: 2px solid var(--border-color);
      border-radius: var(--radius-md); padding: 12px; font-size: 13px;
      color: var(--text-primary); font-family: 'SF Mono', 'Fira Code', monospace;
      resize: vertical; min-height: 120px; max-height: 300px;
      transition: var(--transition); outline: none;
    }
    .bulk-input:focus { border-color: var(--primary); box-shadow: 0 0 0 4px rgba(0, 188, 212, 0.2); }
    .bulk-input::placeholder { color: var(--text-muted); font-size: 12px; }
    .bulk-info {
      display: flex; justify-content: space-between; align-items: center;
      margin-top: 8px; font-size: 11px;
    }
    #bulkLineCount { color: var(--primary); font-weight: 600; }
    .bulk-hint { color: var(--text-muted); }
    .bulk-process-btn {
      width: 100%; margin-top: 12px; padding: 14px;
      background: linear-gradient(135deg, var(--success) 0%, #00c853 100%);
      border: none; border-radius: var(--radius-md); color: #000;
      font-size: 15px; font-weight: 600; cursor: pointer;
      display: flex; align-items: center; justify-content: center; gap: 8px;
      transition: var(--transition);
    }
    .bulk-process-btn:active { transform: scale(0.98); }
    .bulk-process-btn:disabled { opacity: 0.5; cursor: not-allowed; }

    /* Progress Bar */
    .progress-container { margin-top: 12px; display: none; }
    .progress-container.show { display: block; }
    .progress-bar { height: 8px; background: var(--bg-input); border-radius: 4px; overflow: hidden; }
    .progress-fill { height: 100%; background: var(--primary); transition: width 0.3s ease; }
    .progress-text { font-size: 12px; color: var(--text-secondary); margin-top: 6px; text-align: center; }

    /* Scanner Section */
    .scanner-section {
      background: var(--bg-card); border-radius: var(--radius-lg);
      padding: 16px; margin-bottom: 16px; border: 1px solid var(--border-color);
    }
    .scanner-toggle {
      width: 100%; padding: 14px;
      background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
      border: none; border-radius: var(--radius-md); color: #000;
      font-size: 15px; font-weight: 600; cursor: pointer;
      display: flex; align-items: center; justify-content: center; gap: 10px;
    }
    .scanner-toggle:active { transform: scale(0.98); }
    .scanner-toggle.active { background: var(--danger); color: #fff; }
    #scannerContainer { display: none; margin-top: 16px; border-radius: var(--radius-md); overflow: hidden; }
    #scannerContainer.show { display: block; }
    #reader { width: 100%; border-radius: var(--radius-md); }

    /* Stats Grid */
    .stats-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; margin-bottom: 16px; }
    .stat-card {
      background: var(--bg-card); border-radius: var(--radius-lg);
      padding: 16px; text-align: center; border: 1px solid var(--border-color);
    }
    .stat-card.expired { border-color: var(--expired); background: linear-gradient(135deg, rgba(255, 23, 68, 0.1) 0%, transparent 100%); }
    .stat-card.expiring { border-color: var(--expiring); background: linear-gradient(135deg, rgba(255, 145, 0, 0.1) 0%, transparent 100%); }
    .stat-card.ok { border-color: var(--ok); background: linear-gradient(135deg, rgba(0, 230, 118, 0.1) 0%, transparent 100%); }
    .stat-value { font-size: 28px; font-weight: 700; line-height: 1; margin-bottom: 4px; }
    .stat-card.expired .stat-value { color: var(--expired); }
    .stat-card.expiring .stat-value { color: var(--expiring); }
    .stat-card.ok .stat-value { color: var(--ok); }
    .stat-label { font-size: 11px; color: var(--text-secondary); text-transform: uppercase; }

    /* Items List */
    .section-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 12px; }
    .section-title { font-size: 16px; font-weight: 600; display: flex; align-items: center; gap: 8px; }
    .section-action { font-size: 13px; color: var(--primary); background: none; border: none; cursor: pointer; }
    .items-list { display: flex; flex-direction: column; gap: 10px; }
    
    .item-card {
      background: var(--bg-card); border-radius: var(--radius-lg);
      padding: 14px; border: 1px solid var(--border-color);
      position: relative; overflow: hidden;
    }
    .item-card::before { content: ''; position: absolute; left: 0; top: 0; bottom: 0; width: 4px; }
    .item-card.expired::before { background: var(--expired); }
    .item-card.expiring::before { background: var(--expiring); }
    .item-card.ok::before { background: var(--ok); }
    .item-card.api::before { background: var(--api); }
    .item-card.unknown::before { background: var(--text-muted); }

    .item-header { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 8px; }
    .item-name { font-size: 14px; font-weight: 600; flex: 1; margin-right: 8px; line-height: 1.3; }
    .item-expiry-badge { font-size: 12px; font-weight: 600; padding: 4px 10px; border-radius: 20px; white-space: nowrap; }
    .item-card.expired .item-expiry-badge { background: rgba(255, 23, 68, 0.2); color: var(--expired); }
    .item-card.expiring .item-expiry-badge { background: rgba(255, 145, 0, 0.2); color: var(--expiring); }
    .item-card.ok .item-expiry-badge { background: rgba(0, 230, 118, 0.2); color: var(--ok); }
    .item-card.api .item-expiry-badge { background: rgba(167, 139, 250, 0.2); color: var(--api); }

    .item-details { display: grid; grid-template-columns: repeat(2, 1fr); gap: 6px; font-size: 12px; }
    .item-detail { display: flex; align-items: center; gap: 4px; }
    .item-detail-label { color: var(--text-muted); }
    .item-detail-value { color: var(--text-secondary); font-family: 'SF Mono', monospace; }

    .item-actions { display: flex; gap: 8px; margin-top: 10px; padding-top: 10px; border-top: 1px solid var(--border-color); }
    .item-action-btn {
      flex: 1; padding: 8px; border: none; border-radius: var(--radius-sm);
      font-size: 12px; font-weight: 500; cursor: pointer;
      display: flex; align-items: center; justify-content: center; gap: 4px;
    }
    .item-action-btn.edit { background: rgba(0, 188, 212, 0.2); color: var(--primary); }
    .item-action-btn.delete { background: rgba(255, 82, 82, 0.2); color: var(--danger); }
    .item-action-btn:active { transform: scale(0.95); }

    /* Empty State */
    .empty-state { text-align: center; padding: 40px 20px; }
    .empty-icon { font-size: 48px; margin-bottom: 12px; opacity: 0.5; }
    .empty-title { font-size: 16px; font-weight: 600; color: var(--text-secondary); margin-bottom: 4px; }
    .empty-text { font-size: 13px; color: var(--text-muted); }

    /* Bottom Nav */
    .bottom-nav {
      background: var(--bg-card); border-top: 1px solid var(--border-color);
      padding: 8px 16px; padding-bottom: max(8px, env(safe-area-inset-bottom));
      display: flex; justify-content: space-around;
    }
    .nav-item {
      display: flex; flex-direction: column; align-items: center;
      padding: 8px 16px; border-radius: var(--radius-md);
      background: none; border: none; color: var(--text-muted);
      font-size: 10px; cursor: pointer; gap: 4px;
    }
    .nav-item-icon { font-size: 22px; }
    .nav-item.active { color: var(--primary); background: rgba(0, 188, 212, 0.1); }

    /* Pages */
    .page { display: none; }
    .page.active { display: block; }

    /* Modal */
    .modal-overlay {
      position: fixed; inset: 0; background: rgba(0, 0, 0, 0.8);
      backdrop-filter: blur(10px); display: flex; align-items: center;
      justify-content: center; padding: 20px; z-index: 1000;
      opacity: 0; visibility: hidden; transition: var(--transition);
    }
    .modal-overlay.show { opacity: 1; visibility: visible; }
    .modal {
      background: var(--bg-card); border-radius: var(--radius-xl);
      width: 100%; max-width: 400px; max-height: 80vh; overflow-y: auto;
      transform: scale(0.9); transition: var(--transition);
    }
    .modal-overlay.show .modal { transform: scale(1); }
    .modal-header { padding: 20px; border-bottom: 1px solid var(--border-color); display: flex; align-items: center; justify-content: space-between; }
    .modal-title { font-size: 18px; font-weight: 600; }
    .modal-close { width: 32px; height: 32px; border: none; background: var(--bg-input); border-radius: 50%; color: var(--text-secondary); font-size: 18px; cursor: pointer; }
    .modal-body { padding: 20px; }
    .form-group { margin-bottom: 16px; }
    .form-label { display: block; font-size: 12px; font-weight: 500; color: var(--text-secondary); margin-bottom: 6px; text-transform: uppercase; }
    .form-input { width: 100%; background: var(--bg-input); border: 1px solid var(--border-color); border-radius: var(--radius-md); padding: 12px; font-size: 15px; color: var(--text-primary); outline: none; }
    .form-input:focus { border-color: var(--primary); }
    .modal-footer { padding: 16px 20px; border-top: 1px solid var(--border-color); display: flex; gap: 12px; }
    .btn { flex: 1; padding: 14px; border: none; border-radius: var(--radius-md); font-size: 15px; font-weight: 600; cursor: pointer; }
    .btn-primary { background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%); color: #000; }
    .btn-secondary { background: var(--bg-input); color: var(--text-secondary); }

    /* Side Menu */
    .menu-overlay { position: fixed; inset: 0; background: rgba(0, 0, 0, 0.6); z-index: 999; opacity: 0; visibility: hidden; transition: var(--transition); }
    .menu-overlay.show { opacity: 1; visibility: visible; }
    .side-menu { position: fixed; top: 0; right: 0; bottom: 0; width: 280px; background: var(--bg-card); z-index: 1000; transform: translateX(100%); transition: var(--transition); display: flex; flex-direction: column; }
    .side-menu.show { transform: translateX(0); }
    .menu-header { padding: 20px; border-bottom: 1px solid var(--border-color); display: flex; align-items: center; justify-content: space-between; }
    .menu-items { flex: 1; padding: 12px; overflow-y: auto; }
    .menu-item { display: flex; align-items: center; gap: 12px; padding: 14px; border-radius: var(--radius-md); color: var(--text-primary); font-size: 14px; cursor: pointer; background: none; border: none; width: 100%; text-align: left; }
    .menu-item:active { background: var(--bg-input); }
    .menu-divider { height: 1px; background: var(--border-color); margin: 8px 0; }
    .menu-footer { padding: 16px; border-top: 1px solid var(--border-color); text-align: center; }
    .menu-version { font-size: 11px; color: var(--text-muted); }

    /* Toast */
    .toast-container { position: fixed; top: 20px; left: 50%; transform: translateX(-50%); z-index: 9999; display: flex; flex-direction: column; gap: 8px; pointer-events: none; }
    .toast { background: var(--bg-card); border: 1px solid var(--border-color); border-radius: var(--radius-md); padding: 12px 20px; font-size: 14px; box-shadow: var(--shadow); animation: toastIn 0.3s ease; }
    .toast.success { border-color: var(--success); }
    .toast.error { border-color: var(--danger); }
    .toast.warning { border-color: var(--warning); }
    @keyframes toastIn { from { opacity: 0; transform: translateY(-20px); } to { opacity: 1; transform: translateY(0); } }

    /* Loading */
    .loading-overlay { position: fixed; inset: 0; background: rgba(0, 0, 0, 0.8); display: flex; align-items: center; justify-content: center; z-index: 9998; opacity: 0; visibility: hidden; transition: var(--transition); flex-direction: column; gap: 16px; }
    .loading-overlay.show { opacity: 1; visibility: visible; }
    .loading-spinner { width: 48px; height: 48px; border: 4px solid var(--border-color); border-top-color: var(--primary); border-radius: 50%; animation: spin 1s linear infinite; }
    .loading-text { color: var(--text-secondary); font-size: 14px; }
    @keyframes spin { to { transform: rotate(360deg); } }

    /* Settings */
    .settings-section { background: var(--bg-card); border-radius: var(--radius-lg); padding: 4px; margin-bottom: 16px; border: 1px solid var(--border-color); }
    .settings-item { display: flex; align-items: center; justify-content: space-between; padding: 16px; border-radius: var(--radius-md); cursor: pointer; }
    .settings-item:active { background: var(--bg-input); }
    .settings-item-left { display: flex; align-items: center; gap: 12px; }
    .settings-item-icon { width: 40px; height: 40px; background: var(--bg-input); border-radius: var(--radius-md); display: flex; align-items: center; justify-content: center; font-size: 20px; }
    .settings-item-text { display: flex; flex-direction: column; }
    .settings-item-title { font-size: 14px; font-weight: 500; }
    .settings-item-desc { font-size: 12px; color: var(--text-muted); }
    .settings-item-arrow { color: var(--text-muted); font-size: 18px; }

    /* Master Stats */
    .master-stats { background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%); border-radius: var(--radius-lg); padding: 20px; margin-bottom: 16px; text-align: center; }
    .master-count { font-size: 48px; font-weight: 700; color: #fff; line-height: 1; }
    .master-label { font-size: 14px; color: rgba(255,255,255,0.8); margin-top: 4px; }

    /* Search & Filter */
    .search-bar { background: var(--bg-card); border: 1px solid var(--border-color); border-radius: var(--radius-lg); padding: 12px 16px; margin-bottom: 16px; display: flex; align-items: center; gap: 10px; }
    .search-bar input { flex: 1; background: none; border: none; font-size: 15px; color: var(--text-primary); outline: none; }
    .search-bar input::placeholder { color: var(--text-muted); }
    .filter-tabs { display: flex; gap: 8px; margin-bottom: 16px; overflow-x: auto; padding-bottom: 4px; }
    .filter-tab { padding: 8px 16px; background: var(--bg-card); border: 1px solid var(--border-color); border-radius: 20px; font-size: 13px; color: var(--text-secondary); cursor: pointer; white-space: nowrap; }
    .filter-tab.active { background: var(--primary); border-color: var(--primary); color: #000; }
  </style>
</head>
<body>
  <!-- SPLASH SCREEN -->
  <div id="splashScreen">
    <div class="splash-logo">
      <div class="splash-pill">💊</div>
    </div>
    <div class="splash-title">EXPIRY TRACKER</div>
    <div class="splash-tagline">With you. For Life.</div>
    <div class="splash-brand">AI startup by <span>VYSAKH</span></div>
    <div class="splash-loader">
      <div class="splash-loader-bar"></div>
    </div>
  </div>

  <!-- MAIN APP -->
  <div id="app">
    <!-- HEADER -->
    <header class="header">
      <div class="header-left">
        <div class="header-logo">💊</div>
        <span class="header-title">Expiry Tracker</span>
      </div>
      <div class="header-actions">
        <button class="header-btn" id="btnMenu">☰</button>
      </div>
    </header>

    <!-- MAIN CONTENT -->
    <main class="main-content">
      <!-- HOME PAGE -->
      <div id="page-home" class="page active">
        <!-- Manual Input -->
        <div class="input-section">
          <div class="input-section-title">
            <span>📝</span> Single Barcode Entry
          </div>
          <input 
            type="text" 
            id="barcodeInput" 
            class="barcode-input" 
            placeholder="Paste or type GS1 barcode here..."
            autocomplete="off" autocorrect="off" autocapitalize="off" spellcheck="false"
          >
          <div class="input-hint">
            <span>💡</span> Auto-processes on Enter or paste
          </div>
        </div>

        <!-- Bulk Paste Section -->
        <div class="input-section">
          <div class="input-section-title" onclick="toggleBulkArea()">
            <span>📋</span> Bulk Paste (Multiple Barcodes)
            <span class="toggle-icon" id="bulkToggleIcon">▼</span>
          </div>
          <div id="bulkAreaWrapper" class="bulk-area-wrapper">
            <textarea 
              id="bulkInput" 
              class="bulk-input" 
              placeholder="Paste multiple GS1 barcodes here (one per line)...

Example:
(01)05000167091670(17)261231(10)ABC123(21)123456
(01)06291107439358(17)270930(10)XYZ789(21)987654
(01)00840149658430(17)251206(10)BAT001(21)555666

📌 Paste from Excel - each row = one barcode
📌 Supports 500+ barcodes at once"
              rows="6"
            ></textarea>
            <div class="bulk-info">
              <span id="bulkLineCount">0 lines detected</span>
              <span class="bulk-hint">💡 Paste from Excel</span>
            </div>
            <div class="progress-container" id="progressContainer">
              <div class="progress-bar">
                <div class="progress-fill" id="progressFill"></div>
              </div>
              <div class="progress-text" id="progressText">Processing...</div>
            </div>
            <button class="bulk-process-btn" id="btnProcessBulk">
              <span>⚡</span> Process All Barcodes
            </button>
          </div>
        </div>

        <!-- Scanner -->
        <div class="scanner-section">
          <button class="scanner-toggle" id="btnScanner">
            <span>📷</span> Open Camera Scanner
          </button>
          <div id="scannerContainer">
            <div id="reader"></div>
          </div>
        </div>

        <!-- Stats -->
        <div class="stats-grid">
          <div class="stat-card expired" onclick="filterItems('expired')">
            <div class="stat-value" id="statExpired">0</div>
            <div class="stat-label">Expired</div>
          </div>
          <div class="stat-card expiring" onclick="filterItems('expiring')">
            <div class="stat-value" id="statExpiring">0</div>
            <div class="stat-label">Expiring</div>
          </div>
          <div class="stat-card ok" onclick="filterItems('ok')">
            <div class="stat-value" id="statOk">0</div>
            <div class="stat-label">OK</div>
          </div>
        </div>

        <!-- Recent Items -->
        <div class="section-header">
          <div class="section-title"><span>📋</span> Recent Scans</div>
          <button class="section-action" onclick="showPage('history')">View All →</button>
        </div>
        <div class="items-list" id="recentItems">
          <div class="empty-state">
            <div class="empty-icon">📦</div>
            <div class="empty-title">No items yet</div>
            <div class="empty-text">Scan or paste a barcode to start</div>
          </div>
        </div>
      </div>

      <!-- HISTORY PAGE -->
      <div id="page-history" class="page">
        <div class="search-bar">
          <span>🔍</span>
          <input type="text" id="searchInput" placeholder="Search products...">
        </div>
        <div class="filter-tabs">
          <button class="filter-tab active" data-filter="all">All</button>
          <button class="filter-tab" data-filter="expired">Expired</button>
          <button class="filter-tab" data-filter="expiring">Expiring</button>
          <button class="filter-tab" data-filter="ok">OK</button>
        </div>
        <div class="items-list" id="historyList"></div>
      </div>

      <!-- SETTINGS PAGE -->
      <div id="page-settings" class="page">
        <div class="master-stats">
          <div class="master-count" id="masterCount">0</div>
          <div class="master-label">Products in Database</div>
        </div>

        <div class="settings-section">
          <div class="settings-item" onclick="document.getElementById('fileMaster').click()">
            <div class="settings-item-left">
              <div class="settings-item-icon">📤</div>
              <div class="settings-item-text">
                <div class="settings-item-title">Upload Master Data</div>
                <div class="settings-item-desc">Replace product database</div>
              </div>
            </div>
            <div class="settings-item-arrow">›</div>
          </div>
          <div class="settings-item" onclick="document.getElementById('fileAppend').click()">
            <div class="settings-item-left">
              <div class="settings-item-icon">➕</div>
              <div class="settings-item-text">
                <div class="settings-item-title">Append Master Data</div>
                <div class="settings-item-desc">Add to existing database</div>
              </div>
            </div>
            <div class="settings-item-arrow">›</div>
          </div>
        </div>

        <div class="settings-section">
          <div class="settings-item" onclick="exportData()">
            <div class="settings-item-left">
              <div class="settings-item-icon">📊</div>
              <div class="settings-item-text">
                <div class="settings-item-title">Export Data</div>
                <div class="settings-item-desc">Download CSV report</div>
              </div>
            </div>
            <div class="settings-item-arrow">›</div>
          </div>
          <div class="settings-item" onclick="downloadBackup()">
            <div class="settings-item-left">
              <div class="settings-item-icon">💾</div>
              <div class="settings-item-text">
                <div class="settings-item-title">Backup</div>
                <div class="settings-item-desc">Save all data</div>
              </div>
            </div>
            <div class="settings-item-arrow">›</div>
          </div>
          <div class="settings-item" onclick="document.getElementById('fileRestore').click()">
            <div class="settings-item-left">
              <div class="settings-item-icon">📥</div>
              <div class="settings-item-text">
                <div class="settings-item-title">Restore Backup</div>
                <div class="settings-item-desc">Load saved data</div>
              </div>
            </div>
            <div class="settings-item-arrow">›</div>
          </div>
        </div>

        <div class="settings-section">
          <div class="settings-item" onclick="clearHistory()">
            <div class="settings-item-left">
              <div class="settings-item-icon">🗑️</div>
              <div class="settings-item-text">
                <div class="settings-item-title">Clear History</div>
                <div class="settings-item-desc">Remove all scanned items</div>
              </div>
            </div>
            <div class="settings-item-arrow">›</div>
          </div>
          <div class="settings-item" onclick="resetMaster()">
            <div class="settings-item-left">
              <div class="settings-item-icon">🔄</div>
              <div class="settings-item-text">
                <div class="settings-item-title">Reset Master Data</div>
                <div class="settings-item-desc">Clear product database</div>
              </div>
            </div>
            <div class="settings-item-arrow">›</div>
          </div>
        </div>
      </div>
    </main>

    <!-- BOTTOM NAV -->
    <nav class="bottom-nav">
      <button class="nav-item active" data-page="home">
        <span class="nav-item-icon">🏠</span>
        <span>Home</span>
      </button>
      <button class="nav-item" data-page="history">
        <span class="nav-item-icon">📋</span>
        <span>History</span>
      </button>
      <button class="nav-item" data-page="settings">
        <span class="nav-item-icon">⚙️</span>
        <span>Settings</span>
      </button>
    </nav>
  </div>

  <!-- SIDE MENU -->
  <div class="menu-overlay" id="menuOverlay"></div>
  <div class="side-menu" id="sideMenu">
    <div class="menu-header">
      <span class="menu-title">Menu</span>
      <button class="modal-close" onclick="closeMenu()">×</button>
    </div>
    <div class="menu-items">
      <button class="menu-item" onclick="exportData(); closeMenu();">
        <span>📊</span> Export CSV
      </button>
      <button class="menu-item" onclick="downloadBackup(); closeMenu();">
        <span>💾</span> Download Backup
      </button>
      <div class="menu-divider"></div>
      <button class="menu-item" onclick="showPage('settings'); closeMenu();">
        <span>⚙️</span> Settings
      </button>
    </div>
    <div class="menu-footer">
      <div class="menu-version">Expiry Tracker v5.1.0</div>
      <div class="menu-version">AI startup by VYSAKH</div>
    </div>
  </div>

  <!-- EDIT MODAL -->
  <div class="modal-overlay" id="editModal">
    <div class="modal">
      <div class="modal-header">
        <span class="modal-title">Edit Item</span>
        <button class="modal-close" onclick="closeEditModal()">×</button>
      </div>
      <div class="modal-body">
        <input type="hidden" id="editId">
        <div class="form-group">
          <label class="form-label">Product Name</label>
          <input type="text" id="editName" class="form-input">
        </div>
        <div class="form-group">
          <label class="form-label">Expiry Date</label>
          <input type="date" id="editExpiry" class="form-input">
        </div>
        <div class="form-group">
          <label class="form-label">Batch Number</label>
          <input type="text" id="editBatch" class="form-input">
        </div>
        <div class="form-group">
          <label class="form-label">Quantity</label>
          <input type="number" id="editQty" class="form-input" min="1">
        </div>
        <div class="form-group">
          <label class="form-label">RMS Code</label>
          <input type="text" id="editRms" class="form-input">
        </div>
        <div class="form-group">
          <label class="form-label">Supplier</label>
          <input type="text" id="editSupplier" class="form-input">
        </div>
        <div class="form-group">
          <label class="form-label">Returnable</label>
          <select id="editReturnable" class="form-input">
            <option value="">Not specified</option>
            <option value="yes">Yes</option>
            <option value="no">No</option>
          </select>
        </div>
      </div>
      <div class="modal-footer">
        <button class="btn btn-secondary" onclick="closeEditModal()">Cancel</button>
        <button class="btn btn-primary" onclick="saveEdit()">Save</button>
      </div>
    </div>
  </div>

  <!-- TOAST CONTAINER -->
  <div class="toast-container" id="toastContainer"></div>

  <!-- LOADING OVERLAY -->
  <div class="loading-overlay" id="loadingOverlay">
    <div class="loading-spinner"></div>
    <div class="loading-text" id="loadingText">Processing...</div>
  </div>

  <!-- HIDDEN FILE INPUTS -->
  <input type="file" id="fileMaster" accept=".csv,.txt" style="display:none">
  <input type="file" id="fileAppend" accept=".csv,.txt" style="display:none">
  <input type="file" id="fileRestore" accept=".json" style="display:none">

  <script src="app.js"></script>
  <script src="master-data.js"></script>
</body>
</html>
