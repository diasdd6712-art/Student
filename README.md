<html lang="kk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Батырма → Жаңа Activity</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Roboto, sans-serif;
            background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            background: #ffffff;
            border-radius: 24px;
            box-shadow: 0 25px 80px rgba(0,0,0,0.2);
            width: 100%;
            max-width: 480px;
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
            color: white;
            padding: 35px;
            text-align: center;
        }

        .icon-box {
            width: 70px;
            height: 70px;
            background: rgba(255,255,255,0.2);
            border-radius: 20px;
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 35px;
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255,255,255,0.3);
        }

        .header h1 {
            font-size: 26px;
            font-weight: 700;
        }

        .header p {
            opacity: 0.9;
            margin-top: 10px;
            font-size: 15px;
        }

        .demo-area {
            padding: 30px;
            background: #f8f9fa;
        }

        .phone-screen {
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.08);
            text-align: center;
        }

        .screen-title {
            color: #666;
            font-size: 13px;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* БАТЫРМА СТИЛІ */
        .action-button {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            padding: 18px 36px;
            font-size: 16px;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            transition: all 0.3s;
            box-shadow: 0 6px 20px rgba(102, 126, 234, 0.4);
        }

        .action-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(102, 126, 234, 0.5);
        }

        .action-button:active {
            transform: translateY(-1px);
        }

        .action-button::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(255,255,255,0.3);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .action-button:active::after {
            width: 300px;
            height: 300px;
        }

        .arrow-animation {
            margin-top: 25px;
            font-size: 30px;
            color: #667eea;
            opacity: 0;
            transform: translateY(-10px);
            transition: all 0.4s;
        }

        .arrow-animation.show {
            opacity: 1;
            transform: translateY(0);
            animation: bounce 1s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .second-screen {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            border-radius: 20px;
            padding: 40px;
            margin-top: 20px;
            opacity: 0;
            transform: scale(0.9);
            transition: all 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        .second-screen.show {
            opacity: 1;
            transform: scale(1);
        }

        .second-screen h3 {
            color: white;
            font-size: 24px;
            margin-bottom: 10px;
        }

        .second-screen p {
            color: rgba(255,255,255,0.9);
            font-size: 14px;
        }

        .code-section {
            padding: 30px;
        }

        .section-title {
            color: #333;
            font-size: 18px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .code-block {
            background: #1e1e1e;
            border-radius: 16px;
            padding: 24px;
            margin-bottom: 16px;
        }

        .code-header {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 16px;
            padding-bottom: 16px;
            border-bottom: 1px solid #333;
        }

        .code-icon {
            width: 40px;
            height: 40px;
            background: #11998e;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 20px;
        }

        .code-title {
            color: #fff;
            font-size: 15px;
            font-weight: 600;
        }

        .code-path {
            color: #888;
            font-size: 12px;
        }

        pre {
            color: #d4d4d4;
            font-family: 'Courier New', monospace;
            font-size: 13px;
            line-height: 1.8;
            overflow-x: auto;
        }

        .keyword { color: #569cd6; }
        .string { color: #ce9178; }
        .comment { color: #6a9955; }
        .function { color: #dcdcaa; }
        .class { color: #4ec9b0; }
        .variable { color: #9cdcfe; }

        /* ҚЫЗҒЫЛТ САРЫ НӘТИЖЕ */
        .result-box {
            background: linear-gradient(135deg, #FFD93D 0%, #FF6B6B 100%);
            border-radius: 20px;
            padding: 28px;
            margin-top: 20px;
            text-align: center;
            box-shadow: 0 10px 40px rgba(255, 107, 107, 0.3);
        }

        .result-icon {
            width: 70px;
            height: 70px;
            background: white;
            border-radius: 50%;
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 35px;
            box-shadow: 0 6px 20px rgba(0,0,0,0.1);
        }

        .result-text {
            font-size: 24px;
            font-weight: 800;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
            line-height: 1.4;
        }

        .result-hint {
            color: rgba(255,255,255,0.95);
            font-size: 14px;
            margin-top: 12px;
        }

        .flow-diagram {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
            flex-wrap: wrap;
        }

        .flow-box {
            background: white;
            border-radius: 16px;
            padding: 20px 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            text-align: center;
        }

        .flow-box.from {
            border: 3px solid #11998e;
        }

        .flow-box.to {
            border: 3px solid #f5576c;
        }

        .flow-arrow {
            font-size: 30px;
            color: #667eea;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="icon-box">🔄</div>
            <h1>Батырма → Жаңа Activity</h1>
            <p>Intent арқылы экрандар арасында өту</p>
        </div>

        <div class="demo-area">
            <div class="phone-screen">
                <div class="screen-title">📱 MainActivity</div>
                
                <button class="action-button" onclick="openNewScreen()">
                    🚀 SecondActivity ашу
                </button>
                
                <div class="arrow-animation" id="arrow">⬇</div>
                
                <div class="second-screen" id="secondScreen">
                    <h3>🎉 SecondActivity</h3>
                    <p>Жаңа экран сәтті ашылды!</p>
                </div>
            </div>
        </div>

        <div class="code-section">
            <h2 class="section-title">
                <span>💻</span> Java коды
            </h2>

            <div class="code-block">
                <div class="code-header">
                    <div class="code-icon">☕</div>
                    <div>
                        <div class="code-title">MainActivity.java</div>
                        <div class="code-path">onCreate() методында</div>
                    </div>
                </div>
                <pre><span class="comment">// Батырма табу</span>
<span class="class">Button</span> <span class="variable">btnOpen</span> = findViewById(R.id.<span class="variable">btnOpen</span>);

<span class="comment">// Басыңда жаңа Activity ашу</span>
btnOpen.setOnClickListener(<span class="keyword">new</span> <span class="class">View.OnClickListener</span>() {
    <span class="annotation">@Override</span>
    <span class="keyword">public void</span> <span class="function">onClick</span>(View v) {
        <span class="comment">// Intent жасау</span>
        <span class="class">Intent</span> <span class="variable">intent</span> = <span class="keyword">new</span> <span class="class">Intent</span>(
            MainActivity.<span class="keyword">this</span>, 
            SecondActivity.<span class="keyword">class</span>
        );
        
        <span class="comment">// Activity ашу</span>
        startActivity(intent);
    }
});</pre>
            </div>

            <div class="code-block">
                <div class="code-header">
                    <div class="code-icon">🎨</div>
                    <div>
                        <div class="code-title">activity_main.xml</div>
                        <div class="code-path">Батырма layout</div>
                    </div>
                </div>
                <pre><span class="keyword">&lt;Button</span>
    android:id=<span class="string">"@+id/btnOpen"</span>
    android:layout_width=<span class="string">"wrap_content"</span>
    android:layout_height=<span class="string">"wrap_content"</span>
    android:text=<span class="string">"SecondActivity ашу"</span>
    android:backgroundTint=<span class="string">"#667eea"</span> <span class="keyword">/&gt;</span></pre>
            </div>

            <!-- Қызғылт сары нәтиже -->
            <div class="result-box">
                <div class="result-icon">✨</div>
                <div class="result-text">
                    Нәтиже: Батырма басқанда<br>жаңа Activity ашылады!
                </div>
                <div class="result-hint">
                    Intent = Экрандар арасында хабаршы
                </div>
            </div>

            <!-- Схема -->
            <div class="flow-diagram">
                <div class="flow-box from">
                    <div style="font-size: 24px;">📱</div>
                    <div style="color: #333; font-weight: 600; margin-top: 8px;">MainActivity</div>
                    <div style="color: #666; font-size: 12px; margin-top: 4px;">Бастапқы экран</div>
                </div>
                <div class="flow-arrow">➡️ Intent ➡️</div>
                <div class="flow-box to">
                    <div style="font-size: 24px;">🚀</div>
                    <div style="color: #333; font-weight: 600; margin-top: 8px;">SecondActivity</div>
                    <div style="color: #666; font-size: 12px; margin-top: 4px;">Жаңа экран</div>
                </div>
            </div>
        </div>
    </div>

    <script>
        function openNewScreen() {
            const arrow = document.getElementById('arrow');
            const secondScreen = document.getElementById('secondScreen');
            
            // Стрелканы көрсету
            arrow.classList.add('show');
            
            // Activity ашылу анимациясы
            setTimeout(() => {
                secondScreen.classList.add('show');
            }, 400);
            
            // Қайта орнату (қайта басу үшін)
            setTimeout(() => {
                arrow.classList.remove('show');
                secondScreen.classList.remove('show');
            }, 3000);
        }
    </script>
</body>
</html>
