<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FUTURE AI SYSTEM</title>
    <style>
        :root { --neon: #00f2fe; --bg: #050505; --glass: rgba(255, 255, 255, 0.05); }
        body { background: var(--bg); color: white; font-family: 'Segoe UI', sans-serif; margin: 0; display: flex; align-items: center; justify-content: center; height: 100vh; overflow: hidden; }
        
        /* شاشة الدخول */
        #login-screen { text-align: center; z-index: 10; transition: 0.5s; }
        .glass-box { background: var(--glass); backdrop-filter: blur(15px); border: 1px solid rgba(0, 242, 254, 0.3); padding: 40px; border-radius: 25px; box-shadow: 0 0 40px rgba(0, 242, 254, 0.2); }
        h1 { font-size: 3rem; letter-spacing: 5px; color: var(--neon); text-shadow: 0 0 15px var(--neon); margin-bottom: 20px; }
        input { background: rgba(0,0,0,0.6); border: 1px solid #333; color: white; padding: 12px; width: 200px; border-radius: 10px; text-align: center; outline: none; transition: 0.3s; }
        input:focus { border-color: var(--neon); box-shadow: 0 0 10px var(--neon); }
        button { background: var(--neon); color: black; border: none; padding: 12px 30px; border-radius: 10px; cursor: pointer; font-weight: bold; margin-top: 15px; transition: 0.3s; }
        button:hover { transform: scale(1.05); box-shadow: 0 0 20px var(--neon); }

        /* واجهة النظام والذكاء الاصطناعي */
        #main-system { display: none; width: 90%; max-width: 600px; height: 80vh; flex-direction: column; }
        .ai-chat { flex-grow: 1; background: var(--glass); border: 1px solid rgba(0, 242, 254, 0.2); border-radius: 20px; padding: 20px; overflow-y: auto; margin-bottom: 15px; display: flex; flex-direction: column; gap: 10px; }
        .msg { padding: 10px 15px; border-radius: 15px; max-width: 80%; line-height: 1.4; }
        .ai-msg { background: rgba(0, 242, 254, 0.1); align-self: flex-start; border-left: 3px solid var(--neon); }
        .user-msg { background: rgba(255, 255, 255, 0.1); align-self: flex-end; }
        .input-area { display: flex; gap: 10px; }
        .input-area input { flex-grow: 1; text-align: right; }
    </style>
</head>
<body>

    <div id="login-screen" class="glass-box">
        <h1>FUTURE</h1>
        <p style="opacity: 0.7;">نظام الوعي الاصطناعي المشفر</p>
        <input type="password" id="passCode" placeholder="كود الوصول">
        <br>
        <button onclick="login()">تشغيل النواة</button>
    </div>

    <div id="main-system">
        <h2 style="color: var(--neon); text-align: center;">المساعد الذكي FUTURE AI</h2>
        <div class="ai-chat" id="chatBox">
            <div class="msg ai-msg">تم تفعيل البروتوكول بنجاح. أنا مساعدك الشخصي في نظام FUTURE، كيف يمكنني مساعدتك اليوم؟</div>
        </div>
        <div class="input-area">
            <input type="text" id="userInput" placeholder="اسأل المساعد...">
            <button onclick="sendMessage()" style="margin-top:0">إرسال</button>
        </div>
    </div>

    <script>
        // كود الدخول
        function login() {
            const code = document.getElementById('passCode').value;
            if(code === "24262") {
                document.getElementById('login-screen').style.display = 'none';
                document.getElementById('main-system').style.display = 'flex';
            } else {
                alert("تم رصد محاولة دخول غير مصرح بها!");
            }
        }

        // ذكاء اصطناعي تفاعلي (محاكاة)
        function sendMessage() {
            const input = document.getElementById('userInput');
            const chatBox = document.getElementById('chatBox');
            if(input.value.trim() === "") return;

            // رسالة المستخدم
            chatBox.innerHTML += `<div class="msg user-msg">${input.value}</div>`;
            
            // رد الذكاء الاصطناعي
            const userText = input.value;
            let aiResponse = "أقوم بتحليل بياناتك الآن... نظام FUTURE تحت أمرك.";
            
            if(userText.includes("من أنت")) aiResponse = "أنا النواة الذكية لنظام FUTURE، صُممت لأكون مساعدك الشخصي.";
            if(userText.includes("الوقت")) aiResponse = "نحن الآن في عصر المستقبل، الساعة تشير إلى زمن الإنجاز.";
            if(userText.includes("شكرا")) aiResponse = "لا داعي للشكر، أنا هنا لخدمة أهدافك.";

            setTimeout(() => {
                chatBox.innerHTML += `<div class="msg ai-msg">${aiResponse}</div>`;
                chatBox.scrollTop = chatBox.scrollHeight;
            }, 1000);

            input.value = "";
            chatBox.scrollTop = chatBox.scrollHeight;
        }
    </script>
</body>
</html>
