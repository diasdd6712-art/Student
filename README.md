<html lang="kk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SecondActivity қосу</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Roboto, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            background: #ffffff;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            width: 100%;
            max-width: 500px;
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            text-align: center;
        }

        .header-icon {
            width: 80px;
            height: 80px;
            background: rgba(255,255,255,0.2);
            border-radius: 20px;
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 40px;
            backdrop-filter: blur(10px);
        }

        .header h1 {
            font-size: 24px;
            font-weight: 600;
        }

        .header p {
            opacity: 0.9;
            margin-top: 8px;
            font-size: 14px;
        }

        .content {
            padding: 30px;
        }

        .step {
            display: flex;
            align-items: flex-start;
            gap: 16px;
            margin-bottom: 24px;
            padding: 16px;
            background: #f8f9fa;
            border-radius: 12px;
            border-left: 4px solid #667eea;
        }

        .step-number {
            width: 32px;
            height: 32px;
            background: #667eea;
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            flex-shrink: 0;
        }

        .step-content h3 {
            color: #333;
            font-size: 16px;
            margin-bottom: 4px;
        }

        .step-content p {
            color: #666;
            font-size: 13px;
        }

        .btn-create {
            width: 100%;
            padding: 16px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .btn-create:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.4);
        }

        .result-section {
            display: none;
            margin-top: 24px;
        }

        .result-section.show {
            display: block;
            animation: slideUp 0.5s ease;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .code-card {
            background: #1e1e1e;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 16px;
            overflow-x: auto;
        }

        .code-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 12px;
            padding-bottom: 12px;
            border-bottom: 1px solid #333;
        }

        .file-icon {
            width: 36px;
            height: 36px;
            background: #667eea;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 18px;
        }

        .file-name {
            color: #fff;
            font-size: 14px;
            font-weight: 600;
        }

        .file-path {
            color: #888;
            font-size: 12px;
        }

        .code-content {
            color: #d4d4d4;
            font-family: 'Courier New', monospace;
            font-size: 13px;
            line-height: 1.8;
        }

        .keyword { color: #569cd6; }
        .string { color: #ce9178; }
        .comment { color: #6a9955; }
        .function { color: #dcdcaa; }
        .class-name { color: #4ec9b0; }

        /* ҚЫЗҒЫЛТ САРЫ НӘТИЖЕ */
        .success-banner {
            background: linear-gradient(135deg, #FFD93D 0%, #FF6B6B 100%);
            border-radius: 16px;
            padding: 24px;
            text-align: center;
            margin-top: 20px;
            box-shadow: 0 10px 30px rgba(255, 107, 107, 0.3);
        }

        .success-icon {
            width: 60px;
            height: 60px;
            background: white;
            border-radius: 50%;
            margin: 0 auto 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        .success-text {
            font-size: 22px;
            font-weight: 800;
            color: #fff;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
            line-height: 1.4;
        }

        .success-subtext {
            color: rgba(255,255,255,0.9);
            font-size: 14px;
            margin-top: 8px;
        }

        .nav-hint {
            background: #f0f0f0;
            border-radius: 8px;
            padding: 12px;
            margin-top: 16px;
            font-size: 13px;
            color: #555;
        }

        .nav-code {
            background: #e0e0e0;
            padding: 4px 8px;
            border-radius: 4px;
            font-family: monospace;
            color: #333;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="header-icon">📱</div>
            <h1>SecondActivity қосу</h1>
            <p>Жаңа экран жасау және навигация</p>
        </div>

        <div class="content">
            <div class="step">
                <div class="step-number">1</div>
                <div class="step-content">
                    <h3>Java классын жасау</h3>
                    <p>SecondActivity.java файлы</p>
                </div>
            </div>

            <div class="step">
                <div class="step-number">2</div>
                <div class="step-content">
                    <h3>Layout дизайны</h3>
                    <p>activity_second.xml интерфейс</p>
                </div>
            </div>

            <div class="step">
                <div class="step-number">3</div>
                <div class="step-content">
                    <h3>Manifest тіркеу</h3>
                    <p>AndroidManifest.xml жаңарту</p>
                </div>
            </div>

            <button class="btn-create" onclick="createActivity()">
                ✨ SecondActivity жасау
            </button>

            <div id="resultSection" class="result-section">
                <!-- SecondActivity.java -->
                <div class="code-card">
                    <div class="code-header">
                        <div class="file-icon">☕</div>
                        <div>
                            <div class="file-name">SecondActivity.java</div>
                            <div class="file-path">app/src/main/java/com/example/</div>
                        </div>
                    </div>
                    <div class="code-content">
<span class="keyword">package</span> com.example.myapp;

<span class="keyword">import</span> android.os.Bundle;
<span class="keyword">import</span> androidx.appcompat.app.AppCompatActivity;

<span class="keyword">public class</span> <span class="class-name">SecondActivity</span> <span class="keyword">extends</span> AppCompatActivity {
    <span class="annotation">@Override</span>
    <span class="keyword">protected void</span> <span class="function">onCreate</span>(Bundle savedInstanceState) {
        <span class="keyword">super</span>.onCreate(savedInstanceState);
        setContentView(R.layout.<span class="string">activity_second</span>);
    }
}</div>
                </div>

                <!-- activity_second.xml -->
                <div class="code-card">
                    <div class="code-header">
                        <div class="file-icon">🎨</div>
                        <div>
                            <div class="file-name">activity_second.xml</div>
                            <div class="file-path">app/src/main/res/layout/</div>
                        </div>
                    </div>
                    <div class="code-content">
<span class="keyword">&lt;?xml version="1.0" encoding="utf-8"?&gt;</span>
<span class="keyword">&lt;LinearLayout</span> 
    xmlns:android=<span class="string">"http://schemas.android.com/apk/res/android"</span>
    android:layout_width=<span class="string">"match_parent"</span>
    android:layout_height=<span class="string">"match_parent"</span>
    android:orientation=<span class="string">"vertical"</span>
    android:gravity=<span class="string">"center"</span>
    android:background=<span class="string">"#667eea"</span><span class="keyword">&gt;</span>

    <span class="keyword">&lt;TextView</span>
        android:layout_width=<span class="string">"wrap_content"</span>
        android:layout_height=<span class="string">"wrap_content"</span>
        android:text=<span class="string">"🎉 SecondActivity"</span>
        android:textColor=<span class="string">"#FFFFFF"</span>
        android:textSize=<span class="string">"28sp"</span>
        android:textStyle=<span class="string">"bold"</span> <span class="keyword">/&gt;</span>

    <span class="keyword">&lt;Button</span>
        android:id=<span class="string">"@+id/btnBack"</span>
        android:layout_width=<span class="string">"wrap_content"</span>
        android:layout_height=<span class="string">"wrap_content"</span>
        android:text=<span class="string">"Артқа"</span>
        android:layout_marginTop=<span class="string">"20dp"</span> <span class="keyword">/&gt;</span>

<span class="keyword">&lt;/LinearLayout&gt;</span></div>
                </div>

                <!-- AndroidManifest.xml -->
                <div class="code-card">
                    <div class="code-header">
                        <div class="file-icon">📋</div>
                        <div>
                            <div class="file-name">AndroidManifest.xml</div>
                            <div class="file-path">app/src/main/</div>
                        </div>
                    </div>
                    <div class="code-content">
<span class="keyword">&lt;activity</span>
    android:name=<span class="string">".SecondActivity"</span>
    android:label=<span class="string">"Екінші экран"</span> <span class="keyword">/&gt;</span>

<span class="comment">&lt;!-- Автоматты түрде тіркелді --&gt;</span></div>
                </div>

                <!-- Қызғылт сары нәтиже -->
                <div class="success-banner">
                    <div class="success-icon">🚀</div>
                    <div class="success-text">
                        SecondActivity сәтті қосылды!
                    </div>
                    <div class="success-subtext">
                        Енді бір экраннан екіншісіне өтуге болады
                    </div>
                </div>

                <div class="nav-hint">
                    <strong>Навигация коды:</strong><br>
                    <span class="nav-code">Intent intent = new Intent(MainActivity.this, SecondActivity.class);<br>startActivity(intent);</span>
                </div>
            </div>
        </div>
    </div>

    <script>
        function createActivity() {
            document.getElementById('resultSection').classList.add('show');
        }
    </script>
</body>
</html>
