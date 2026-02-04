<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ringle AI Live Feedback MVP</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        body {
            background-color: #0b0e26; /* 링글 앱 특유의 깊은 네이비 */
            color: white;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }
        .iphone-frame {
            width: 375px;
            height: 812px;
            background-color: #0b0e26;
            border: 8px solid #1f2937;
            border-radius: 40px;
            position: relative;
            display: flex;
            flex-direction: column;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
        }
        .status-bar {
            height: 44px;
            padding: 0 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 14px;
            font-weight: 600;
        }
        .content {
            flex: 1;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 40px 24px;
            text-align: center;
        }
        .avatar {
            width: 72px;
            height: 72px;
            background: #7367f0;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 28px;
            font-weight: bold;
            margin-bottom: 12px;
        }
        .ai-name {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 4px;
        }
        .timer {
            font-size: 18px;
            color: #94a3b8;
            margin-bottom: 40px;
        }
        .speech-container {
            width: 100%;
            display: flex;
            flex-direction: column;
            gap: 24px;
        }
        .ai-message {
            font-size: 18px;
            line-height: 1.5;
            color: #f8fafc;
            opacity: 0;
            transition: opacity 0.5s ease;
        }
        .user-transcription {
            font-size: 20px;
            line-height: 1.4;
            font-weight: 600;
            color: #fbbf24; /* 요청하신 노란색 하이라이트 */
            min-height: 60px;
        }
        .correction-card {
            background: rgba(255, 255, 255, 0.08);
            border: 1px solid rgba(251, 191, 36, 0.3);
            border-radius: 16px;
            padding: 16px;
            text-align: left;
            transform: translateY(20px);
            opacity: 0;
            transition: all 0.6s cubic-bezier(0.16, 1, 0.3, 1);
        }
        .correction-card.show {
            transform: translateY(0);
            opacity: 1;
        }
        .correction-header {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 12px;
            color: #fbbf24;
            font-weight: 700;
            margin-bottom: 8px;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }
        .original-text {
            color: #94a3b8;
            font-size: 14px;
            text-decoration: line-through;
            margin-bottom: 4px;
        }
        .suggested-text {
            color: white;
            font-size: 16px;
            font-weight: 500;
        }
        .suggested-text span {
            color: #fbbf24;
            font-weight: 700;
        }
        .controls {
            height: 180px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            gap: 30px;
            padding-bottom: 20px;
        }
        .button-row {
            display: flex;
            justify-content: space-evenly;
            align-items: center;
            width: 100%;
        }
        .icon-btn {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
            color: #94a3b8;
            font-size: 12px;
            cursor: pointer;
        }
        .icon-circle {
            width: 52px;
            height: 52px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            color: white;
        }
        .hang-up-btn {
            width: 72px;
            height: 72px;
            background: #ef4444;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 30px;
            color: white;
            box-shadow: 0 10px 15px -3px rgba(239, 68, 68, 0.3);
            cursor: pointer;
        }
        .overlay {
            position: absolute;
            inset: 0;
            background: rgba(11, 14, 38, 0.9);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 50;
            border-radius: 32px;
            cursor: pointer;
        }
        .start-badge {
            background: #fbbf24;
            color: #0b0e26;
            padding: 12px 24px;
            border-radius: 30px;
            font-weight: 800;
            font-size: 18px;
            animation: bounce 1s infinite;
        }
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }
    </style>
</head>
<body>

    <div class="iphone-frame">
        <!-- 시작 오버레이 -->
        <div id="overlay" class="overlay" onclick="startCall()">
            <div class="start-badge">전화 시작하기</div>
        </div>

        <div class="status-bar">
            <span>12:54</span>
            <div class="flex gap-1 items-center">
                <i class="fas fa-signal"></i>
                <i class="fas fa-wifi"></i>
                <i class="fas fa-battery-full"></i>
            </div>
        </div>

        <div class="content">
            <div class="avatar">G</div>
            <div class="ai-name">Gwen</div>
            <div id="timer" class="timer">00:00</div>

            <div class="speech-container">
                <!-- AI 발화 -->
                <div id="ai-message" class="ai-message">
                    "Hello! It's great to see you again. Are you ready for our session today?"
                </div>

                <!-- 유저 실시간 발화 (노란색) -->
                <div id="user-transcription" class="user-transcription"></div>

                <!-- 실시간 교정 카드 -->
                <div id="correction-card" class="correction-card">
                    <div class="correction-header">
                        <i class="fas fa-sparkles"></i>
                        Ivy League Feedback
                    </div>
                    <div class="original-text" id="original-text">"I want to find gaps in the market."</div>
                    <div class="suggested-text" id="suggested-text">
                        Try: <span>"I'm looking to identify untapped market opportunities."</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="controls">
            <div class="button-row">
                <div class="icon-btn">
                    <div class="icon-circle"><i class="fas fa-microphone-slash"></i></div>
                    <span>소리끔</span>
                </div>
                <div class="icon-btn">
                    <div class="icon-circle"><i class="fas fa-volume-up"></i></div>
                    <span>스피커</span>
                </div>
                <div class="icon-btn">
                    <div class="icon-circle"><i class="fas fa-closed-captioning"></i></div>
                    <span>모두 보기</span>
                </div>
            </div>
            <div class="button-row">
                <div class="hang-up-btn" onclick="location.reload()">
                    <i class="fas fa-phone-slash"></i>
                </div>
            </div>
        </div>
    </div>

    <script>
        let seconds = 0;
        let timerInterval;

        function startCall() {
            document.getElementById('overlay').style.display = 'none';
            
            // 타이머 시작
            timerInterval = setInterval(() => {
                seconds++;
                const m = Math.floor(seconds / 60).toString().padStart(2, '0');
                const s = (seconds % 60).toString().padStart(2, '0');
                document.getElementById('timer').innerText = `${m}:${s}`;
            }, 1000);

            // 시나리오 시작
            runScenario();
        }

        async function runScenario() {
            const aiMsg = document.getElementById('ai-message');
            const userTrans = document.getElementById('user-transcription');
            const correction = document.getElementById('correction-card');

            // 1. AI가 인사함
            aiMsg.style.opacity = '1';
            
            await new Promise(r => setTimeout(r, 2000));

            // 2. 유저가 답변함 (실시간 타이핑 효과)
            const sentence = "I wanted to... uh... find some gaps in the market.";
            const words = sentence.split(" ");
            
            for(let i=0; i<words.length; i++) {
                userTrans.innerText += (i === 0 ? "" : " ") + words[i];
                await new Promise(r => setTimeout(r, 4000 / words.length));
            }

            await new Promise(r => setTimeout(r, 8000));

            // 3. 실시간 교정 등장
            correction.classList.add('show');
        }
    </script>
</body>
</html>
