<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Host The Future | Welcome</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        /* خلفية فضاء حقيقية بنجوم متحركة وسديم بنفسجي لامع وخفيف */
        body {
            background: radial-gradient(circle at 30% 20%, #120924 0%, #040308 60%), 
                        radial-gradient(circle at 80% 70%, #180b30 0%, #030206 100%);
            color: #ffffff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
            position: relative;
        }

        /* تأثير النجوم المتلألئة المضيئة */
        body::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background-image: 
                radial-gradient(white, rgba(255,255,255,.2) 1.5px, transparent 30px),
                radial-gradient(white, rgba(255,255,255,.15) 1px, transparent 20px);
            background-size: 350px 350px, 250px 250px;
            opacity: 0.4;
            z-index: 0;
            animation: starsMove 120s linear infinite;
        }

        @keyframes starsMove {
            from { background-position: 0 0, 40px 60px; }
            to { background-position: 350px 700px, 290px 460px; }
        }

        /* شريط التنقل العلوي */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 5%;
            background: rgba(4, 3, 8, 0.75);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.04);
            z-index: 10;
        }

        .nav-logo {
            font-size: 1.4rem;
            font-weight: 800;
            color: #00bcd4;
            text-shadow: 0 0 15px rgba(0, 188, 212, 0.5);
            text-decoration: none;
        }

        .menu-toggle {
            font-size: 1.4rem;
            color: #ffffff;
            cursor: pointer;
            transition: 0.3s;
            padding: 5px;
        }

        /* القائمة الجانبية المرنة (تتطابق مع لغة الموقع وتمنع التعليق) */
        .sidebar {
            position: fixed;
            top: 0;
            width: 280px;
            height: 100%;
            background: #050408;
            box-shadow: 0 0 30px rgba(0,0,0,0.7);
            z-index: 999;
            padding: 25px 20px;
            transition: transform 0.4s cubic-bezier(0.1, 1, 0.1, 1);
        }

        /* التحكم في اتجاه فتح القائمة حسب اللغة */
        html[dir="ltr"] .sidebar { right: 0; transform: translateX(300px); border-left: 1px solid rgba(255, 255, 255, 0.05); }
        html[dir="rtl"] .sidebar { left: 0; transform: translateX(-300px); border-right: 1px solid rgba(255, 255, 255, 0.05); }
        
        html[dir="ltr"] .sidebar.active { transform: translateX(0); }
        html[dir="rtl"] .sidebar.active { transform: translateX(0); }

        .sidebar-close {
            font-size: 1.4rem;
            color: #64748b;
            cursor: pointer;
            margin-bottom: 25px;
        }
        html[dir="ltr"] .sidebar-close { text-align: left; }
        html[dir="rtl"] .sidebar-close { text-align: right; }

        .sidebar-item {
            padding: 12px 10px;
            color: #94a3b8;
            font-weight: 600;
            cursor: pointer;
            border-radius: 8px;
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 8px;
            transition: 0.3s;
        }
        .sidebar-item:hover { background: rgba(255,255,255,0.03); color: #fff; }

        .sidebar-dropdown {
            width: 100%;
            background: rgba(0,0,0,0.4);
            border-radius: 8px;
            padding: 12px;
            margin-top: 8px;
            display: none;
        }
        html[dir="ltr"] .sidebar-dropdown { text-align: left; direction: ltr; }
        html[dir="rtl"] .sidebar-dropdown { text-align: right; direction: rtl; }

        .dropdown-title { color: #00bcd4; font-weight: bold; font-size: 0.9rem; }
        .dropdown-subtitle { font-size: 0.75rem; color: #64748b; margin-bottom: 8px; }
        .founder-name { color: #ff3b3b; text-shadow: 0 0 8px rgba(255, 59, 59, 0.3); margin: 4px 0; font-size: 0.85rem; }

        /* أزرار اللغات جنب بعضها */
        .lang-section {
            margin-top: 30px;
            display: flex;
            gap: 10px;
            border-top: 1px solid rgba(255,255,255,0.05);
            padding-top: 20px;
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
            text-align: center;
            transition: 0.3s;
        }
        .lang-btn-box.active {
            background: #00bcd4;
            color: #000;
            border-color: #00bcd4;
            box-shadow: 0 0 10px rgba(0, 188, 212, 0.3);
        }

        /* كرت المحتوى الرئيسي متناسق الحجم */
        .main-wrapper {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            z-index: 5;
        }

        .main-card {
            background: rgba(8, 7, 12, 0.8);
            border: 1px solid rgba(255, 255, 255, 0.04);
            border-radius: 20px;
            padding: 30px;
            max-width: 420px;
            width: 100%;
            text-align: center;
            box-shadow: 0 20px 50px rgba(0,0,0,0.6);
            backdrop-filter: blur(15px);
        }

        /* تم تصغير منطقة الوردة والنظام الشمسي لتناسب الهواتف تماماً */
        .universe-zone {
            position: relative;
            width: 110px;
            height: 110px;
            margin: 0 auto 20px auto;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .solar-orbit {
            position: absolute;
            width: 100%;
            height: 100%;
            border: 1px dashed rgba(0, 188, 212, 0.25);
            border-radius: 50%;
            animation: orbitSpin 15s linear infinite;
        }

        .solar-orbit::after {
            content: '';
            position: absolute;
            top: 5px;
            left: 50%;
            width: 8px;
            height: 8px;
            background: #00bcd4;
            border-radius: 50%;
            box-shadow: 0 0 8px #00bcd4;
        }

        @keyframes orbitSpin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* الوردة الفضائية المصغرة والمحاطة بالنجوم الداخلية */
        .space-black-rose {
            position: relative;
            width: 65px;
            height: 65px;
            background: #020104;
            border-radius: 50%;
            box-shadow: 0 0 20px rgba(0,0,0,0.8);
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.03);
        }

        .petal {
            position: absolute;
            width: 28px;
            height: 28px;
            background: linear-gradient(135deg, #09070f 0%, #010003 100%);
            border-radius: 50% 0 50% 0;
            border: 1px solid rgba(255, 255, 255, 0.01);
        }
        .p1 { transform: rotate(0deg); }
        .p2 { transform: rotate(45deg); }
        .p3 { transform: rotate(90deg); }
        .p4 { transform: rotate(135deg); }

        .center-core {
            position: absolute;
            width: 12px;
            height: 12px;
            background: #000;
            border-radius: 50%;
            z-index: 5;
        }

        .rose-star {
            position: absolute;
            background: #fff;
            border-radius: 50%;
            box-shadow: 0 0 4px #fff;
            z-index: 6;
            animation: roseStarBlink 2s infinite ease-in-out;
        }
        .rs1 { width: 2px; height: 2px; top: 18px; left: 22px; animation-delay: 0.2s; }
        .rs2 { width: 2px; height: 2px; top: 42px; left: 38px; animation-delay: 0.7s; }
        .rs3 { width: 1.5px; height: 1.5px; top: 28px; left: 45px; animation-delay: 1.3s; }

        @keyframes roseStarBlink {
            0%, 100% { opacity: 0.2; transform: scale(0.8); }
            50% { opacity: 1; transform: scale(1.2); }
        }

        /* صندوق الإحصائيات المعدل */
        .stats-container {
            display: flex;
            justify-content: space-between;
            background: rgba(255, 255, 255, 0.01);
            border: 1px solid rgba(255, 255, 255, 0.04);
            padding: 12px;
            border-radius: 12px;
            margin-bottom: 20px;
        }

        .stat-box { flex: 1; text-align: center; }
        html[dir="ltr"] .stat-box:first-child { border-right: 1px solid rgba(255,255,255,0.04); }
        html[dir="rtl"] .stat-box:first-child { border-left: 1px solid rgba(255,255,255,0.04); }

        .stat-num { font-size: 1.2rem; font-weight: 800; color: #34d399; }
        .stat-label { font-size: 0.75rem; color: #64748b; margin-top: 2px; }

        /* الأزرار */
        .action-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            width: 100%;
            padding: 12px;
            border-radius: 10px;
            font-size: 1rem;
            font-weight: 700;
            text-decoration: none;
            cursor: pointer;
            transition: 0.3s;
            margin-bottom: 10px;
            border: none;
        }

        .btn-start { background: #00bcd4; color: #000; box-shadow: 0 4px 15px rgba(0, 188, 212, 0.2); }
        .btn-start:hover { background: #00e5ff; transform: translateY(-1px); }
        .btn-discord { background: #5865F2; color: #fff; }
        .btn-discord:hover { background: #4752c4; transform: translateY(-1px); }

        /* النوافذ المنبثقة (Auth Modals) */
        .auth-overlay {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(3, 2, 6, 0.94);
            z-index: 1000;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            pointer-events: none;
            transition: 0.3s ease;
        }

        .auth-overlay.active { opacity: 1; pointer-events: auto; }

        .auth-modal {
            background: #06050a;
            border: 1px solid rgba(255, 255, 255, 0.06);
            border-radius: 16px;
            padding: 30px;
            max-width: 400px;
            width: 90%;
            position: relative;
        }

        .close-btn { position: absolute; top: 12px; right: 18px; font-size: 1.2rem; color: #64748b; cursor: pointer; }
        .auth-title { font-size: 1.4rem; font-weight: 700; margin-bottom: 20px; text-align: center; color: #00bcd4; }

        .input-group { margin-bottom: 15px; text-align: left; }
        html[dir="rtl"] .input-group { text-align: right; }
        .input-group label { display: block; font-size: 0.8rem; color: #94a3b8; margin-bottom: 5px; }
        
        .input-group input {
            width: 100%;
            padding: 10px;
            background: rgba(255,255,255,0.02);
            border: 1px solid rgba(255,255,255,0.08);
            border-radius: 6px;
            color: white;
            outline: none;
        }
        .input-group input:focus { border-color: #00bcd4; }

        .captcha-box {
            background: rgba(255,255,255,0.01);
            border: 1px solid rgba(255,255,255,0.06);
            padding: 10px;
            border-radius: 6px;
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 15px;
        }

        .switch-auth-mode { text-align: center; margin-top: 12px; font-size: 0.8rem; color: #64748b; }
        .switch-auth-mode span { color: #00bcd4; cursor: pointer; font-weight: bold; }
        
        .oauth-divider { display: flex; align-items: center; text-align: center; color: #4b5563; margin: 15px 0; font-size: 0.75rem; }
        .oauth-divider::before, .oauth-divider::after { content: ''; flex: 1; border-bottom: 1px solid rgba(255,255,255,0.05); }
        html[dir="ltr"] .oauth-divider::before { margin-right: .5em; } html[dir="ltr"] .oauth-divider::after { margin-left: .5em; }
        html[dir="rtl"] .oauth-divider::before { margin-left: .5em; } html[dir="rtl"] .oauth-divider::after { margin-right: .5em; }

        .oauth-buttons { display: flex; gap: 10px; }
        .oauth-btn { flex: 1; padding: 10px; border-radius: 6px; border: none; cursor: pointer; font-weight: 600; font-size: 0.8rem; display: inline-flex; align-items: center; justify-content: center; gap: 6px; }
    </style>
        <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
    <script type="text/javascript">
        (function() {
            // ربط الحساب بمفتاحك العام
            emailjs.init("LSXuDqmuHCy7-zx1w");
        })();
    </script>
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
                <i class="fa-solid fa-code"></i> 
                <span>Developers</span> 
                <i class="fa-solid fa-chevron-down" style="font-size: 0.7rem; margin-left: auto; margin-right: auto;"></i>
            </div>
            
            <div class="sidebar-dropdown" id="devDropdown">
                <div class="dropdown-title">مؤسسين (The Future)</div>
                <div class="dropdown-subtitle">(المؤسسين من أصول عربيه)</div>
                <div class="founder-name">المؤسس: مالك</div>
                <div class="founder-name">المؤسس: وسيم</div>
            </div>

            <div class="sidebar-item" onclick="alert('SOON')">
                <i class="fa-solid fa-screwdriver-wrench"></i> <span>Tools</span>
            </div>

            <div class="lang-section">
                <button class="lang-btn-box" id="enBtn" onclick="setLanguage('en')">🇺🇸 English</button>
                <button class="lang-btn-box" id="arBtn" onclick="setLanguage('ar')">عربيه 🇸🇦</button>
            </div>
        </div>
    </div>

    <div class="main-wrapper">
        <div class="main-card">
            <div class="universe-zone">
                <div class="solar-orbit"></div>
                <div class="space-black-rose">
                    <div class="petal p1"></div><div class="petal p2"></div><div class="petal p3"></div><div class="petal p4"></div>
                    <div class="center-core"></div>
                    <div class="rose-star rs1"></div><div class="rose-star rs2"></div><div class="rose-star rs3"></div>
                </div>
            </div>

            <h2 id="cardTitle" style="color: #fff; margin-bottom: 8px; font-weight: 800;">Cloud Infrastructure</h2>
            <p id="cardDesc" style="color: #64748b; font-size: 0.85rem; margin-bottom: 20px;">Deploy high performance environments instantly in the cloud network.</p>

            <div class="stats-container">
                <div class="stat-box">
                    <div class="stat-num">Free</div>
                    <div class="stat-label" id="lblServer">Server</div>
                </div>
                <div class="stat-box">
                    <div class="stat-num">24/7</div>
                    <div class="stat-label" id="lblSport">Sport</div>
                </div>
            </div>

            <button class="action-btn btn-start" id="btnStartText" onclick="openAuthModal('login')">
                <i class="fa-solid fa-bolt"></i> Start
            </button>

            <a href="https://discord.gg/YCXRJRztRb" target="_blank" class="action-btn btn-discord" id="btnDiscordText">
                <i class="fa-brands fa-discord"></i> Join Discord
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
                    <label for="captchaCheck" style="font-size: 0.8rem; color: #94a3b8; cursor: pointer;">I am not a robot</label>
                    <i class="fa-solid fa-shield-halved" style="color: #34d399; margin-left: auto;"></i>
                </div>
                <button type="submit" class="action-btn btn-start" style="margin-bottom:0;">Login</button>
            </form>
            <div class="oauth-divider">Or Sign In With</div>
            <div class="oauth-buttons">
                <button class="oauth-btn" style="background:#fff; color:#000;" onclick="alert('Connecting to Google...')"><i class="fa-brands fa-google"></i> Google</button>
                <button class="oauth-btn" style="background:#5865F2; color:#fff;" onclick="alert('Connecting to Discord...')"><i class="fa-brands fa-discord"></i> Discord</button>
            </div>
            <div class="switch-auth-mode">Don't have an account? <span onclick="openAuthModal('register')">New account</span></div>
        </div>

        <div class="auth-modal" id="registerModal" style="display:none;">
            <span class="close-btn" onclick="closeAuthModal()">&times;</span>
            <div class="auth-title">Create New Account</div>
            <form onsubmit="handleRegisterSubmit(event)">
                <div class="input-group">
                    <label>Username</label>
                    <input type="text" required placeholder="e.g. enzo_dev">
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
                <button type="submit" class="action-btn btn-start" style="margin-bottom:0; background:#34d399; color:#000;">Verify Email</button>
            </form>
            <div class="switch-auth-mode">Already have an account? <span onclick="openAuthModal('login')">Login</span></div>
        </div>
    </div>

    <script>
        // حفظ واسترجاع اللغة المفضلة من ذاكرة المتصفح لمنع التعليق
        const savedLang = localStorage.getItem('siteLang') || 'en';
        applyLanguageStyles(savedLang);

        function applyLanguageStyles(lang) {
            document.documentElement.lang = lang;
            if (lang === 'ar') {
                document.documentElement.dir = 'rtl';
                document.getElementById('arBtn').classList.add('active');
                document.getElementById('enBtn').classList.remove('active');
                // ترجمة العناصر الأساسية للواجهة
                document.getElementById('cardTitle').innerText = "البنية التحتية السحابية";
                document.getElementById('cardDesc').innerText = "قم بنشر بيئات عالية الأداء فوراً داخل الشبكة السحابية.";
                document.getElementById('lblServer').innerText = "سيرفر";
                document.getElementById('lblSport').innerText = "دعم";
                document.getElementById('btnStartText').innerHTML = '<i class="fa-solid fa-bolt"></i> ابدأ الآن';
                document.getElementById('btnDiscordText').innerHTML = '<i class="fa-brands fa-discord"></i> دخول الديسكورد';
            } else {
                document.documentElement.dir = 'ltr';
                document.getElementById('enBtn').classList.add('active');
                document.getElementById('arBtn').classList.remove('active');
            }
        }

        function setLanguage(lang) {
            localStorage.setItem('siteLang', lang);
            // عمل ريست وإعادة تحميل فوري للموقع لتجنب التعليق وتطبيق الترجمة بشكل سليم مية بالمية
            window.location.reload();
        }

        function toggleSidebar(open) {
            const sidebar = document.getElementById('sidebarMenu');
            if(open) sidebar.classList.add('active');
            else sidebar.classList.remove('active');
        }

        function toggleDevelopers() {
            const devDropdown = document.getElementById('devDropdown');
            devDropdown.style.display = devDropdown.style.display === 'block' ? 'none' : 'block';
        }

        function openAuthModal(mode) {
            document.getElementById('authOverlay').classList.add('active');
            if(mode === 'login') {
                document.getElementById('loginModal').style.display = 'block';
                document.getElementById('registerModal').style.display = 'none';
            } else {
                document.getElementById('loginModal').style.display = 'none';
                document.getElementById('registerModal').style.display = 'block';
            }
        }

        function closeAuthModal() { document.getElementById('authOverlay').classList.remove('active'); }

        function handleRegisterSubmit(e) {
            e.preventDefault();
            
            // جلب الإيميل واسم المستخدم اللي الشخص كتبهم
            const email = document.getElementById('regEmail').value;
            const username = document.getElementById('regUser') ? document.getElementById('regUser').value : 'User';
            
            // تغيير نص الزرار عشان اليوزر يعرف إنه جاري الإرسال
            const submitBtn = e.target.querySelector('button[type="submit"]');
            const originalText = submitBtn.innerText;
            submitBtn.innerText = "Sending...";
            submitBtn.disabled = true;

            // تجهيز البيانات المتطابقة مع الـ Template بتاعك
            const templateParams = {
                user_email: email,
                user_name: username,
                reply_to: "support@thefuture.com"
            };

            // إرسال الإيميل الحقيقي فوراً عبر السيرفر
            emailjs.send("service_z01ptyg", "template_mbb5nh5", templateParams)
                .then(function(response) {
                    alert(`✅ تم إرسال رابط التحقق بنجاح إلى البريد: ${email}\n\nبرجاء فتح بريدك لتفعيل الحساب، ثم عد للموقع لتسجيل الدخول!`);
                    submitBtn.innerText = originalText;
                    submitBtn.disabled = false;
                    openAuthModal('login'); // تحويله لصفحة تسجيل الدخول
                }, function(error) {
                    alert("❌ عذراً، حدث خطأ أثناء إرسال الإيميل. تأكد من إعدادات الحساب.");
                    console.log("EmailJS Error:", error);
                    submitBtn.innerText = originalText;
                    submitBtn.disabled = false;
                });
        }

                function handleLoginSubmit(e) {
            e.preventDefault();
            
            // التشيك السحري: هل الشخص ده دخل على رابط الإيميل وفعل حسابه؟
            const isVerified = localStorage.getItem('accountVerified');

            if (isVerified === 'true') {
                alert('✅ تم التحقق من حسابك بنجاح! جاري تحويلك إلى لوحة التحكم وتحميل السيرفر...');
                // تحويله فوراً للـ Dashboard طالما الحساب متفعل ومثبت من نفس الجهاز
                window.location.href = 'dashboard.html'; 
            } else {
                // لو حاول يسجل من غير ما يفتح الرابط اللي في الإيميل
                alert('❌ عذراً! هذا الحساب غير مفعّل. يجب عليك الضغط على رابط التفعيل المرسل إلى بريدك الإلكتروني أولاً لتتمكن من تسجيل الدخول.');
            }
        }

        function handleLoginSubmit(e) {
            e.preventDefault();
            alert('تم تسجيل الدخول بنجاح! جاري تحويلك للوحة التحكم...');
            window.location.href = 'dashboard.html';
        }
    </script>
</body>
</html>
