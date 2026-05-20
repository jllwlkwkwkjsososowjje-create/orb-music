<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kerit Cloud | Welcome</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* تهيئة أساسية ودعم الترجمة */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        /* خلفية سوداء لامعة متغيرة ومتحركة */
        body {
            background: linear-gradient(135deg, #050508 0%, #0a0f24 40%, #030305 70%, #0d1330 100%);
            background-size: 400% 400%;
            animation: glossyBg 15s ease infinite;
            color: #ffffff;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow-x: hidden;
        }

        @keyframes glossyBg {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* شريط اللغات العلوي */
        .lang-bar {
            position: absolute;
            top: 20px;
            left: 20px;
            display: flex;
            gap: 10px;
            z-index: 10;
        }

        .lang-btn {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            color: white;
            padding: 8px 16px;
            border-radius: 20px;
            cursor: pointer;
            font-size: 0.9rem;
            transition: 0.3s;
        }

        .lang-btn:hover {
            background: #3b82f6;
            border-color: #3b82f6;
        }

        /* كارت الترحيب اللامع */
        .welcome-card {
            background: rgba(10, 10, 15, 0.75);
            border: 1px solid rgba(255, 255, 255, 0.08);
            box-shadow: 0 0 40px rgba(59, 130, 246, 0.15), inset 0 0 20px rgba(255, 255, 255, 0.02);
            padding: 40px 30px;
            border-radius: 24px;
            text-align: center;
            max-width: 480px;
            width: 90%;
            backdrop-filter: blur(20px);
            position: relative;
        }

        .logo {
            font-size: 3.5rem;
            color: #3b82f6;
            margin-bottom: 20px;
            filter: drop-shadow(0 0 15px rgba(59, 130, 246, 0.6));
        }

        h1 {
            font-size: 2.2rem;
            margin-bottom: 12px;
            font-weight: 800;
            background: linear-gradient(to right, #fff, #94a3b8);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        p {
            color: #94a3b8;
            font-size: 1rem;
            margin-bottom: 30px;
            line-height: 1.6;
        }

        /* أزرار تسجيل الدخول */
        .auth-options {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            color: white;
            padding: 14px;
            border-radius: 12px;
            font-size: 1rem;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
            width: 100%;
        }

        .btn-discord {
            background: #5865F2;
            box-shadow: 0 4px 20px rgba(88, 101, 242, 0.3);
        }

        .btn-discord:hover {
            background: #4752c4;
            transform: translateY(-2px);
        }

        .btn-google {
            background: #ffffff;
            color: #1f2937;
            box-shadow: 0 4px 20px rgba(255, 255, 255, 0.1);
        }

        .btn-google:hover {
            background: #f3f4f6;
            transform: translateY(-2px);
        }

        .btn-email {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .btn-email:hover {
            background: rgba(255, 255, 255, 0.1);
            border-color: #3b82f6;
        }

        /* النافذة المنبثقة للتسجيل (Modal) */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 100;
            opacity: 0;
            pointer-events: none;
            transition: 0.3s ease;
        }

        .modal.active {
            opacity: 1;
            pointer-events: auto;
        }

        .modal-content {
            background: #0d0d14;
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 35px;
            border-radius: 20px;
            width: 90%;
            max-width: 450px;
            position: relative;
            box-shadow: 0 0 50px rgba(0,0,0,0.8);
        }

        .close-modal {
            position: absolute;
            top: 15px;
            left: 15px;
            color: #64748b;
            cursor: pointer;
            font-size: 1.2rem;
        }

        .form-group {
            margin-bottom: 16px;
            text-align: right;
        }

        .form-group label {
            display: block;
            margin-bottom: 6px;
            font-size: 0.9rem;
            color: #94a3b8;
        }

        .form-group input {
            width: 100%;
            padding: 12px;
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            color: white;
            font-size: 0.95rem;
            outline: none;
            transition: 0.3s;
        }

        .form-group input:focus {
            border-color: #3b82f6;
            background: rgba(255, 255, 255, 0.05);
        }

        /* مؤشر قوة كلمة المرور */
        .password-strength {
            font-size: 0.8rem;
            margin-top: 5px;
            color: #ef4444;
            display: none;
        }

        .checkbox-group {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 20px;
            font-size: 0.85rem;
            color: #94a3b8;
        }

        .checkbox-group input {
            cursor: pointer;
            width: 16px;
            height: 16px;
        }

        .checkbox-group a {
            color: #3b82f6;
            text-decoration: none;
        }
    </style>
</head>
<body>

    <div class="lang-bar">
        <button class="lang-btn" onclick="changeLang('ar')">العربية</button>
        <button class="lang-btn" onclick="changeLang('en')">English</button>
    </div>

    <div class="welcome-card" id="welcomeCard">
        <div class="logo">
            <i class="fa-solid : fa-cloud-bolt"></i>
        </div>
        <h1 id="mainTitle">مرحباً بك في Kerit Cloud</h1>
        <p id="mainDesc">أنشئ واستضف سيرفراتك مجاناً وبأعلى أداء سحابي بره جهازك تماماً.</p>
        
        <div class="auth-options">
            <a href="/auth/discord" class="btn btn-discord">
                <i class="fa-brands : fa-discord"></i>
                <span id="txtDiscord">التسجيل عبر الديسكورد</span>
            </a>

            <a href="/auth/google" class="btn btn-google">
                <img src="https://upload.wikimedia.org/wikipedia/commons/c/c1/Google_構成_2015_logo.svg" alt="Google" style="width: 18px; margin-left: 5px;">
                <span id="txtGoogle">التسجيل عبر جوجل</span>
            </a>

            <button class="btn btn-email" onclick="toggleModal(true)">
                <i class="fa-solid : fa-envelope"></i>
                <span id="txtEmail">إنشاء حساب / تسجيل دخول يدوي</span>
            </button>
        </div>
    </div>

    <div class="modal" id="registerModal">
        <div class="modal-content">
            <i class="fa-solid : fa-xmark close-modal" onclick="toggleModal(false)"></i>
            <h2 style="margin-bottom: 20px; font-weight: 700; text-align: center;">إنشاء حساب جديد</h2>
            
            <form id="registerForm" onsubmit="handleRegister(event)">
                <div class="form-group">
                    <label>اسم المستخدم (يوزر فريد)</label>
                    <input type="text" id="username" required placeholder="مثال: enzo_dev">
                </div>
                <div class="form-group">
                    <label>البريد الإلكتروني</label>
                    <input type="email" id="email" required placeholder="name@example.com">
                </div>
                <div class="form-group">
                    <label>كلمة المرور</label>
                    <input type="password" id="password" required placeholder="••••••••" oninput="checkPasswordStrength()">
                    <div class="password-strength" id="passError">كلمة المرور ضعيفة! يجب أن تحتوي على 8 أحرف وأرقام على الأقل.</div>
                </div>
                <div class="form-group">
                    <label>تأكيد كلمة المرور</label>
                    <input type="password" id="confirmPassword" required placeholder="••••••••">
                </div>

                <div class="checkbox-group">
                    <input type="checkbox" id="termsCheck" required>
                    <label for="termsCheck">أوافق على <a href="#">شروط الخدمة</a> و <a href="#">سياسة الخصوصية</a></label>
                </div>

                <button type="submit" class="btn btn-discord" style="background: #3b82f6;">تأكيد وإنشاء الحساب</button>
            </form>
        </div>
    </div>

    <script>
        // إظهار وإخفاء نافذة التسجيل
        function toggleModal(show) {
            const modal = document.getElementById('registerModal');
            if(show) modal.classList.add('active');
            else modal.classList.remove('active');
        }

        // فحص قوة كلمة المرور
        function checkPasswordStrength() {
            const pass = document.getElementById('password').value;
            const errorDiv = document.getElementById('passError');
            // شرط: أرقام وحروف ولا تقل عن 8 خانات
            const regex = /^(?=.*[A-Za-z])(?=.*\d)[A-Za-z]\d{7,}$/;
            
            if(pass.length < 8) {
                errorDiv.style.display = 'block';
                return false;
            } else {
                errorDiv.style.display = 'none';
                return true;
            }
        }

        // التعامل مع فورم التسجيل
        function handleRegister(e) {
            e.preventDefault();
            const pass = document.getElementById('password').value;
            const confirmPass = document.getElementById('confirmPassword').value;

            if(pass !== confirmPass) {
                alert('كلمات المرور غير متطابقة!');
                return;
            }

            if(pass.length < 8) {
                alert('الرجاء اختيار كلمة مرور أقوى!');
                return;
            }

            // هنا السيستم هيبعت البيانات لقاعدة البيانات بعدين
            alert('تم التسجيل بنجاح! سيتم توجيهك للوحة التحكم.');
            window.location.href = '/dashboard'; // هيحولك لصفحة اللوحة
        }

        // تبديل اللغات البسيط (ترجمة جوجل ستعمل تلقائياً أيضاً بناء على لغة الصفحة)
        function changeLang(lang) {
            if(lang === 'en') {
                document.documentElement.dir = 'ltr';
                document.documentElement.lang = 'en';
                document.getElementById('mainTitle').innerText = "Welcome to Kerit Cloud";
                document.getElementById('mainDesc').innerText = "Create and host your servers for free with top cloud performance entirely off your device.";
                document.getElementById('txtDiscord').innerText = "Sign up via Discord";
                document.getElementById('txtGoogle').innerText = "Sign up via Google";
                document.getElementById('txtEmail').innerText = "Manual Sign up / Login";
            } else {
                document.documentElement.dir = 'rtl';
                document.documentElement.lang = 'ar';
                document.getElementById('mainTitle').innerText = "مرحباً بك في Kerit Cloud";
                document.getElementById('mainDesc').innerText = "أنشئ واستضف سيرفراتك مجاناً وبأعلى أداء سحابي بره جهازك تماماً.";
                document.getElementById('txtDiscord').innerText = "التسجيل عبر الديسكورد";
                document.getElementById('txtGoogle').innerText = "التسجيل عبر جوجل";
                document.getElementById('txtEmail').innerText = "إنشاء حساب / تسجيل دخول يدوي";
            }
        }
    </script>

</body>
</html>
