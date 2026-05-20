<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Future | Welcome</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* إعدادات المتصفح الأساسية ودعم التجاوب مع الشاشات */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        /* خلفية الفضاء اللامعة المليئة بالنجوم والمتحركة */
        body {
            background: radial-gradient(circle at center, #080711 0%, #030206 100%);
            color: #ffffff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
            position: relative;
        }

        /* تأثير النجوم المتلألئة في الخلفية */
        body::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background-image: 
                radial-gradient(white, rgba(255,255,255,.2) 2px, transparent 40px),
                radial-gradient(white, rgba(255,255,255,.15) 1px, transparent 30px),
                radial-gradient(white, rgba(255,255,255,.1) 2px, transparent 40px);
            background-size: 550px 550px, 350px 350px, 250px 250px;
            background-position: 0 0, 40px 60px, 130px 270px;
            opacity: 0.4;
            z-index: 0;
            animation: starsMove 100s linear infinite;
        }

        @keyframes starsMove {
            from { background-position: 0 0, 40px 60px, 130px 270px; }
            to { background-position: 550px 1100px, 390px 760px, 1130px 1270px; }
        }

        /* تصميم الوردة السوداء الفضائية */
        .space-black-rose {
            position: relative;
            width: 80px;
            height: 80px;
            background: #030206;
            border-radius: 50%;
            box-shadow: 0 0 25px rgba(0,0,0,0.9), inset 0 0 15px rgba(255,255,255,0.05);
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.03);
        }

        /* بتلات الوردة السوداء الهندسة */
        .petal {
            position: absolute;
            width: 35px;
            height: 35px;
            background: linear-gradient(135deg, #0b0911 0%, #020104 100%);
            border-radius: 50% 0 50% 0;
            border: 1px solid rgba(255, 255, 255, 0.02);
        }
        .p1 { transform: rotate(0deg); }
        .p2 { transform: rotate(45deg); }
        .p3 { transform: rotate(90deg); }
        .p4 { transform: rotate(135deg); }

        .center-core {
            position: absolute;
            width: 15px;
            height: 15px;
            background: #000;
            border-radius: 50%;
            z-index: 5;
            box-shadow: 0 0 10px rgba(0, 188, 212, 0.2);
        }

        /* نجوم المجرة العشوائية المتحركة جوه الوردة */
        .rose-star {
            position: absolute;
            background: #fff;
            border-radius: 50%;
            box-shadow: 0 0 5px #fff;
            z-index: 6;
            animation: roseStarBlink 2s infinite ease-in-out;
        }
        .rs1 { width: 2px; height: 2px; top: 25px; left: 30px; animation-delay: 0.2s; }
        .rs2 { width: 3px; height: 3px; top: 50px; left: 45px; animation-delay: 0.7s; }
        .rs3 { width: 2px; height: 2px; top: 35px; left: 55px; animation-delay: 1.3s; }

        @keyframes roseStarBlink {
            0%, 100% { opacity: 0.1; transform: scale(0.8) translate(0, 0); }
            50% { opacity: 1; transform: scale(1.2) translate(3px, -2px); }
        }

        /* تنسيق شريط التنقل العلوي */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 5%;
            background: rgba(5, 5, 10, 0.75);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            z-index: 10;
            position: relative;
        }

        .nav-logo {
            font-size: 1.6rem;
            font-weight: 800;
            color: #00bcd4;
            text-shadow: 0 0 15px rgba(0, 188, 212, 0.6);
            text-decoration: none;
        }

        .menu-toggle {
            font-size: 1.5rem;
            color: #ffffff;
            cursor: pointer;
            transition: 0.3s;
        }
        .menu-toggle:hover { color: #00bcd4; }

        /* ستايل القائمة الجانبية (Sidebar) بأنيميشن متجاوب */
        .sidebar {
            position: fixed;
            top: 0;
            right: -300px; /* مخفية بره الشاشة */
            width: 280px;
            height: 100%;
            background: #07070c;
            border-left: 1px solid rgba(255, 255, 255, 0.05);
            box-shadow: -10px 0 30px rgba(0,0,0,0.5);
            z-index: 999;
            padding: 30px 20px;
            transition: right 0.4s cubic-bezier(0.1, 1, 0.1, 1); /* أنيميشن ناعم جداً */
        }

        .sidebar.active {
            right: 0; /* تفتح للداخل */
        }

        .sidebar-close {
            font-size: 1.5rem;
            color: #64748b;
            cursor: pointer;
            text-align: left;
            margin-bottom: 30px;
        }
        .sidebar-close:hover { color: #ff3b3b; }

        .sidebar-item {
            padding: 15px 10px;
            color: #94a3b8;
            font-weight: 600;
            cursor: pointer;
            border-radius: 8px;
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 10px;
            transition: 0.3s;
            flex-direction: row;
            flex-wrap: wrap;
        }
        .sidebar-item:hover { background: rgba(255,255,255,0.02); color: #fff; }

        /* قائمة المطورين المنسدلة داخل الـ Sidebar */
        .sidebar-dropdown {
            width: 100%;
            background: rgba(0,0,0,0.3);
            border-radius: 8px;
            padding: 15px;
            margin-top: 10px;
            display: none;
            text-align: right;
            direction: rtl;
        }

        .dropdown-title { color: #00bcd4; font-weight: bold; font-size: 0.95rem; }
        .dropdown-subtitle { font-size: 0.75rem; color: #64748b; margin-bottom: 10px; }
        .founder-name { color: #ff3b3b; text-shadow: 0 0 8px rgba(255, 59, 59, 0.3); margin: 6px 0; font-size: 0.85rem; }

        /* أزرار اللغات الجديدة (جنب بعض) */
        .lang-section {
            margin-top: 40px;
            display: flex;
            gap: 10px;
            border-top: 1px solid rgba(255,255,255,0.05);
            padding-top: 25px;
        }

        .lang-btn-box {
            flex: 1;
            background: rgba(255,255,255,0.03);
            border: 1px solid rgba(255,255,255,0.08);
            color: #94a3b8;
            padding: 10px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 0.85rem;
            font-weight: bold;
            transition: 0.3s;
        }
        .lang-btn-box:hover, .lang-btn-box.active {
            background: #00bcd4;
            color: #000;
            border-color: #00bcd4;
            box-shadow: 0 0 10px rgba(0, 188, 212, 0.3);
        }

        /* النظام الشمسي الذي يدور حول الوردة */
        .solar-orbit {
            position: absolute;
            width: 100%;
            height: 100%;
            border: 1px dashed rgba(0, 188, 212, 0.3);
            border-radius: 50%;
            animation: orbitSpin 12s linear infinite;
        }

        /* الكوكب الذي يدور في النظام */
        .solar-orbit::after {
            content: '';
            position: absolute;
            top: 10px;
            left: 50%;
            width: 12px;
            height: 12px;
            background: #00bcd4;
            border-radius: 50%;
            box-shadow: 0 0 10px #00bcd4;
        }

        @keyframes orbitSpin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* الوردة السوداء الفضائية ذات النقاط والنجوم اللامعة في قلب النظام */
        .black-rose-icon {
            width: 80px;
            height: 80px;
            background: radial-gradient(circle, #1a1525 0%, #050408 100%);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 2.5rem;
            color: #111;
            border: 2px solid rgba(255,255,255,0.05);
            text-shadow: 0 0 5px rgba(255,255,255,0.1);
            position: relative;
            box-shadow: 0 0 25px rgba(0,0,0,0.9);
        }

        /* بريق متلألئ خفيف داخل الوردة */
        .black-rose-icon::before {
            content: '✨';
            position: absolute;
            font-size: 0.8rem;
            top: 15px;
            right: 15px;
            animation: pulse 2s infinite alternate;
        }

        @keyframes pulse {
            0% { opacity: 0.3; }
            100% { opacity: 1; }
        }

        /* قسم الإحصائيات (السيرفرات والسبورت) */
        .stats-container {
            display: flex;
            justify-content: space-between;
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid rgba(255, 255, 255, 0.05);
            padding: 15px;
            border-radius: 14px;
            margin-bottom: 25px;
        }

        .stat-box {
            flex: 1;
            text-align: center;
        }

        .stat-box:first-child {
            border-right: 1px solid rgba(255,255,255,0.05);
        }

        .stat-num {
            font-size: 1.3rem;
            font-weight: 800;
            color: #34d399;
        }

        .stat-label {
            font-size: 0.8rem;
            color: #64748b;
            margin-top: 2px;
            text-transform: uppercase;
        }

        /* أزرار العمليات الأساسية */
        .action-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            width: 100%;
            padding: 14px;
            border-radius: 12px;
            font-size: 1.05rem;
            font-weight: 700;
            text-decoration: none;
            cursor: pointer;
            transition: 0.3s;
            margin-bottom: 12px;
            border: none;
        }

        .btn-start {
            background: #00bcd4;
            color: #000;
            box-shadow: 0 4px 20px rgba(0, 188, 212, 0.3);
        }

        .btn-start:hover {
            background: #00e5ff;
            transform: translateY(-2px);
        }

        /* زر الديسكورد - تعديل الرابط هنا سهل جداً */
        .btn-discord {
            background: #5865F2;
            color: #fff;
            box-shadow: 0 4px 20px rgba(88, 101, 242, 0.2);
        }

        .btn-discord:hover {
            background: #4752c4;
            transform: translateY(-2px);
        }

        /* تعديل للمنطقة التجريبية والمحاكاة المنظرية التي طلبتها */
        .custom-text-zone {
            margin: 15px 0;
            font-size: 0.85rem;
            color: #4b5563;
        }

        /* شاشات التسجيل والـ Modals التفاعلية */
        .auth-overlay {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(3, 2, 6, 0.95);
            z-index: 1000;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            pointer-events: none;
            transition: 0.3s ease;
        }

        .auth-overlay.active {
            opacity: 1;
            pointer-events: auto;
        }

        .auth-modal {
            background: #08080d;
            border: 1px solid rgba(255, 255, 255, 0.08);
            border-radius: 20px;
            padding: 35px;
            max-width: 440px;
            width: 90%;
            position: relative;
        }

        .close-btn {
            position: absolute;
            top: 15px; right: 20px;
            font-size: 1.3rem;
            color: #64748b;
            cursor: pointer;
        }

        .auth-title {
            font-size: 1.6rem;
            font-weight: 700;
            margin-bottom: 25px;
            text-align: center;
            color: #00bcd4;
        }

        .input-group {
            margin-bottom: 18px;
        }

        .input-group label {
            display: block;
            font-size: 0.85rem;
            color: #94a3b8;
            margin-bottom: 6px;
        }

        .input-group input {
            width: 100%;
            padding: 12px;
            background: rgba(255,255,255,0.03);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 8px;
            color: white;
            outline: none;
            transition: 0.3s;
        }

        .input-group input:focus { border-color: #00bcd4; }

        /* أداة الكابتشا (أنا لست روبوت محاكاة) */
        .captcha-box {
            background: rgba(255,255,255,0.02);
            border: 1px solid rgba(255,255,255,0.08);
            padding: 12px;
            border-radius: 8px;
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 20px;
        }

        .captcha-box input[type="checkbox"] {
            width: 20px;
            height: 20px;
            cursor: pointer;
        }

        .switch-auth-mode {
            text-align: center;
            margin-top: 15px;
            font-size: 0.85rem;
            color: #64748b;
        }

        .switch-auth-mode span {
            color: #00bcd4;
            cursor: pointer;
            font-weight: bold;
        }

        .oauth-divider {
            display: flex;
            align-items: center;
            text-align: center;
            color: #4b5563;
            margin: 20px 0;
            font-size: 0.8rem;
        }
        .oauth-divider::before, .oauth-divider::after {
            content: ''; flex: 1; border-bottom: 1px solid rgba(255,255,255,0.05);
        }
        .oauth-divider:not(:empty)::before { margin-right: .25em; }
        .oauth-divider:not(:empty)::after { margin-left: .25em; }

        .oauth-buttons {
            display: flex;
            gap: 10px;
        }

        .oauth-btn {
            flex: 1;
            padding: 10px;
            border-radius: 8px;
            border: none;
            cursor: pointer;
            font-weight: 600;
            font-size: 0.85rem;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        /* توافق تام مع الموبايل */
        @media (max-width: 768px) {
            nav { padding: 15px 20px; }
            .nav-links { gap: 15px; }
            .main-card { padding: 25px 20px; }
        }
    </style>
</head>
<body>

    <nav>
        <a href="#" class="nav-logo">Host The Future</a>
        
        <div class="menu-toggle" onclick="toggleSidebar(true)">
            <i class="fa-solid fa-bars"></i>
        </div>
    </nav>

    <div class="sidebar" id="sidebarMenu">
        <div class="sidebar-close" onclick="toggleSidebar(false)">
            <i class="fa-solid fa-xmark"></i>
        </div>

        <div class="sidebar-content">
            <div class="sidebar-item" onclick="toggleDevelopers()">
                <i class="fa-solid fa-code"></i> Developers <i class="fa-solid fa-chevron-down" style="font-size: 0.8rem; margin-left: auto;"></i>
                <div class="sidebar-dropdown" id="devDropdown">
                    <div class="dropdown-title">مؤسسين (The Future)</div>
                    <div class="dropdown-subtitle">(المؤسسين من أصول عربيه)</div>
                    <div class="founder-name">المؤسس: مالك</div>
                    <div class="founder-name">المؤسس: وسيم</div>
                </div>
            </div>

            <div class="sidebar-item" onclick="alert('ادوات بايثون جافا بمبالغ معقوله')">
                <i class="fa-solid fa-screwdriver-wrench"></i> Tools
            </div>

            <div class="lang-section">
                <button class="lang-btn-box active" onclick="changeLang('en', this)">🇺🇸 English</button>
                <button class="lang-btn-box" onclick="changeLang('ar', this)">عربيه 🇸🇦</button>
            </div>
        </div>
    </div>

    <div class="main-wrapper">
        <div class="main-card">
            
            <div class="universe-zone">
                <div class="solar-orbit"></div>
                <div class="space-black-rose">
                    <div class="petal p1"></div>
                    <div class="petal p2"></div>
                    <div class="petal p3"></div>
                    <div class="petal p4"></div>
                    <div class="center-core"></div>
                    <div class="rose-star rs1"></div>
                    <div class="rose-star rs2"></div>
                    <div class="rose-star rs3"></div>
                </div>
            </div>

            <h2 style="color: #fff; margin-bottom: 10px; font-weight: 800;">Cloud Infrastructure</h2>
            <p style="color: #64748b; font-size: 0.9rem; margin-bottom: 20px;">Deploy high performance environments instantly in the cloud network.</p>

            <div class="stats-container">
                <div class="stat-box">
                    <div class="stat-num">Free</div>
                    <div class="stat-label">Server</div>
                </div>
                <div class="stat-box">
                    <div class="stat-num">24/7</div>
                    <div class="stat-label">Sport</div>
                </div>
            </div>

            <div class="custom-text-zone">
                </div>

            <button class="action-btn btn-start" onclick="openAuthModal('login')">
                <i class="fa-solid : fa-bolt"></i> Start
            </button>

            <a href="https://discord.gg/YCXRJRztRb" target="_blank" class="action-btn btn-discord">
                <i class="fa-brands : fa-discord"></i> Join Discord
            </a>

        </div>
    </div>

    <div class="auth-overlay" id="authOverlay">
        
        <div class="auth-modal" id="loginModal">
            <span class="close-btn" onclick="closeAuthModal()">&times;</span>
            <div class="auth-title">Login</div>
            <form onsubmit="handleLoginSubmit(event)">
                <div class="input-group">
                    <label>Email Address</label>
                    <input type="email" required placeholder="name@example.com">
                </div>
                <div class="input-group">
                    <label>Password</label>
                    <input type="password" required placeholder="••••••••">
                </div>

                <div class="captcha-box">
                    <input type="checkbox" id="captchaCheck" required>
                    <label for="captchaCheck" style="font-size: 0.85rem; color: #94a3b8; cursor: pointer;">I am not a robot</label>
                    <i class="fa-solid : fa-shield-halved" style="color: #34d399; margin-left: auto;"></i>
                </div>

                <button type="submit" class="action-btn btn-start" style="margin-bottom:0;">Login</button>
            </form>

            <div class="oauth-divider">Or Sign In With</div>
            <div class="oauth-buttons">
                <button class="oauth-btn" style="background:#fff; color:#000;" onclick="alert('جاري الاتصال بـ Google...')"><i class="fa-brands : fa-google"></i> Google</button>
                <button class="oauth-btn" style="background:#5865F2; color:#fff;" onclick="alert('جاري الاتصال بـ Discord...')"><i class="fa-brands : fa-discord"></i> Discord</button>
            </div>

            <div class="switch-auth-mode">Don't have an account? <span onclick="openAuthModal('register')">New account</span></div>
        </div>

        <div class="auth-modal" id="registerModal" style="display:none;">
            <span class="close-btn" onclick="closeAuthModal()">&times;</span>
            <div class="auth-title">Create New Account</div>
            <form onsubmit="handleRegisterSubmit(event)">
                <div class="input-group">
                    <label>Username</label>
                    <input type="text" id="regUser" required placeholder="e.g. enzo_dev">
                </div>
                <div class="input-group">
                    <label>Email Address</label>
                    <input type="email" id="regEmail" required placeholder="yourname@gmail.com">
                </div>
                <div class="input-group">
                    <label>Password</label>
                    <input type="password" required placeholder="••••••••">
                </div>
                <div class="input-group">
                    <label>Confirm Password</label>
                    <input type="password" required placeholder="••••••••">
                </div>

                <button type="submit" class="action-btn btn-start" style="margin-bottom:0; background:#34d399; color:#000; box-shadow: 0 4px 20px rgba(52, 211, 153, 0.2);">Verify Email</button>
            </form>
            <div class="switch-auth-mode">Already have an account? <span onclick="openAuthModal('login')">Login</span></div>
        </div>

    </div>

    <script>
        const overlay = document.getElementById('authOverlay');
        const loginModal = document.getElementById('loginModal');
        const registerModal = document.getElementById('registerModal');

        // فتح نوافذ الحسابات
        function openAuthModal(mode) {
            overlay.classList.add('active');
            if(mode === 'login') {
                loginModal.style.display = 'block';
                registerModal.style.display = 'none';
            } else {
                loginModal.style.display = 'none';
                registerModal.style.display = 'block';
            }
        }

        // إغلاق النوافذ
        function closeAuthModal() {
            overlay.classList.remove('active');
        }

        // فتح وإغلاق القائمة الجانبية
        function toggleSidebar(open) {
            const sidebar = document.getElementById('sidebarMenu');
            if(open) sidebar.classList.add('active');
            else sidebar.classList.remove('active');
        }

        // فتح وإغلاق المطورين داخل القائمة الجانبية
        function toggleDevelopers() {
            const devDropdown = document.getElementById('devDropdown');
            if(devDropdown.style.display === 'block') {
                devDropdown.style.display = 'none';
            } else {
                devDropdown.style.display = 'block';
            }
        }

        // تحديث دالة تغيير اللغة لتغيير حالة الأزرار النشطة
        function changeLang(lang, buttonElement) {
            // إزالة الحالة النشطة من كل أزرار اللغات
            document.querySelectorAll('.lang-btn-box').forEach(btn => btn.classList.remove('active'));
            // إضافة الحالة النشطة للزر المضغوط
            buttonElement.classList.add('active');
            
            if(lang === 'en') {
                document.documentElement.dir = 'ltr';
                document.documentElement.lang = 'en';
                // بقية نصوص الترجمة هنا...
            } else {
                document.documentElement.dir = 'rtl';
                document.documentElement.lang = 'ar';
                // بقية نصوص الترجمة العربية هنا...
            }
        }

        // محاكاة إرسال رابط التفعيل للإيميل
        function handleRegisterSubmit(e) {
            e.preventDefault();
            const email = document.getElementById('regEmail').value;
            alert(`تم إرسال رابط التحقق بنجاح إلى البريد: ${email}\n\nبرجاء فتح الرابط في بريدك لتأكيد حسابك، ثم ارجع للموقع مجدداً لتسجيل الدخول!`);
            openAuthModal('login');
        }

        // تسجيل الدخول والتحويل للوحة التحكم المفترضة بعد التحقق
        function handleLoginSubmit(e) {
            e.preventDefault();
            alert('تم تسجيل الدخول بنجاح! جاري تحويلك إلى لوحة التحكم وتحميل السيرفر السحابي...');
            // هنا السيستم بيحولك فوراً لصفحة اللوحة والعداد اللي عملناها سوا
            window.location.href = 'dashboard.html'; 
        }
    </script>
</body>
</html>
