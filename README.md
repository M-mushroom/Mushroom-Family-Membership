.family { background: linear-gradient(135deg,#fff0f6,#fff7fa); border: 1px solid #f8bbd0; border-radius: 19px; padding: 16px; }
.family-top { display: flex; align-items: center; gap: 10px; }
.family-icon { width: 43px; height: 43px; border-radius: 14px; background: #fce4ec; color: var(--pink); display: flex; align-items: center; justify-content: center; font-size: 19px; }
.family h3 { color: #ad1457; font-size: 14px; }
.family p { color: #666; font-size: 10px; margin-top: 2px; }
.family-status { margin-top: 13px; display: flex; justify-content: space-between; font-size: 10px; }
.family-bar { height: 6px; background: #f8bbd0; border-radius: 10px; margin-top: 6px; overflow: hidden; }
.family-bar span { display: block; width: 72%; height: 100%; background: var(--pink); }

.activity { background: white; border: 1px solid var(--border); border-radius: 18px; overflow: hidden; }
.activity-item { display: flex; align-items: center; gap: 11px; padding: 13px; border-bottom: 1px solid #eee; animation: popIn 0.3s ease; }
.activity-item:last-child { border-bottom: 0; }
.activity-icon { width: 38px; height: 38px; border-radius: 12px; display: flex; align-items: center; justify-content: center; }
.activity-info { flex: 1; }
.activity-info strong { display: block; font-size: 11px; }
.activity-info small { color: var(--muted); font-size: 9px; }
.amount { font-size: 12px; font-weight: 800; color: var(--green); }

.guarantee { margin-top: 17px; background: linear-gradient(135deg,#e8f5e9,#c8e6c9); border-left: 4px solid var(--green); border-radius: 14px; padding: 13px; }
.guarantee strong { display: block; font-size: 12px; }
.guarantee p { font-size: 9px; color: #444; margin-top: 3px; line-height: 1.6; }

/* =========================
   BOTTOM NAV & MODALS
========================= */
.bottom-nav {
  position: fixed; left: 50%; bottom: 0; transform: translateX(-50%); width: 100%; max-width: 650px;
  background: rgba(255,255,255,.96); backdrop-filter: blur(12px); border-top: 1px solid var(--border);
  display: grid; grid-template-columns: repeat(5,1fr); padding: 8px 5px 10px; z-index: 1000;
}
.nav-item { border: 0; background: none; color: #858585; display: flex; flex-direction: column; align-items: center; gap: 4px; font-size: 9px; font-weight: 600; }
.nav-item i { font-size: 17px; }
.nav-item.active { color: var(--green); }

.modal-overlay {
  position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: rgba(0,0,0,0.6);
  display: flex; align-items: center; justify-content: center; z-index: 3000; opacity: 0; pointer-events: none; transition: opacity 0.3s;
}
.modal-overlay.show { opacity: 1; pointer-events: auto; }
.modal-content { background: white; border-radius: 20px; padding: 20px; width: 90%; max-width: 400px; text-align: center; position: relative; box-shadow: 0 10px 30px rgba(0,0,0,0.2); animation: popIn 0.25s ease; }
.close-modal { position: absolute; top: 12px; right: 15px; font-size: 18px; color: #888; border: 0; background: none; }

.wheel-wrapper { position: relative; width: 220px; height: 220px; margin: 15px auto; }
.wheel-pointer { position: absolute; top: -10px; left: 50%; transform: translateX(-50%); border-left: 10px solid transparent; border-right: 10px solid transparent; border-top: 18px solid var(--red); z-index: 10; }
.wheel-canvas { width: 100%; height: 100%; border-radius: 50%; border: 4px solid var(--orange); transition: transform 3.5s cubic-bezier(0.15, 0.99, 0.18, 1); }

.scratch-container { position: relative; width: 240px; height: 140px; margin: 15px auto; border-radius: 12px; overflow: hidden; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
.scratch-reveal { position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: linear-gradient(135deg, #fff3e0, #ffe0b2); display: flex; flex-direction: column; align-items: center; justify-content: center; }
#scratchCanvas { position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 2; cursor: pointer; }

.audit-box { background: #1a1a1a; color: #00ff66; padding: 10px; border-radius: 8px; font-family: monospace; font-size: 10px; text-align: left; height: 150px; overflow-y: auto; margin-top: 10px; }

.toast {
  position: fixed; left: 50%; bottom: 85px; transform: translate(-50%,20px);
  background: #222; color: white; padding: 11px 16px; border-radius: 12px; font-size: 11px; z-index: 4000;
  opacity: 0; pointer-events: none; transition: .25s; white-space: nowrap;
}
.toast.show { opacity: 1; transform: translate(-50%,0); }

@media(max-width:370px){
  .quick-grid { grid-template-columns: repeat(2,1fr); }
  .member-badge { display: none; }
  .wallet-amount { font-size: 25px; }
}
</style>
</head>

<body>
<div class="app">

  <!-- HEADER -->
  <header class="header">
    <div class="header-top">
      <div class="brand">
        <div class="brand-icon">🍄</div>
        <div>
          <h1>Kundu Care</h1>
          <small>Kundu Mushroom Farm</small>
        </div>
      </div>
      <div class="header-actions">
        <button class="icon-btn" onclick="openModal('adminModal')"><i class="fa-solid fa-user-shield"></i></button>
        <button class="icon-btn" onclick="showToast('🔔 আপনার ২টি নতুন notification আছে')">
          <i class="fa-solid fa-bell"></i>
          <span class="notification-dot"></span>
        </button>
      </div>
    </div>

    <div class="profile">
      <div class="avatar">ব</div>
      <div class="profile-info">
        <h2>বাবাই কুণ্ডু</h2>
        <p>📱 +91 9876543210</p>
      </div>
      <div class="member-badge">⭐ GOLD</div>
    </div>
  </header>

  <main class="main">

    <!-- WALLET SECTION -->
    <section>
      <div class="wallet-card">
        <div class="wallet-title">
          <h3>💰 My Rewards</h3>
          <span onclick="showToast('Wallet history সম্প্রতি আপডেট হয়েছে')">View History →</span>
        </div>

        <div class="wallet-main">
          <div>
            <small>Cashback Balance</small>
            <div class="wallet-amount">₹<span id="walletBalance">120.00</span></div>
          </div>
          <button class="wallet-action" onclick="redirectToShop()" title="Redeem at Shop">
            <i class="fa-solid fa-bag-shopping"></i>
          </button>
        </div>

        <div class="wallet-grid">
          <div class="mini-wallet">
            <div class="mini-wallet-icon icon-orange">🍄</div>
            <small>Mushroom Coins</small>
            <strong><span id="coinBalance">450</span></strong>
          </div>
          <div class="mini-wallet">
            <div class="mini-wallet-icon icon-purple">🔥</div>
            <small>Current Streak</small>
            <strong>5 Days</strong>
          </div>
        </div>
      </div>
    </section>

    <!-- SHOP REDIRECTION BANNER -->
    <section class="shop-banner">
      <div class="shop-banner-info">
        <h4>🛒 Kundu Mushroom Store</h4>
        <p>ব্যালেন্স দিয়ে সরাসরি শপিং করুন</p>
      </div>
      <button class="shop-btn" onclick="redirectToShop()">
        Shop Now <i class="fa-solid fa-arrow-right"></i>
      </button>
    </section>

    <!-- USER GUIDANCE STEP-BY-STEP -->
    <section class="guide-card">
      <div class="section-head">
        <h3>🧭 Rewards Guide</h3>
        <span style="font-size: 10px; color: var(--muted);" id="stepTracker">Step 1 of 3</span>
      </div>
      <div class="guide-steps">
        <div class="guide-step active" id="step1">
          <div class="step-num">১</div>
          <div>প্যাকেটের QR বা Code ইনপুট দিয়ে Purchase Verify করুন।</div>
        </div>
        <div class="guide-step" id="step2">
          <div class="step-num">২</div>
          <div>রিওয়ার্ড হিসেবে Cash, Mushroom Coins বা Spin অণলক করুন।</div>
        </div>
        <div class="guide-step" id="step3">
          <div class="step-num">৩</div>
          <div>Shoopy Store-এ কেনাকাটায় জমানো ব্যালেন্স রিডিম করুন।</div>
        </div>
      </div>
    </section>

    <!-- QUICK ACTIONS -->
    <section class="section">
      <div class="section-head">
        <h3>⚡ Quick Actions</h3>
      </div>
      <div class="quick-grid">
        <button class="quick" onclick="scrollToSection('verify')">
          <div class="quick-icon green-icon"><i class="fa-solid fa-qrcode"></i></div>
          <p>Verify QR</p>
        </button>
        <button class="quick" onclick="openScratchModal()">
          <div class="quick-icon orange-icon"><i class="fa-solid fa-ticket"></i></div>
          <p>Scratch</p>
        </button>
        <button class="quick" onclick="openSpinModal()">
          <div class="quick-icon pink-icon"><i class="fa-solid fa-arrows-spin"></i></div>
          <p>Spin</p>
        </button>
        <button class="quick" onclick="showToast('👥 Referral link কপি হয়েছে!')">
          <div class="quick-icon blue-icon"><i class="fa-solid fa-user-plus"></i></div>
          <p>Refer</p>
        </button>
      </div>
    </section>

    <!-- REWARD CENTER -->
    <section class="section">
      <div class="reward-card">
        <div class="reward-top">
          <div class="reward-icon">🎁</div>
          <div>
            <h3>Reward Center</h3>
            <p>আপনার নতুন reward unlock করার সুযোগ!</p>
          </div>
        </div>
        <div class="reward-buttons">
          <button class="reward-btn white" onclick="openScratchModal()">🎫 Scratch Card</button>
          <button class="reward-btn dark" onclick="openSpinModal()">🎡 Spin & Win</button>
        </div>
      </div>
    </section>

    <!-- PURCHASE VERIFICATION -->
    <section class="section" id="verify">
      <div class="section-head">
        <h3>🔐 Purchase Verification</h3>
      </div>
      <div class="verify-card">
        <div class="verify-head">
          <div class="verify-icon"><i class="fa-solid fa-shield-halved"></i></div>
          <div>
            <h3>QR / Purchase Code</h3>
            <p>প্যাকেটে থাকা unique code দিন</p>
          </div>
        </div>
        <input class="verify-input" id="qrInput" type="text" placeholder="যেমন: KM-7A82X9" autocomplete="off">
        <button class="primary-btn" onclick="verifyPurchase()"><i class="fa-solid fa-check-circle"></i> Verify Purchase</button>
      </div>
    </section>

    <!-- MISSIONS -->
    <section class="section">
      <div class="section-head">
        <h3>🎯 Active Missions</h3>
        <button onclick="showToast('সব Missions ভিউ করা হচ্ছে')">See All</button>
      </div>
      <div class="mission-card">
        <div class="mission">
          <div class="mission-icon">📦</div>
          <div class="mission-content">
            <strong>৩টি Purchase Complete করুন</strong>
            <small>Reward: +50 Mushroom Coins</small>
            <div class="progress"><span style="width:66%"></span></div>
          </div>
          <button class="mission-btn" onclick="claimMission(50)">Claim</button>
        </div>
        <div class="mission">
          <div class="mission-icon">🎁</div>
          <div class="mission-content">
            <strong>৫ Packet Challenge</strong>
            <small>Reward: Spin & Win</small>
            <div class="progress"><span style="width:40%"></span></div>
          </div>
          <button class="mission-btn" onclick="showToast('আরও ৩টি packet প্রয়োজন')">2/5</button>
        </div>
        <div class="mission">
          <div class="mission-icon">🔥</div>
          <div class="mission-content">
            <strong>7 Days Streak</strong>
            <small>Reward: +100 Coins</small>
            <div class="progress"><span style="width:71%"></span></div>
          </div>
          <button class="mission-btn">5/7</button>
        </div>
      </div>
    </section>

    <!-- FAMILY CLUB -->
    <section class="section">
      <div class="family">
        <div class="family-top">
          <div class="family-icon"><i class="fa-solid fa-people-group"></i></div>
          <div>
            <h3>👨‍👩‍👧 Mushroom Family Club</h3>
            <p>Family Purchase থেকে আরও বেশি reward</p>
          </div>
        </div>
        <div class="family-status">
          <span>Monthly Target</span>
          <strong>18 / 25 Packets</strong>
        </div>
        <div class="family-bar"><span></span></div>
        <div style="display:flex; justify-content:space-between; margin-top:9px; font-size:9px; color:#777;">
          <span>🎁 Member Price</span>
          <span>🚚 Free Delivery</span>
          <span>⭐ Special Gift</span>
        </div>
      </div>
    </section>

    <!-- RECENT ACTIVITY -->
    <section class="section">
      <div class="section-head">
        <h3>📜 Recent Activity</h3>
        <button onclick="showToast('Full transaction history আপডেট হচ্ছে')">View All</button>
      </div>
      <div class="activity" id="activityContainer">
        <div class="activity-item">
          <div class="activity-icon green-icon"><i class="fa-solid fa-qrcode"></i></div>
          <div class="activity-info">
            <strong>Purchase Verified</strong>
            <small>আজ • KM-7A82X9</small>
          </div>
          <div class="amount">+₹20</div>
        </div>
      </div>
    </section>

    <!-- GUARANTEE CARD -->
    <div class="guarantee">
      <strong>🍄 100% Fresh Mushroom Guarantee</strong>
      <p>Farm থেকে সরাসরি fresh mushroom। Quality issue হলে নির্দিষ্ট সময়ের মধ্যে replacement অথবা eligible credit পাওয়া যাবে।</p>
    </div>

  </main>
  
