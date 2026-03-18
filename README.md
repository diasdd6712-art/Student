<html lang="kk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Launcher Activity орнату</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #f0f2f5;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            background: #ffffff;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            width: 100%;
            max-width: 550px;
            padding: 28px;
        }

        h1 {
            color: #333;
            font-size: 22px;
            margin-bottom: 8px;
        }

        .subtitle {
            color: #666;
            font-size: 13px;
            margin-bottom: 24px;
        }

        .task-badge {
            display: inline-block;
            background: #E3F2FD;
            color: #1976D2;
            padding: 4px 12px;
            border-radius: 12px;
            font-size: 12px;
            font-weight: 600;
            margin-bottom: 16px;
        }

        .form-group {
            margin-bottom: 16px;
        }

        label {
            display: block;
            color: #444;
            font-size: 13px;
            margin-bottom: 6px;
            font-weight: 500;
        }

        select, input[type="text"] {
            width: 100%;
            padding: 10px 12px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 14px;
            font-family: 'Courier New', monospace;
            background: #fff;
        }

        select:focus, input[type="text"]:focus {
            outline: none;
            border-color: #2196F3;
        }

        .btn-set {
            background: #2196F3;
            color: white;
            border: none;
            padding: 12px 24px;
            font-size: 14px;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
            margin-top: 8px;
        }

        .btn-set:hover {
            background: #1976D2;
        }

        .result-section {
            margin-top: 24px;
            padding-top: 20px;
            border-top: 2px solid #e0e0e0;
            display: none;
        }

        .result-section.show {
            display: block;
        }

        .code-block {
            background: #1e1e1e;
            border-radius: 6px;
            padding: 16px;
            margin-bottom: 16px;
            overflow-x: auto;
        }

        .file-name {
            color: #9cdcfe;
            font-size: 12px;
            margin-bottom: 10px;
            font-weight: bold;
        }

        .code-line {
            color: #d4d4d4;
            font-family: 'Courier New', monospace;
            font-size: 13px;
            line-height: 1.8;
        }

        .tag { color: #569cd6; }
        .attr { color: #9cdcfe; }
        .value { color: #ce9178; }
        .comment { color: #6a9955; }

        /* ҚЫЗҒЫЛТ САРЫ НӘТИЖЕ */
        .launcher-result {
            background: linear-gradient(135deg, #FFF3E0 0%, #FFE0B2 100%);
            border: 2px solid #FF9800;
            border-radius: 8px;
            padding: 20px;
            margin-top: 16px;
        }

        .result-title {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 12px;
        }

        .icon-launcher {
            width: 40px;
            height: 40px;
            background: #FF9800;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 20px;
        }

        .highlight-text {
            font-size: 18px;
            font-weight: 700;
            color: #E65100;
            text-shadow: 1px 1px 2px rgba(230, 81, 0, 0.2);
        }

        .result-desc {
            color: #BF360C;
            font-size: 14px;
            line-height: 1.6;
            margin-top: 8px;
            padding-left: 8px;
            border-left: 3px solid #FF9800;
        }

        .phone-mockup {
            background: #263238;
            border-radius: 20px;
            padding: 16px;
            margin-top: 16px;
            text-align: center;
        }

        .phone-screen {
            background: #fff;
            border-radius: 12px;
            padding: 40px 20px;
            min-height: 120px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 12px;
        }

        .app-icon-large {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #FF9800 0%, #F57C00 100%);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 28px;
            box-shadow: 0 4px 8px rgba(255, 152, 0, 0.3);
        }

        .app-label {
            color: #333;
            font-size: 14px;
            font-weight: 500;
        }

        .tap-hint {
            color: #999;
            font-size: 12px;
        }
    </style>
</head>
<body>
    <div class="container">
        <span class="task-badge">3-тапсырма</span>
        <h1>🚀 Launcher Activity орнату</h1>
        <p class="subtitle">Қосымшаның бастапқы экранын таңдаңыз</p>

        <div class="form-group">
            <label>Бастапқы экран (Launcher):</label>
            <select id="launcherActivity">
                <option value="MainActivity">MainActivity</option>
                <option value="SecondActivity">SecondActivity</option>
                <option value="SplashActivity">SplashActivity</option>
                <option value="LoginActivity">LoginActivity</option>
            </select>
        </div>

        <div class="form-group">
            <label>Қосымша атауы:</label>
            <input type="text" id="appName" value="Менің Қосымшам">
        </div>

        <button class="btn-set" onclick="setLauncher()">
            Launcher ретінде орнату
        </button>

        <div id="resultSection" class="result-section">
            <!-- AndroidManifest.xml -->
            <div class="code-block">
                <div class="file-name">📄 AndroidManifest.xml</div>
                <div class="code-line" id="manifestCode"></div>
            </div>

            <!-- Қызғылт сары нәтиже -->
            <div class="launcher-result">
                <div class="result-title">
                    <div class="icon-launcher">▶</div>
                    <div class="highlight-text" id="resultText">
                        Нәтиже: Қосымша осы экраннан ашылады!
                    </div>
                </div>
                <div class="result-desc" id="resultDesc">
                    MainActivity — қосымшаның бастапқы нүктесі.<br>
                    Пайдаланшы қосымшаны іске қосқанда бірінші осы экран көрсетіледі.
                </div>
            </div>

            <!-- Телефон макеті -->
            <div class="phone-mockup">
                <div style="color: #90a4ae; font-size: 11px; margin-bottom: 12px;">📱 Телефон экраны</div>
                <div class="phone-screen">
                    <div class="app-icon-large">📱</div>
                    <div class="app-label" id="phoneAppName">Менің Қосымшам</div>
                    <div class="tap-hint">Басыңыз → <span id="phoneActivity">MainActivity</span> ашылады</div>
                </div>
            </div>
        </div>
    </div>

    <script>
        function setLauncher() {
            const activity = document.getElementById('launcherActivity').value;
            const appName = document.getElementById('appName').value || 'Менің Қосымшам';
            
            // Manifest кодын генерациялау
            const manifestCode = `<span class="tag">&lt;activity</span>
    <span class="attr">android:name</span>=<span class="value">".${activity}"</span>
    <span class="attr">android:label</span>=<span class="value">"@string/app_name"</span><span class="tag">&gt;</span>
    <span class="tag">&lt;intent-filter&gt;</span>
        <span class="tag">&lt;action</span> <span class="attr">android:name</span>=<span class="value">"android.intent.action.MAIN"</span> <span class="tag">/&gt;</span>
        <span class="tag">&lt;category</span> <span class="attr">android:name</span>=<span class="value">"android.intent.category.LAUNCHER"</span> <span class="tag">/&gt;</span>
    <span class="tag">&lt;/intent-filter&gt;</span>
<span class="tag">&lt;/activity&gt;</span>

<span class="comment">&lt;!-- Нәтиже: ${activity} қосымшаның бастапқы экраны болды --&gt;</span>`;

            document.getElementById('manifestCode').innerHTML = manifestCode;
            
            // Нәтиже мәтінін жаңарту
            document.getElementById('resultText').innerHTML = `Нәтиже: Қосымша осы экраннан ашылады!`;
            document.getElementById('resultDesc').innerHTML = `
                <strong>${activity}</strong> — қосымшаның бастапқы нүктесі.<br>
                Пайдаланушы қосымшаны іске қосқанда бірінші осы экран көрсетіледі.<br>
                <span style="color: #E65100; font-size: 12px; margin-top: 8px; display: block;">
                    ⚡ MAIN action + LAUNCHER category = Бастапқы экран
                </span>
            `;
            
            // Телефон макетін жаңарту
            document.getElementById('phoneAppName').textContent = appName;
            document.getElementById('phoneActivity').textContent = activity;
            
            // Нәтиже бөлімін көрсету
            document.getElementById('resultSection').classList.add('show');
        }
    </script>
</body>
</html>
