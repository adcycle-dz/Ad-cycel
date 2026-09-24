<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ad_cycel | نظام جمع البلاستيك</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@200;400;600;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <style>
        :root {
            --bg: #0a1a0f;
            --bg2: #0f2518;
            --card: #132e1b;
            --card2: #1a3d24;
            --border: #1e4a28;
            --fg: #e8f5e9;
            --fg2: #a5d6a7;
            --muted: #5a8a64;
            --accent: #00e676;
            --accent2: #00c853;
            --gold: #ffd740;
            --gold-bg: rgba(255,215,64,0.1);
            --gold-border: rgba(255,215,64,0.3);
            --silver: #b0bec5;
            --silver-bg: rgba(176,190,197,0.1);
            --silver-border: rgba(176,190,197,0.3);
            --bronze: #cd7f32;
            --bronze-bg: rgba(205,127,50,0.1);
            --bronze-border: rgba(205,127,50,0.3);
            --danger: #ff5252;
            --radius: 16px;
            --radius-sm: 10px;
        }
        *{margin:0;padding:0;box-sizing:border-box}
        body{font-family:'Cairo',sans-serif;background:var(--bg);color:var(--fg);min-height:100vh;overflow-x:hidden}
        .bg-effects{position:fixed;inset:0;z-index:0;pointer-events:none;overflow:hidden}
        .bg-effects .blob{position:absolute;border-radius:50%;filter:blur(120px);opacity:0.15;animation:blobFloat 20s ease-in-out infinite}
        .blob-1{width:500px;height:500px;background:var(--accent);top:-150px;right:-100px}
        .blob-2{width:400px;height:400px;background:#004d40;bottom:-100px;left:-100px;animation-delay:-7s}
        .blob-3{width:300px;height:300px;background:var(--gold);top:50%;left:50%;animation-delay:-14s;opacity:0.08}
        @keyframes blobFloat{0%,100%{transform:translate(0,0) scale(1)}33%{transform:translate(30px,-40px) scale(1.1)}66%{transform:translate(-20px,30px) scale(0.9)}}
        
        .app-container{position:relative;z-index:1;min-height:100vh}

        .login-screen{display:flex;align-items:center;justify-content:center;min-height:100vh;padding:20px}
        .login-box{background:var(--card);border:1px solid var(--border);border-radius:24px;padding:50px 40px;width:100%;max-width:460px;text-align:center;position:relative;overflow:hidden;animation:slideUp 0.6s ease}
        .login-box::before{content:'';position:absolute;top:0;left:0;right:0;height:4px;background:linear-gradient(90deg,var(--accent),var(--gold),var(--accent))}
        @keyframes slideUp{from{opacity:0;transform:translateY(40px)}to{opacity:1;transform:translateY(0)}}
        
        .login-logo{width:90px;height:90px;background:linear-gradient(135deg,var(--accent),#004d40);border-radius:50%;display:flex;align-items:center;justify-content:center;margin:0 auto 20px;font-size:36px;box-shadow:0 8px 32px rgba(0,230,118,0.3);padding:5px; overflow: hidden; border: 2px solid rgba(0,230,118,0.2);}
        .login-logo img { width: 100%; height: 100%; object-fit: cover; border-radius: 50%; }
        
        .login-title{font-size:32px;font-weight:900;margin-bottom:6px;background:linear-gradient(135deg,var(--fg),var(--accent));-webkit-background-clip:text;-webkit-text-fill-color:transparent;letter-spacing:1px}
        .login-subtitle{color:var(--muted);font-size:14px;margin-bottom:36px}
        
        .form-group{margin-bottom:18px;text-align:right}
        .form-group label{display:block;font-size:13px;color:var(--fg2);margin-bottom:6px;font-weight:600}
        
        .input-icon-wrapper { position: relative; }
        .input-icon-wrapper i { position: absolute; right: 16px; top: 50%; transform: translateY(-50%); color: var(--muted); font-size: 14px; pointer-events: none; transition: color 0.3s; }
        .icon-input { padding-right: 42px !important; }
        .input-icon-wrapper .icon-input:focus ~ i, .input-icon-wrapper .icon-input:focus + i { color: var(--accent); }

        .form-input{width:100%;padding:14px 16px;background:var(--bg);border:1px solid var(--border);border-radius:var(--radius-sm);color:var(--fg);font-family:'Cairo';font-size:15px;transition:all 0.3s;outline:none}
        .form-input:focus{border-color:var(--accent);box-shadow:0 0 0 3px rgba(0,230,118,0.1)}
        .form-input::placeholder{color:var(--muted)}
        
        .btn{padding:14px 28px;border:none;border-radius:var(--radius-sm);font-family:'Cairo';font-size:15px;font-weight:700;cursor:pointer;transition:all 0.3s;display:inline-flex;align-items:center;justify-content:center;gap:8px}
        .btn-primary{width:100%;background:linear-gradient(135deg,var(--accent),var(--accent2));color:#0a1a0f;font-size:16px;padding:16px;margin-top:8px}
        .btn-primary:hover{transform:translateY(-2px);box-shadow:0 8px 24px rgba(0,230,118,0.3)}
        .btn-sm{padding:8px 16px;font-size:13px;border-radius:8px}
        .btn-accent{background:var(--accent);color:#0a1a0f}
        .btn-accent:hover{box-shadow:0 4px 16px rgba(0,230,118,0.3)}
        .btn-outline{background:transparent;border:1px solid var(--border);color:var(--fg2)}
        .btn-outline:hover{border-color:var(--accent);color:var(--accent)}
        .btn-danger{background:rgba(255,82,82,0.15);color:var(--danger);border:1px solid rgba(255,82,82,0.3)}
        .btn-warning{background:rgba(255,215,64,0.15);color:var(--gold);border:1px solid var(--gold-border)}

        .topbar{background:rgba(10,26,15,0.85);backdrop-filter:blur(20px);border-bottom:1px solid var(--border);padding:0 28px;height:68px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:100}
        .topbar-brand{display:flex;align-items:center;gap:12px}
        .topbar-brand-icon{width:42px;height:42px;background:linear-gradient(135deg,var(--accent),#004d40);border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:18px; overflow: hidden; padding: 2px; border: 1px solid rgba(0,230,118,0.3); box-shadow:0 0 10px rgba(0,230,118,0.1);}
        .topbar-brand-icon img { width: 100%; height: 100%; object-fit: cover; border-radius: 10px; }

        .topbar-brand-text{font-size:20px;font-weight:900;letter-spacing:1px}
        .topbar-user{display:flex;align-items:center;gap:14px}
        .topbar-user-info{text-align:right}
        .topbar-user-name{font-size:14px;font-weight:700}
        .topbar-user-role{font-size:11px;color:var(--muted)}
        .topbar-avatar{width:40px;height:40px;border-radius:12px;background:var(--card2);display:flex;align-items:center;justify-content:center;font-size:16px;border:2px solid var(--border)}
        .btn-logout{background:rgba(255,82,82,0.1);border:1px solid rgba(255,82,82,0.2);color:var(--danger);padding:8px 14px;border-radius:8px;cursor:pointer;font-family:'Cairo';font-size:13px;font-weight:600;transition:all 0.3s}
        .btn-logout:hover{background:rgba(255,82,82,0.2)}

        .main-layout{display:flex;min-height:calc(100vh - 68px)}
        .sidebar{width:260px;background:var(--card);border-left:1px solid var(--border);padding:24px 14px;flex-shrink:0;display:flex;flex-direction:column;gap:4px;overflow-y:auto;height:calc(100vh - 68px); position:sticky;top:68px;}
        .sidebar-label{font-size:11px;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;padding:12px 14px 6px;cursor:default}
        .sidebar-item{width:100%;padding:12px 14px;border:none;border-radius:10px;background:transparent;color:var(--fg2);font-family:'Cairo';font-size:14px;font-weight:600;cursor:pointer;transition:all 0.2s;display:flex;align-items:center;gap:10px;text-align:right}
        .sidebar-item:hover{background:rgba(0,230,118,0.08);color:var(--accent)}
        .sidebar-item.active{background:rgba(0,230,118,0.12);color:var(--accent);box-shadow:inset 3px 0 0 var(--accent)}
        .sidebar-item i{width:20px;text-align:center;font-size:15px}
        .sidebar-badge{background:var(--accent);color:#0a1a0f;font-size:10px;font-weight:800;padding:2px 7px;border-radius:20px;margin-right:auto}
        
        .content{flex:1;padding:28px;overflow-y:auto;height:calc(100vh - 68px); position: relative;}
        .page{display:none;animation:fadeIn 0.4s ease}
        .page.active{display:block}
        @keyframes fadeIn{from{opacity:0;transform:translateY(12px)}to{opacity:1;transform:translateY(0)}}
        .page-header{margin-bottom:28px}
        .page-title{font-size:26px;font-weight:900;margin-bottom:4px}
        .page-desc{color:var(--muted);font-size:14px}

        .stats-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:16px;margin-bottom:28px}
        .stat-card{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:22px;position:relative;overflow:hidden;transition:all 0.3s}
        .stat-card:hover{transform:translateY(-3px);box-shadow:0 8px 24px rgba(0,0,0,0.3)}
        .stat-card::after{content:'';position:absolute;top:0;left:0;right:0;height:3px}
        .stat-card.green::after{background:var(--accent)}
        .stat-card.gold::after{background:var(--gold)}
        .stat-card.silver::after{background:var(--silver)}
        .stat-card.bronze::after{background:var(--bronze)}
        .stat-icon{width:44px;height:44px;border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:18px;margin-bottom:14px}
        .stat-icon.green{background:rgba(0,230,118,0.12);color:var(--accent)}
        .stat-icon.gold{background:var(--gold-bg);color:var(--gold)}
        .stat-icon.silver{background:var(--silver-bg);color:var(--silver)}
        .stat-icon.bronze{background:var(--bronze-bg);color:var(--bronze)}
        .stat-value{font-size:30px;font-weight:900;line-height:1;margin-bottom:4px}
        .stat-label{font-size:13px;color:var(--muted)}

        .packages-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:20px;margin-bottom:28px}
        .package-card{border-radius:var(--radius);padding:28px;text-align:center;position:relative;overflow:hidden;transition:all 0.3s;border:1px solid transparent}
        .package-card:hover{transform:translateY(-5px)}
        .package-card.gold-pkg{background:linear-gradient(180deg,var(--gold-bg),var(--card));border-color:var(--gold-border)}
        .package-card.silver-pkg{background:linear-gradient(180deg,var(--silver-bg),var(--card));border-color:var(--silver-border)}
        .package-card.bronze-pkg{background:linear-gradient(180deg,var(--bronze-bg),var(--card));border-color:var(--bronze-border)}
        .package-card.featured{box-shadow:0 0 40px rgba(255,215,64,0.1)}
        .package-badge{position:absolute;top:14px;left:14px;font-size:11px;font-weight:700;padding:4px 12px;border-radius:20px}
        .gold-pkg .package-badge{background:var(--gold);color:#1a1a00}
        .silver-pkg .package-badge{background:var(--silver);color:#1a1a1a}
        .bronze-pkg .package-badge{background:var(--bronze);color:#fff}
        .package-icon{font-size:40px;margin-bottom:14px}
        .gold-pkg .package-icon{color:var(--gold)}
        .silver-pkg .package-icon{color:var(--silver)}
        .bronze-pkg .package-icon{color:var(--bronze)}
        .package-name{font-size:22px;font-weight:900;margin-bottom:8px}
        .package-range{font-size:13px;color:var(--muted);margin-bottom:16px}
        .package-points{font-size:15px;font-weight:700;margin-bottom:18px;padding:10px;border-radius:8px;background:rgba(255,255,255,0.04)}
        .package-count{font-size:13px;color:var(--fg2);margin-top:12px}
        .package-count strong{color:var(--fg)}

        .table-container{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);overflow:hidden;margin-bottom:28px;}
        .table-header{padding:18px 22px;border-bottom:1px solid var(--border);display:flex;align-items:center;justify-content:space-between;}
        .table-title{font-size:16px;font-weight:700}
        table{width:100%;border-collapse:collapse;}
        th{padding:14px 22px;text-align:right;font-size:12px;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:0.5px;border-bottom:1px solid var(--border);background:rgba(0,0,0,0.15)}
        td{padding:14px 22px;font-size:14px;border-bottom:1px solid rgba(30,74,40,0.3)}
        tr:last-child td{border-bottom:none}
        tr:hover td{background:rgba(0,230,118,0.03)}
        .badge{display:inline-flex;align-items:center;gap:5px;padding:4px 12px;border-radius:20px;font-size:12px;font-weight:700}
        .badge-gold{background:var(--gold-bg);color:var(--gold);border:1px solid var(--gold-border)}
        .badge-silver{background:var(--silver-bg);color:var(--silver);border:1px solid var(--silver-border)}
        .badge-bronze{background:var(--bronze-bg);color:var(--bronze);border:1px solid var(--bronze-border)}

        .form-card{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:28px;max-width:520px}
        .form-card-title{font-size:18px;font-weight:700;margin-bottom:20px;display:flex;align-items:center;gap:10px}
        select.form-input{appearance:none;cursor:pointer}

        .collection-list{display:flex;flex-direction:column;gap:10px}
        .collection-item{background:var(--card);border:1px solid var(--border);border-radius:var(--radius-sm);padding:16px 20px;display:flex;align-items:center;justify-content:space-between;transition:all 0.2s}
        .collection-item:hover{border-color:rgba(0,230,118,0.3)}
        .collection-item-right{display:flex;align-items:center;gap:14px}
        .collection-item-icon{width:42px;height:42px;border-radius:10px;background:rgba(0,230,118,0.1);display:flex;align-items:center;justify-content:center;color:var(--accent)}
        .collection-item-date{font-size:12px;color:var(--muted)}
        .collection-item-qty{font-size:18px;font-weight:900;color:var(--accent)}
        .collection-item-pts{font-size:13px;color:var(--gold);font-weight:700}

        .leaderboard-item{background:var(--card);border:1px solid var(--border);border-radius:var(--radius-sm);padding:16px 20px;display:flex;align-items:center;gap:16px;margin-bottom:10px;transition:all 0.3s}
        .leaderboard-item:hover{transform:translateX(-4px);border-color:rgba(0,230,118,0.3)}
        .leaderboard-rank{width:36px;height:36px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-weight:900;font-size:15px;flex-shrink:0}
        .leaderboard-rank.r1{background:var(--gold-bg);color:var(--gold);border:1px solid var(--gold-border)}
        .leaderboard-rank.r2{background:var(--silver-bg);color:var(--silver);border:1px solid var(--silver-border)}
        .leaderboard-rank.r3{background:var(--bronze-bg);color:var(--bronze);border:1px solid var(--bronze-border)}
        .leaderboard-rank.rn{background:var(--bg);color:var(--muted)}
        .leaderboard-info{flex:1}
        .leaderboard-name{font-size:15px;font-weight:700}
        .leaderboard-pkg{font-size:12px;color:var(--muted)}
        .leaderboard-pts{font-size:20px;font-weight:900;color:var(--accent)}
        .leaderboard-pts-label{font-size:11px;color:var(--muted);text-align:center}

        .progress-bar-container{background:var(--bg);border-radius:10px;height:12px;overflow:hidden;margin-top:8px}
        .progress-bar{height:100%;border-radius:10px;transition:width 1s ease}
        .progress-bar.gold-bar{background:linear-gradient(90deg,var(--bronze),var(--gold))}
        .progress-bar.silver-bar{background:linear-gradient(90deg,var(--bronze),var(--silver))}
        .progress-bar.bronze-bar{background:var(--bronze)}

        .rewards-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));gap:16px;margin-bottom:28px}
        .reward-card{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:22px;text-align:center;transition:all 0.3s;position:relative;overflow:hidden}
        .reward-card:hover{transform:translateY(-4px);box-shadow:0 8px 24px rgba(0,0,0,0.3)}
        .reward-card.locked{opacity:0.5}
        .reward-card.locked::after{content:'\f023';font-family:'Font Awesome 6 Free';font-weight:900;position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);font-size:28px;color:var(--muted);opacity:0.5}
        .reward-icon{font-size:36px;margin-bottom:12px;color:var(--gold)}
        .reward-name{font-size:16px;font-weight:700;margin-bottom:6px}
        .reward-pts{font-size:13px;color:var(--accent);font-weight:700}
        .reward-btn{margin-top:14px}

        .toast-container{position:fixed;top:80px;left:24px;z-index:9999;display:flex;flex-direction:column;gap:10px}
        .toast{background:var(--card);border:1px solid var(--border);border-radius:var(--radius-sm);padding:14px 20px;display:flex;align-items:center;gap:12px;min-width:300px;box-shadow:0 8px 32px rgba(0,0,0,0.4);animation:toastIn 0.4s ease;font-size:14px;font-weight:600}
        .toast.success{border-color:rgba(0,230,118,0.4)}.toast.success i{color:var(--accent)}
        .toast.error{border-color:rgba(255,82,82,0.4)}.toast.error i{color:var(--danger)}
        .toast.warning{border-color:rgba(255,215,64,0.4)}.toast.warning i{color:var(--gold)}
        @keyframes toastIn{from{opacity:0;transform:translateX(-40px)}to{opacity:1;transform:translateX(0)}}
        @keyframes toastOut{from{opacity:1;transform:translateX(0)}to{opacity:0;transform:translateX(-40px)}}

        .modal-overlay{position:fixed;inset:0;background:rgba(0,0,0,0.7);backdrop-filter:blur(4px);z-index:1000;display:none;align-items:center;justify-content:center;padding:20px}
        .modal-overlay.show{display:flex;animation:fadeIn 0.3s ease}
        .modal{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:32px;width:100%;max-width:460px;animation:slideUp 0.4s ease}
        .modal-title{font-size:20px;font-weight:900;margin-bottom:16px}
        .modal-actions{display:flex;gap:10px;margin-top:24px;justify-content:flex-start}

        .restaurant-layout .sidebar{width:220px}
        .welcome-banner{background:linear-gradient(135deg,rgba(0,230,118,0.12),rgba(0,77,64,0.2));border:1px solid rgba(0,230,118,0.2);border-radius:var(--radius);padding:28px;margin-bottom:28px;display:flex;align-items:center;justify-content:space-between}
        .welcome-text h2{font-size:22px;font-weight:900;margin-bottom:6px}
        .welcome-text p{color:var(--fg2);font-size:14px}

        .save-indicator{position:fixed;bottom:20px;right:20px;z-index:200;background:var(--card);border:1px solid rgba(0,230,118,0.3);border-radius:10px;padding:10px 16px;display:flex;align-items:center;gap:8px;font-size:12px;font-weight:600;color:var(--accent);opacity:0;transform:translateY(10px);transition:all 0.3s;pointer-events:none}
        .save-indicator.show{opacity:1;transform:translateY(0)}

        .mobile-nav{display:none;position:fixed;bottom:0;left:0;right:0;background:rgba(10,26,15,0.95);backdrop-filter:blur(20px);border-top:1px solid var(--border);z-index:100;padding:8px 4px;gap:2px}
        .mobile-nav-item{flex:1;display:flex;flex-direction:column;align-items:center;gap:2px;padding:8px 4px;border:none;background:none;color:var(--muted);font-family:'Cairo';font-size:10px;font-weight:600;cursor:pointer;border-radius:8px;transition:all 0.2s}
        .mobile-nav-item.active{color:var(--accent);background:rgba(0,230,118,0.08)}
        .mobile-nav-item i{font-size:18px}
        .pulse-dot{width:8px;height:8px;border-radius:50%;background:var(--accent);display:inline-block;animation:pulse 2s ease infinite}
        @keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:0.4;transform:scale(1.5)}}

        @media(max-width:1024px){
            .packages-grid{grid-template-columns: repeat(2, 1fr); gap: 15px;}
            .stats-grid{grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); }
        }
        @media(max-width:768px){
            .sidebar{display:none;}
            .content{padding:16px;padding-top:20px;}
            .stats-grid{grid-template-columns: 1fr; gap: 12px;}
            .topbar{padding:0 16px;}
            .topbar-brand-text{display:none;}
            .topbar-user-info{display:none;}
            .welcome-banner{flex-direction:column;text-align:center;gap:16px;}
            .mobile-nav{display:flex !important; height: 60px;}
            .content{padding-bottom: 80px;}
        }
        @media(max-width:480px){
            .login-box{padding:32px 24px;}
            .packages-grid{grid-template-columns: 1fr; gap: 15px;}
            .table-container{overflow-x: auto;}
            table{font-size: 12px;}
            th,td{padding: 10px 8px;}
            .table-header{padding:12px 16px;}
            .page-title{font-size:20px;}
            .page-desc{display: none;}
        }
        ::-webkit-scrollbar{width:6px}::-webkit-scrollbar-track{background:var(--bg)}::-webkit-scrollbar-thumb{background:var(--border);border-radius:3px}
    </style>
</head>
<body>

<div class="bg-effects"><div class="blob blob-1"></div><div class="blob blob-2"></div><div class="blob blob-3"></div></div>
<div class="toast-container" id="toastContainer"></div>
<div class="modal-overlay" id="modalOverlay"><div class="modal" id="modalContent"></div></div>
<div class="save-indicator" id="saveIndicator"><i class="fas fa-check-circle"></i> تم الحفظ بنجاح</div>

<div class="app-container">

    <!-- تسجيل الدخول -->
    <div class="login-screen" id="loginScreen">
        <div class="login-box">
            <div class="login-logo">
                <img src="https://z-cdn-media.chatglm.cn/files/57f6f9c3-d069-4883-85da-b02ecd157280.jpg?auth_key=1889503561-8068c24ba349406a8cedab55b86564c2-0-270bcff4b63d89d6c674006d6a126c26" alt="Ad_cycel Logo">
            </div>
            <h1 class="login-title">Ad_cycel</h1>
            <p class="login-subtitle">نظام إدارة جمع القوارير البلاستيكية الذكي</p>
            
            <div id="loginForm">
                <div class="form-group">
                    <label>البريد الإلكتروني</label>
                    <div class="input-icon-wrapper">
                        <input type="email" class="form-input icon-input" id="loginEmail" placeholder="example@domain.com">
                        <i class="fas fa-envelope"></i>
                    </div>
                </div>
                <div class="form-group">
                    <label>كلمة السر</label>
                    <div class="input-icon-wrapper">
                        <input type="password" class="form-input icon-input" id="loginCode" placeholder="أدخل كلمة السر">
                        <i class="fas fa-key"></i>
                    </div>
                </div>
                
                <p id="forgotPassLink" style="margin-top:-10px;margin-bottom:18px;font-size:12px;text-align:left;"><span style="color:var(--accent);cursor:pointer;" onclick="showForgotPassword()">هل نسيت كلمة السر؟</span></p>

                <div id="registerFields" style="display:none;">
                    <div class="form-group"><label>اسم المطعم</label><input type="text" class="form-input" id="regRestName" placeholder="مثال: ATLANTA"></div>
                    <div class="form-group"><label>رقم الهاتف</label><input type="tel" class="form-input" id="regPhone" placeholder="0550 00 00 00"></div>
                    <div class="form-group"><label>عنوان المطعم</label><input type="text" class="form-input" id="regAddress" placeholder="الولاية - البلدية"></div>
                    <div class="form-group">
                        <label>البريد الإلكتروني</label>
                        <div class="input-icon-wrapper">
                            <input type="email" class="form-input icon-input" id="regEmail" placeholder="example@domain.com">
                            <i class="fas fa-envelope"></i>
                        </div>
                    </div>
                    <div class="form-group">
                        <label>كلمة السر</label>
                        <div class="input-icon-wrapper">
                            <input type="password" class="form-input icon-input" id="regCode" placeholder="اختر كلمة السر">
                            <i class="fas fa-key"></i>
                        </div>
                    </div>
                </div>
                
                <button class="btn btn-primary" onclick="handleLogin()"><i class="fas fa-arrow-left"></i><span id="loginBtnText">تسجيل الدخول</span></button>
                <p style="margin-top:14px;font-size:13px;color:var(--muted);"><span id="toggleRegText" style="color:var(--accent);cursor:pointer;" onclick="toggleRegister()">ليس لديك حساب؟ سجل الآن</span></p>
            </div>
        </div>
    </div>

    <!-- واجهة المدير -->
    <div id="adminDashboard" style="display:none;">
        <header class="topbar">
            <div class="topbar-brand">
                <div class="topbar-brand-icon">
                    <img src="https://z-cdn-media.chatglm.cn/files/e3a354f3-0bb9-4a01-8f7e-1064f913a748.jpg?auth_key=1889499426-bbb8954530794cfeaa8e5def2ca3579a-0-6a0d15fd6f13550023c5694edf47e802" alt="Ad_cycel Logo">
                </div>
                <div class="topbar-brand-text">Ad_cycel</div>
            </div>
            <div class="topbar-user">
                <div class="topbar-user-info"><div class="topbar-user-name">مدير المشروع</div><div class="topbar-user-role"><span class="pulse-dot"></span> متصل الآن</div></div>
                <div class="topbar-avatar"><i class="fas fa-user-tie"></i></div>
                <button class="btn-logout" onclick="logout()"><i class="fas fa-right-from-bracket"></i></button>
            </div>
        </header>
        <div class="main-layout">
            <nav class="sidebar">
                <div class="sidebar-label">الرئيسية</div>
                <button class="sidebar-item active" onclick="showAdminPage('overview',this)"><i class="fas fa-chart-pie"></i> نظرة عامة</button>
                <button class="sidebar-item" onclick="showAdminPage('restaurants',this)"><i class="fas fa-store"></i> المطاعم <span class="sidebar-badge" id="restCountBadge">0</span></button>
                <button class="sidebar-item" onclick="showAdminPage('packages',this)"><i class="fas fa-crown"></i> الباقات</button>
                <div class="sidebar-label">البيانات</div>
                <button class="sidebar-item" onclick="showAdminPage('leaderboard',this)"><i class="fas fa-trophy"></i> المتصدرين</button>
                <button class="sidebar-item" onclick="showAdminPage('allCollections',this)"><i class="fas fa-list-check"></i> سجل الجمع</button>
                <button class="sidebar-item" onclick="showAdminPage('rewardsAdmin',this)"><i class="fas fa-gift"></i> المكافآت</button>
                <div class="sidebar-label">النظام</div>
                <button class="sidebar-item" onclick="showAdminPage('settings',this)"><i class="fas fa-database"></i> النسخ الاحتياطي</button>
            </nav>
            <main class="content">
                <div class="page active" id="admin-overview">
                    <div class="page-header"><h1 class="page-title">نظرة عامة</h1><p class="page-desc">ملخص شامل لأداء مشروع جمع البلاستيك</p></div>
                    <div class="stats-grid" id="adminStats"></div>
                    <div class="table-container"><div class="table-header"><span class="table-title"><i class="fas fa-clock"></i> آخر عمليات الجمع</span></div>
                        <table><thead><tr><th>المطعم</th><th>الكمية (كجم)</th><th>النقاط</th><th>التاريخ</th><th>الباقة</th></tr></thead><tbody id="recentCollectionsTable"></tbody></table>
                    </div>
                </div>
                <div class="page" id="admin-restaurants">
                    <div class="page-header"><h1 class="page-title">إدارة المطاعم</h1><p class="page-desc">عرض وإدارة جميع المطاعم المسجلة في المشروع</p></div>
                    <div class="table-container"><div class="table-header"><span class="table-title"><i class="fas fa-store"></i> قائمة المطاعم</span></div>
                        <table><thead><tr><th>#</th><th>المطعم</th><th>الهاتف</th><th>إجمالي الكمية</th><th>النقاط</th><th>الباقة</th><th>إجراء</th></tr></thead><tbody id="restaurantsTable"></tbody></table>
                    </div>
                </div>
                <div class="page" id="admin-packages">
                    <div class="page-header"><h1 class="page-title">نظام الباقات</h1><p class="page-desc">الباقات الثلاث حسب حجم الجمع مع النقاط المقابلة</p></div>
                    <div class="packages-grid" id="packagesGrid"></div>
                </div>
                <div class="page" id="admin-leaderboard">
                    <div class="page-header"><h1 class="page-title">لوحة المتصدرين</h1><p class="page-desc">ترتيب المطاعم حسب النقاط المكتسبة</p></div>
                    <div id="leaderboardList"></div>
                </div>
                <div class="page" id="admin-allCollections">
                    <div class="page-header"><h1 class="page-title">سجل جميع عمليات الجمع</h1><p class="page-desc">كل كميات البلاستيك التي تم جمعها</p></div>
                    <div class="collection-list" id="allCollectionsList"></div>
                </div>
                <div class="page" id="admin-rewardsAdmin">
                    <div class="page-header"><h1 class="page-title">إدارة المكافآت</h1><p class="page-desc">المكافآت المتاحة للمطاعم حسب النقاط</p></div>
                    <div class="rewards-grid" id="rewardsAdminGrid"></div>
                </div>
                <div class="page" id="admin-settings">
                    <div class="page-header"><h1 class="page-title">النسخ الاحتياطي وإدارة البيانات</h1><p class="page-desc">تصدير واستيراد وحذف بيانات التطبيق</p></div>
                    <div class="stats-grid">
                        <div class="stat-card green" style="cursor:pointer;" onclick="exportData()"><div class="stat-icon green"><i class="fas fa-download"></i></div><div class="stat-value" style="font-size:18px;">تصدير البيانات</div><div class="stat-label">تحميل نسخة احتياطية كملف JSON</div></div>
                        <div class="stat-card gold" style="cursor:pointer;" onclick="document.getElementById('importFile').click()"><div class="stat-icon gold"><i class="fas fa-upload"></i></div><div class="stat-value" style="font-size:18px;">استيراد البيانات</div><div class="stat-label">استعادة من ملف نسخة احتياطية</div><input type="file" id="importFile" accept=".json" style="display:none;" onchange="importData(event)"></div>
                        <div class="stat-card bronze" style="cursor:pointer;" onclick="resetAllData()"><div class="stat-icon bronze"><i class="fas fa-trash-alt"></i></div><div class="stat-value" style="font-size:18px;">مسح جميع البيانات</div><div class="stat-label">حذف كل شيء وإعادة التعيين</div></div>
                    </div>
                    <div style="background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:22px;margin-top:8px;">
                        <h3 style="font-size:15px;font-weight:700;margin-bottom:12px;"><i class="fas fa-info-circle" style="color:var(--accent);"></i> حالة التخزين</h3>
                        <div id="storageInfo" style="font-size:13px;color:var(--fg2);line-height:2;"></div>
                    </div>
                </div>
            </main>
        </div>
    </div>

    <!-- واجهة المطعم -->
    <div id="restaurantDashboard" style="display:none;">
        <header class="topbar">
            <div class="topbar-brand">
                <div class="topbar-brand-icon">
                    <img src="https://z-cdn-media.chatglm.cn/files/e3a354f3-0bb9-4a01-8f7e-1064f913a748.jpg?auth_key=1889499426-bbb8954530794cfeaa8e5def2ca3579a-0-6a0d15fd6f13550023c5694edf47e802" alt="Ad_cycel Logo">
                </div>
                <div class="topbar-brand-text">Ad_cycel</div>
            </div>
            <div class="topbar-user">
                <div class="topbar-user-info"><div class="topbar-user-name" id="restTopbarName">المطعم</div><div class="topbar-user-role" id="restTopbarPkg"><span class="pulse-dot"></span> باقة برونزية</div></div>
                <div class="topbar-avatar"><i class="fas fa-store"></i></div>
                <button class="btn-logout" onclick="logout()"><i class="fas fa-right-from-bracket"></i></button>
            </div>
        </header>
        <div class="main-layout restaurant-layout">
            <nav class="sidebar">
                <div class="sidebar-label">الرئيسية</div>
                <button class="sidebar-item active" onclick="showRestPage('home',this)"><i class="fas fa-home"></i> الرئيسية</button>
                <button class="sidebar-item" onclick="showRestPage('addCollection',this)"><i class="fas fa-plus-circle"></i> تسجيل جمع</button>
                <button class="sidebar-item" onclick="showRestPage('myHistory',this)"><i class="fas fa-history"></i> سجلي</button>
                <div class="sidebar-label">المزيد</div>
                <button class="sidebar-item" onclick="showRestPage('myPackage',this)"><i class="fas fa-crown"></i> باقتي</button>
                <button class="sidebar-item" onclick="showRestPage('myRewards',this)"><i class="fas fa-gift"></i> المكافآت</button>
                <button class="sidebar-item" onclick="showRestPage('myLeaderboard',this)"><i class="fas fa-trophy"></i> الترتيب</button>
            </nav>
            <nav class="mobile-nav" id="restMobileNav">
                <button class="mobile-nav-item active" onclick="showRestPage('home',this)"><i class="fas fa-home"></i>الرئيسية</button>
                <button class="mobile-nav-item" onclick="showRestPage('addCollection',this)"><i class="fas fa-plus-circle"></i>تسجيل</button>
                <button class="mobile-nav-item" onclick="showRestPage('myHistory',this)"><i class="fas fa-history"></i>سجلي</button>
                <button class="mobile-nav-item" onclick="showRestPage('myPackage',this)"><i class="fas fa-crown"></i>باقتي</button>
                <button class="mobile-nav-item" onclick="showRestPage('myRewards',this)"><i class="fas fa-gift"></i>مكافآت</button>
                <button class="mobile-nav-item" onclick="showRestPage('myLeaderboard',this)"><i class="fas fa-trophy"></i>الترتيب</button>
            </nav>
            <main class="content" style="padding-bottom:80px;">
                <div class="page active" id="rest-home">
                    <div class="welcome-banner">
                        <div class="welcome-text"><h2 id="restWelcomeName">مرحباً بك</h2><p>ساهم في حماية البيئة واكسب نقاطاً ومكافآت مقابل كل كجم تجمعه</p></div>
                        <button class="btn btn-accent btn-sm" onclick="showRestPage('addCollection')"><i class="fas fa-plus"></i> سجّل جمع جديد</button>
                    </div>
                    <div class="stats-grid" id="restStats"></div>
                </div>
                <div class="page" id="rest-addCollection">
                    <div class="page-header"><h1 class="page-title">تسجيل عملية جمع جديدة</h1><p class="page-desc">أدخل كمية البلاستيك التي قمت بجمعها</p></div>
                    <div class="form-card">
                        <div class="form-card-title"><i class="fas fa-recycle" style="color:var(--accent)"></i> بيانات الجمع</div>
                        <div class="form-group"><label>كمية البلاستيك (بالكيلوغرام)</label><input type="number" class="form-input" id="collectQty" placeholder="مثال: 25" min="0.5" step="0.5"></div>
                        <div class="form-group"><label>نوع القوارير</label><select class="form-input" id="collectType"><option value="water">قوارير مياه</option><option value="soft">قوارير مشروبات غازية</option><option value="mixed">خليط</option></select></div>
                        <div class="form-group"><label>ملاحظات (اختياري)</label><input type="text" class="form-input" id="collectNotes" placeholder="أي ملاحظات إضافية..."></div>
                        <button class="btn btn-primary" onclick="submitCollection()" style="margin-top:8px;"><i class="fas fa-check-circle"></i> تأكيد التسجيل</button>
                    </div>
                </div>
                <div class="page" id="rest-myHistory">
                    <div class="page-header"><h1 class="page-title">سجل عمليات الجمع</h1><p class="page-desc">جميع الكميات التي سجلتها مسبقاً</p></div>
                    <div class="collection-list" id="myHistoryList"></div>
                </div>
                <div class="page" id="rest-myPackage">
                    <div class="page-header"><h1 class="page-title">باقتي الحالية</h1><p class="page-desc">معلومات عن الباقة التي أنت فيها وكيفية الترقية</p></div>
                    <div id="myPackageDetails"></div>
                </div>
                <div class="page" id="rest-myRewards">
                    <div class="page-header"><h1 class="page-title">المكافآت المتاحة</h1><p class="page-desc">استبدل نقاطك بمكافآت قيّمة</p></div>
                    <div class="rewards-grid" id="myRewardsGrid"></div>
                </div>
                <div class="page" id="rest-myLeaderboard">
                    <div class="page-header"><h1 class="page-title">ترتيب المطاعم</h1><p class="page-desc">شاهد مكانك بين المطاعم الأخرى</p></div>
                    <div id="restLeaderboardList"></div>
                </div>
            </main>
        </div>
    </div>
</div>

<script>
const STORAGE_KEY = 'adcycel_data';
const PACKAGES = {
    bronze:{name:'برونزية',icon:'fa-medal',minKg:0,maxKg:100,pointsPerKg:1,cssClass:'bronze',badgeClass:'badge-bronze',color:'var(--bronze)',barClass:'bronze-bar'},
    silver:{name:'فضية',icon:'fa-medal',minKg:101,maxKg:300,pointsPerKg:2,cssClass:'silver',badgeClass:'badge-silver',color:'var(--silver)',barClass:'silver-bar'},
    gold:{name:'ذهبية',icon:'fa-crown',minKg:301,maxKg:Infinity,pointsPerKg:3,cssClass:'gold',badgeClass:'badge-gold',color:'var(--gold)',barClass:'gold-bar'}
};
const REWARDS=[
    {id:1,name:'شهادة شكر رسمية',pts:50,icon:'fa-certificate',desc:'شهادة تقدير من المشروع'},
    {id:2,name:'خصم 10% على خدمات النظافة',pts:150,icon:'fa-broom',desc:'شريك مع شركة نظافة'},
    {id:3,name:'لافتة "مطعم صديق البيئة"',pts:300,icon:'fa-sign-hanging',desc:'لافتة يتم تعليقها على المدخل'},
    {id:4,name:'دعوة لحفل التكريم السنوي',pts:500,icon:'fa-glass-cheers',desc:'تذاكر لحفل اختتام المشروع'},
    {id:5,name:'حملة إعلانية مجانية',pts:800,icon:'fa-bullhorn',desc:'ترويج عبر حسابات المشروع'},
    {id:6,name:'درع التميز الذهبي',pts:1200,icon:'fa-award',desc:'درع تذكاري ذهبي مع جائزة مالية'}
];

const DEFAULT_DATA={
    restaurants:[
        {id:1,name:'ATLANTA',phone:'0550123456',address:'الجزائر العاصمة - سطيف',email:'atlanta@mail.com',code:'1111',totalKg:340,points:0,spentPoints:0,claimedRewards:[]},
        {id:2,name:'mega pizza',phone:'0661987654',address:'البليدة - العاصمة',email:'mega@mail.com',code:'2222',totalKg:180,points:0,spentPoints:0,claimedRewards:[]},
        {id:3,name:'miga food',phone:'0771345678',address:'وهران - حي الراية',email:'miga@mail.com',code:'3333',totalKg:85,points:0,spentPoints:0,claimedRewards:[]},
        {id:4,name:'nativo',phone:'0550123456',address:'قسنطينة - حي الشهداء',email:'nativo@mail.com',code:'4444',totalKg:420,points:0,spentPoints:0,claimedRewards:[]},
        {id:5,name:'les platan',phone:'0552345678',address:'عنابة - حي البحيرة',email:'lesplatan@mail.com',code:'5555',totalKg:55,points:0,spentPoints:0,claimedRewards:[]}
    ],
    collections:[
        {id:1,restId:1,qty:50,type:'water',notes:'جمع أولي',date:'2023-08-10T10:00:00Z',pointsEarned:50},
        {id:2,restId:1,qty:90,type:'mixed',notes:'ترويج للباقة الفضية',date:'2023-09-15T14:30:00Z',pointsEarned:130},
        {id:3,restId:1,qty:200,type:'soft',notes:'جمع كبير نهاية العام',date:'2023-10-20T09:15:00Z',pointsEarned:440},
        {id:4,restId:2,qty:80,type:'water',notes:'بداية التعاون',date:'2023-09-05T11:00:00Z',pointsEarned:80},
        {id:5,restId:2,qty:100,type:'mixed',notes:'تحسن ملحوظ',date:'2023-10-12T16:45:00Z',pointsEarned:180},
        {id:6,restId:3,qty:85,type:'water',notes:'جمع الشهر الأول',date:'2023-10-01T08:30:00Z',pointsEarned:85},
        {id:7,restId:4,qty:120,type:'soft',notes:'مطعم نشط جداً',date:'2023-07-15T13:20:00Z',pointsEarned:140},
        {id:8,restId:4,qty:130,type:'water',notes:'الوصول للفضية',date:'2023-08-20T10:10:00Z',pointsEarned:260},
        {id:9,restId:4,qty:170,type:'mixed',notes:'الوصول للذهبية!',date:'2023-09-25T15:00:00Z',pointsEarned:460},
        {id:10,restId:5,qty:55,type:'water',notes:'بداية متواضعة',date:'2023-11-18T09:00:00Z',pointsEarned:55}
    ],
    nextCollectionId:11,
    nextRestId:6
};

let restaurants=[],collections=[],nextCollectionId=1,nextRestId=6;

function loadData(){
    try{
        const saved=localStorage.getItem(STORAGE_KEY);
        if(saved){const d=JSON.parse(saved);restaurants=d.restaurants||[];collections=d.collections||[];nextCollectionId=d.nextCollectionId||1;nextRestId=d.nextRestId||1;}
        else{restaurants=JSON.parse(JSON.stringify(DEFAULT_DATA.restaurants));collections=JSON.parse(JSON.stringify(DEFAULT_DATA.collections));nextCollectionId=DEFAULT_DATA.nextCollectionId;nextRestId=DEFAULT_DATA.nextRestId;recalcAllPoints();saveData();}
        restaurants.forEach(r => { if(typeof r.spentPoints === 'undefined') r.spentPoints = 0; if(!r.email) r.email = r.name.toLowerCase().replace(/\s/g,'')+'@mail.com'; if(!r.code) r.code = '1234'; if(!r.claimedRewards) r.claimedRewards = []; });
    }catch(e){
        restaurants=JSON.parse(JSON.stringify(DEFAULT_DATA.restaurants));collections=JSON.parse(JSON.stringify(DEFAULT_DATA.collections));nextCollectionId=DEFAULT_DATA.nextCollectionId;nextRestId=DEFAULT_DATA.nextRestId;recalcAllPoints();
    }
}

function saveData(){
    try{localStorage.setItem(STORAGE_KEY,JSON.stringify({restaurants,collections,nextCollectionId,nextRestId}));showSaveIndicator();}catch(e){showToast('خطأ في حفظ البيانات!','error');}
}

function showSaveIndicator(){const el=document.getElementById('saveIndicator');el.classList.add('show');setTimeout(()=>el.classList.remove('show'),2000);}

function exportData(){
    const data={restaurants,collections,nextCollectionId,nextRestId,exportDate:new Date().toISOString()};
    const blob=new Blob([JSON.stringify(data,null,2)],{type:'application/json'});
    const url=URL.createObjectURL(blob);const a=document.createElement('a');a.href=url;a.download=`Adcycel_backup_${new Date().toISOString().split('T')[0]}.json`;a.click();URL.revokeObjectURL(url);showToast('تم تصدير النسخة الاحتياطية','success');
}
function importData(event){
    const file=event.target.files[0];if(!file)return;
    showModal(`<div class="modal-title">تأكيد الاستيراد</div><p style="color:var(--fg2);font-size:14px;">سيتم استبدال جميع البيانات الحالية بالبيانات من الملف.</p><div class="modal-actions"><button class="btn btn-sm btn-warning" onclick="confirmImport()">نعم، استبدل</button><button class="btn btn-sm btn-outline" onclick="closeModal()">إلغاء</button></div>`);
    window._importFile=file;event.target.value='';
}
function confirmImport(){
    const file=window._importFile;if(!file)return;
    const reader=new FileReader();
    reader.onload=function(e){try{const d=JSON.parse(e.target.result);if(!d.restaurants||!d.collections)throw new Error('ملف غير صالح');restaurants=d.restaurants;collections=d.collections;nextCollectionId=d.nextCollectionId||collections.length+1;nextRestId=d.nextRestId||restaurants.length+1;recalcAllPoints();saveData();closeModal();renderAdminDashboard();showToast('تم استيراد البيانات بنجاح!','success');}catch(err){closeModal();showToast('ملف غير صالح!','error');}};
    reader.readAsText(file);window._importFile=null;
}
function resetAllData(){
    showModal(`<div class="modal-title">مسح جميع البيانات</div><p style="color:var(--danger);font-size:14px;font-weight:700;margin-bottom:8px;">تحذير: لا يمكن التراجع عن هذا الإجراء!</p><div class="modal-actions"><button class="btn btn-sm btn-danger" onclick="confirmReset()">نعم، امسح الكل</button><button class="btn btn-sm btn-outline" onclick="closeModal()">إلغاء</button></div>`);}
function confirmReset(){localStorage.removeItem(STORAGE_KEY);loadData();closeModal();renderAdminDashboard();showToast('تم مسح البيانات وإعادة التعيين','warning');}

function updateStorageInfo(){const el=document.getElementById('storageInfo');if(!el)return;const saved=localStorage.getItem(STORAGE_KEY);const size=saved?(new Blob([saved]).size/1024).toFixed(2):'0';el.innerHTML=`<div><i class="fas fa-database" style="color:var(--accent);"></i> حجم البيانات: <strong>${size} كيلوبايت</strong></div><div><i class="fas fa-store" style="color:var(--gold);"></i> عدد المطاعم: <strong>${restaurants.length}</strong></div><div><i class="fas fa-list" style="color:var(--silver);"></i> سجلات الجمع: <strong>${collections.length}</strong></div><div><i class="fas fa-clock" style="color:var(--muted);"></i> آخر حفظ: <strong>${new Date().toLocaleString('ar-SA')}</strong></div>`;}

function getPackage(kg){if(kg>=301)return PACKAGES.gold;if(kg>=101)return PACKAGES.silver;return PACKAGES.bronze;}
function calcTotalPoints(kg){let p=0;p+=Math.min(kg,100)*1;if(kg>100)p+=Math.min(kg-100,200)*2;if(kg>300)p+=(kg-300)*3;return Math.round(p);}
function recalcAllPoints(){restaurants.forEach(r=>{r.points=calcTotalPoints(r.totalKg);if(typeof r.spentPoints === 'undefined') r.spentPoints = 0;});}
function formatDate(d){return new Date(d).toLocaleDateString('ar-SA',{year:'numeric',month:'short',day:'numeric'});}
function typeLabel(t){return{water:'قوارير مياه',soft:'مشروبات غازية',mixed:'خليط'}[t]||t;}

function showToast(msg,type='success'){const c=document.getElementById('toastContainer');const icons={success:'fa-check-circle',error:'fa-times-circle',warning:'fa-exclamation-triangle'};const t=document.createElement('div');t.className=`toast ${type}`;t.innerHTML=`<i class="fas ${icons[type]}"></i> ${msg}`;c.appendChild(t);setTimeout(()=>{t.style.animation='toastOut 0.4s ease forwards';setTimeout(()=>t.remove(),400);},3000);}
function showModal(html){document.getElementById('modalContent').innerHTML=html;document.getElementById('modalOverlay').classList.add('show');}
function closeModal(){document.getElementById('modalOverlay').classList.remove('show');}
document.getElementById('modalOverlay').addEventListener('click',function(e){if(e.target===this)closeModal();});

let isRegistering=false,currentRestId=null;
let currentResetOTP=null,currentResetEmail=null;

// استعادة كلمة السر
function showForgotPassword() {
    currentResetOTP = null; currentResetEmail = null;
    showModal(`
        <div id="forgotPhase1">
            <div class="modal-title">استعادة كلمة السر</div>
            <p style="color:var(--fg2);font-size:14px;margin-bottom:16px;">أدخل بريدك الإلكتروني المسجل لدينا لتلقي رمز التحقق.</p>
            <div class="form-group"><label>البريد الإلكتروني</label><input type="email" class="form-input" id="forgotEmail" placeholder="example@domain.com"></div>
            <div class="modal-actions"><button class="btn btn-sm btn-accent" onclick="sendResetCode()">إرسال رمز التحقق</button><button class="btn btn-sm btn-outline" onclick="closeModal()">إلغاء</button></div>
        </div>
        <div id="forgotPhase2" style="display:none;">
            <div class="modal-title">تعيين كلمة السر الجديدة</div>
            <p style="color:var(--fg2);font-size:14px;margin-bottom:16px;">أدخل الرمز الذي وصلك وكلمة السر الجديدة.</p>
            <div class="form-group"><label>رمز التحقق (OTP)</label><input type="text" class="form-input" id="forgotOtp" placeholder="مثال: 4567"></div>
            <div class="form-group"><label>كلمة السر الجديدة</label><input type="password" class="form-input" id="forgotNewPass" placeholder="اختر كلمة سر جديدة"></div>
            <div class="modal-actions"><button class="btn btn-sm btn-accent" onclick="verifyAndResetPassword()">حفظ التغييرات</button><button class="btn btn-sm btn-outline" onclick="closeModal()">إلغاء</button></div>
        </div>
    `);
}

function sendResetCode() {
    const email = document.getElementById('forgotEmail').value.trim();
    if (!email) { showToast('يرجى إدخال البريد الإلكتروني', 'error'); return; }
    
    const rest = restaurants.find(r => r.email === email);
    if (!rest) { showToast('هذا البريد غير مسجل في النظام', 'error'); return; }

    currentResetOTP = Math.floor(1000 + Math.random() * 9000).toString();
    currentResetEmail = email;

    showToast(`رمز التحقق الخاص بك هو: ${currentResetOTP} (للمحاكاة فقط)`, 'warning');
    
    document.getElementById('forgotPhase1').style.display = 'none';
    document.getElementById('forgotPhase2').style.display = 'block';
}

function verifyAndResetPassword() {
    const otp = document.getElementById('forgotOtp').value.trim();
    const newPass = document.getElementById('forgotNewPass').value.trim();

    if (!otp || !newPass) { showToast('يرجى ملء الرمز وكلمة السر', 'error'); return; }
    if (otp !== currentResetOTP) { showToast('رمز التحقق غير صحيح', 'error'); return; }

    const rest = restaurants.find(r => r.email === currentResetEmail);
    if (rest) {
        rest.code = newPass;
        saveData();
        closeModal();
        showToast('تم تغيير كلمة السر بنجاح! يمكنك تسجيل الدخول الآن', 'success');
        currentResetOTP = null; currentResetEmail = null;
    }
}

function toggleRegister() {
    isRegistering = !isRegistering;
    const regFields = document.getElementById('registerFields');
    const btnText = document.getElementById('loginBtnText');
    const toggleText = document.getElementById('toggleRegText');
    const forgotLink = document.getElementById('forgotPassLink');
    
    regFields.style.display = isRegistering ? 'block' : 'none';
    btnText.innerText = isRegistering ? 'إنشاء حساب' : 'تسجيل الدخول';
    toggleText.innerText = isRegistering ? 'لديك حساب؟ سجل دخولك' : 'ليس لديك حساب؟ سجل الآن';
    if(forgotLink) forgotLink.style.display = isRegistering ? 'none' : 'block';
}

function handleLogin() {
    const email = document.getElementById('loginEmail').value.trim();
    const code = document.getElementById('loginCode').value.trim();

    if (!email || !code) { showToast('يرجى إدخال البريد وكلمة السر', 'error'); return; }

    if (isRegistering) {
        const name = document.getElementById('regRestName').value.trim();
        const phone = document.getElementById('regPhone').value.trim();
        const address = document.getElementById('regAddress').value.trim();
        const regEmail = document.getElementById('regEmail').value.trim();
        const regCode = document.getElementByIdG(`regCode`).value.trim();

        if (!name || !regEmail || !regCode) { showToast('يرجى ملء جميع الحقول المطلوبة', 'error'); return; }
        if (restaurants.find(r => r.email === regEmail)) { showToast('هذا البريد مسجل مسبقاً', 'error'); return; }

        const newRest = { id: nextRestId++, name, phone, address, email: regEmail, code: regCode, totalKg: 0, points: 0, spentPoints: 0, claimedRewards: [] };
        restaurants.push(newRest);
        saveData();
        showToast('تم إنشاء الحساب بنجاح! جاري تسجيل دخولك...', 'success');
        
        currentRestId = newRest.id;
        document.getElementById('loginScreen').style.display = 'none';
        document.getElementById('restaurantDashboard').style.display = 'block';
        renderRestDashboard();
        toggleRegister(); 
        return;
    }

    // دخول المدير
    if (email === 'admin@adcycel.com' && code === 'admin123') {
        document.getElementById('loginScreen').style.display = 'none';
        document.getElementById('adminDashboard').style.display = 'block';
        renderAdminDashboard();
        return;
    }

    // دخول المطعم
    const rest = restaurants.find(r => r.email === email && r.code === code);
    if (rest) {
        currentRestId = rest.id;
        document.getElementById('loginScreen').style.display = 'none';
        document.getElementById('restaurantDashboard').style.display = 'block';
        renderRestDashboard();
    } else {
        showToast('البريد الإلكتروني أو كلمة السر غير صحيحة', 'error');
    }
}

function logout() {
    currentRestId = null;
    document.getElementById('loginScreen').style.display = 'flex';
    document.getElementById('adminDashboard').style.display = 'none';
    document.getElementById('restaurantDashboard').style.display = 'none';
}

// Rendering methods (added to ensure the app works properly)
function renderAdminDashboard() {
    document.getElementById('restCountBadge').innerText = restaurants.length;
    updateStorageInfo();
    // Basic rendering logic for overview stats
    const totalKg = collections.reduce((s,c) => s + c.qty, 0);
    const totalPoints = restaurants.reduce((s,r) => s + r.points, 0);
    document.getElementById('adminStats').innerHTML = `
        <div class="stat-card green"><div class="stat-icon green"><i class="fas fa-recycle"></i></div><div class="stat-value">${totalKg}</div><div class="stat-label">إجمالي الكمية (كجم)</div></div>
        <div class="stat-card gold"><div class="stat-icon gold"><i class="fas fa-store"></i></div><div class="stat-value">${restaurants.length}</div><div class="stat-label">المطاعم المسجلة</div></div>
        <div class="stat-card silver"><div class="stat-icon silver"><i class="fas fa-star"></i></div><div class="stat-value">${totalPoints}</div><div class="stat-label">إجمالي النقاط</div></div>
    `;
    // Render recent collections table
    const recent = [...collections].sort((a,b) => new Date(b.date) - new Date(a.date)).slice(0, 5);
    document.getElementById('recentCollectionsTable').innerHTML = recent.map(c => {
        const r = restaurants.find(x => x.id === c.restId);
        const pkg = getPackage(r ? r.totalKg : 0);
        return `<tr><td>${r ? r.name : 'غير معروف'}</td><td>${c.qty}</td><td>${c.pointsEarned}</td><td>${formatDate(c.date)}</td><td><span class="badge ${pkg.badgeClass}">${pkg.name}</span></td></tr>`;
    }).join('');
}

function renderRestDashboard() {
    const rest = restaurants.find(r => r.id === currentRestId);
    if (!rest) return;
    const pkg = getPackage(rest.totalKg);
    
    document.getElementById('restTopbarName').innerText = rest.name;
    document.getElementById('restTopbarPkg').innerHTML = `<span class="pulse-dot"></span> باقة ${pkg.name}`;
    document.getElementById('restWelcomeName').innerText = `مرحباً بك، ${rest.name}`;
    
    document.getElementById('restStats').innerHTML = `
        <div class="stat-card green"><div class="stat-icon green"><i class="fas fa-recycle"></i></div><div class="stat-value">${rest.totalKg}</div><div class="stat-label">إجمالي الكمية (كجم)</div></div>
        <div class="stat-card gold"><div class="stat-icon gold"><i class="fas fa-star"></i></div><div class="stat-value">${rest.points - rest.spentPoints}</div><div class="stat-label">نقاطك المتاحة</div></div>
        <div class="stat-card bronze"><div class="stat-icon bronze"><i class="fas ${pkg.icon}"></i></div><div class="stat-value">${pkg.name}</div><div class="stat-label">باقتك الحالية</div></div>
    `;
}

function submitCollection() {
    const qty = parseFloat(document.getElementById('collectQty').value);
    if (!qty || qty <= 0) { showToast('يرجى إدخال كمية صحيحة', 'error'); return; }
    const type = document.getElementById('collectType').value;
    const notes = document.getElementById('collectNotes').value.trim();
    const rest = restaurants.find(r => r.id === currentRestId);
    if (!rest) return;

    const pkg = getPackage(rest.totalKg);
    const pointsEarned = Math.round(qty * pkg.pointsPerKg);

    const collection = {
        id: nextCollectionId++,
        restId: currentRestId,
        qty,
        type,
        notes,
        date: new Date().toISOString(),
        pointsEarned
    };

    collections.push(collection);
    rest.totalKg += qty;
    recalcAllPoints();
    saveData();

    showToast(`تم تسجيل ${qty} كجم واكتساب ${pointsEarned} نقطة!`, 'success');
    document.getElementById('collectQty').value = '';
    document.getElementById('collectNotes').value = '';
    renderRestDashboard();
    showRestPage('home');
}

function showAdminPage(pageId, btn) {
    document.querySelectorAll('#adminDashboard .page').forEach(p => p.classList.remove('active'));
    document.getElementById('admin-' + pageId).classList.add('active');
    if (btn) {
        document.querySelectorAll('#adminDashboard .sidebar-item').forEach(i => i.classList.remove('active'));
        btn.classList.add('active');
    }
    if (pageId === 'settings') updateStorageInfo();
}

function showRestPage(pageId, btn) {
    document.querySelectorAll('#restaurantDashboard .page').forEach(p => p.classList.remove('active'));
    document.getElementById('rest-' + pageId).classList.add('active');
    if (btn) {
        document.querySelectorAll('#restaurantDashboard .sidebar-item, #restaurantDashboard .mobile-nav-item').forEach(i => i.classList.remove('active'));
        btn.classList.add('active');
    }
}

// Initialization
loadData();
</script>
</body>
</html>
