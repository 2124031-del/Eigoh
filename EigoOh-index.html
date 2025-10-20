<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>英語王</title>
    <!-- レトロゲーム風フォントをGoogle Fontsから読み込み -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=DotGothic16&family=Press+Start+2P&display=swap" rel="stylesheet">
    <style>
        /* --- 全体のスタイル --- */
        :root {
            --level1-color: #87cefa; --level2-color: #ffd700; --level3-color: #ff4500;
            --hp-color: #32cd32; --hp-damage-color: #dc143c; --exp-color: #9acd32;
            --damage-color: #ff4757; --critical-color: #f1c40f; --correct-color: #2ed573; --incorrect-color: #ff6348;
        }

        body { background-color: #000; font-family: 'DotGothic16', sans-serif; color: #fff; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; text-align: center; overflow: hidden; transition: background-color 1s; }
        .screen { width: 100%; height: 100%; display: flex; flex-direction: column; justify-content: center; align-items: center; padding: 10px; box-sizing: border-box; position: absolute; top: 0; left: 0; transition: opacity 0.3s, visibility 0.3s; }
        .hidden { display: none !important; }
        .flex { display: flex; }

        /* --- タイトル画面 --- */
        .title { font-family: 'Press Start 2P', cursive; font-size: clamp(2.5rem, 10vw, 4.5rem); color: #fff; margin-bottom: 60px; animation: flicker 1.5s infinite alternate; }
        @keyframes flicker { 0%,18%,22%,25%,53%,57%,100%{text-shadow:0 0 4px #fff,0 0 11px #fff,0 0 19px #fff,0 0 40px #0fa,0 0 80px #0fa,0 0 90px #0fa,0 0 100px #0fa,0 0 150px #0fa} 20%,24%,55%{text-shadow:none} }
        
        .menu, .level-select-menu { display: flex; flex-direction: column; gap: 25px; align-items: center; width: 90%; max-width: 400px; }

        .menu-button, .level-button, .close-button, .popup-button, .choice-button { 
            font-family: 'DotGothic16', sans-serif; 
            background-color: #4a4a4a; 
            color: #fff; 
            border: 4px solid #000;
            box-shadow: 6px 6px 0 #000; 
            cursor: pointer; 
            transition: all .1s; 
            user-select: none; 
        }
        .menu-button:active, .level-button:active, .close-button:active, .popup-button:active, .choice-button:active { transform: translate(4px, 4px); box-shadow: 2px 2px 0 #000; }
        
        .menu-button, .level-button, .close-button, .popup-button {
            font-size: clamp(1.2rem, 4vw, 1.6rem); 
            padding: 15px 10px; 
            width: 100%; 
        }

        #secretButton {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 80px; /* A decent tappable area at the top */
            background-color: transparent;
            border: none;
            cursor: pointer;
            z-index: 10;
        }
        
        .secret-input {
            background-color: #222;
            border: 2px solid #fff;
            color: #fff;
            font-family: 'DotGothic16', sans-serif;
            padding: 10px;
            font-size: 1.2rem;
            text-align: center;
            width: 100%;
            box-sizing: border-box;
            margin-bottom: 15px;
        }


        #level1Button { color: var(--level1-color); } #level2Button { color: var(--level2-color); } #level3Button { color: var(--level3-color); }
        
        /* === バトル画面 === */
        #battleScreen { justify-content: flex-start; }
        .battle-container { width: 100%; max-width: 800px; height: 100%; display: flex; flex-direction: column; position: relative; }
        .battle-info-top { display: flex; justify-content: space-between; border: 4px solid #fff; padding: 10px; margin-bottom: 10px; background: rgba(0,0,0,0.7); align-items: center; }
        .status-box { flex-basis: 50%; text-align: left; } .exp-box { flex-basis: 45%; text-align: right; }
        .hp-bar-container, .exp-bar-container { height: 12px; border: 2px solid #fff; background: #333; margin-top: 5px; }
        .hp-bar { height: 100%; background: var(--hp-color); transition: width 0.3s; }
        .hp-bar.enemy { background: var(--hp-damage-color); }
        .exp-bar { height: 100%; background: var(--exp-color); transition: width 0.3s; }
        .exp-bar.max { animation: max-exp-glow 1s infinite alternate; }
        @keyframes max-exp-glow { from { box-shadow: 0 0 5px var(--exp-color); } to { box-shadow: 0 0 15px #fff, 0 0 20px var(--exp-color); } }
        .enemy-area { flex-grow: 1; display: flex; flex-direction: column; justify-content: center; align-items: center; position: relative; }
        #enemy-sprite { position: relative; transition: transform 0.1s; }
        #enemy-sprite.damaged { animation: enemy-shake 0.2s; }
        @keyframes enemy-shake { 50% { transform: translateX(10px); } }
        body.player-damaged { animation: screen-shake 0.3s; }
        @keyframes screen-shake { 0%,100%{transform:translateX(0)} 40%,80%{transform:translateX(-10px)} 20%,60%{transform:translateX(10px)} }
        .enemy-status { position: absolute; top: 10px; left: 10px; background: rgba(0,0,0,0.7); padding: 5px; }

        #question-box { border: 4px solid #fff; padding: 15px; margin-bottom: 10px; background: rgba(0,0,0,0.7); font-size: clamp(1.2rem, 4vw, 1.8rem); min-height: 50px; display: flex; justify-content: center; align-items: center; }
        #choices-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; }
        
        .choice-button { 
            font-size: clamp(0.9rem, 3vw, 1.3rem); 
            padding: 15px 5px; 
            white-space: nowrap; 
            overflow: hidden; 
            text-overflow: clip;
        }

        .choice-button:disabled { background-color: #222; color: #555; box-shadow: 2px 2px 0 #000; transform: translate(4px, 4px); }
        .choice-button.correct { background: var(--correct-color); color: #fff; }
        .choice-button.incorrect { background: var(--incorrect-color); }
        .choice-button.correct-answer { animation: flash-green 1s; }
        @keyframes flash-green { 50% { background: var(--correct-color); } }

        #battle-message-box { position: absolute; top: 30%; left: 50%; transform: translate(-50%,-50%); width: 90%; max-width: 600px; background: #000; color: #fff; border: 4px solid #fff; padding: 20px; z-index: 200; font-size: 1.5rem; }
        
        .damage-indicator { position: absolute; font-size: clamp(1.5rem, 5vw, 2.2rem); font-family: 'Press Start 2P', cursive; text-shadow: 2px 2px #000; pointer-events: none; animation: fade-up 1s forwards ease-out; }
        @keyframes fade-up { to { transform: translateY(-60px); opacity: 0; } }
        .damage-indicator.enemy { top: 0; left: 50%; transform: translateX(-50%); } 
        .damage-indicator.player { position: fixed; bottom: 25%; left: 50%; transform: translateX(-50%); }
        
        #pause-button { position: absolute; top: 130px; right: 15px; z-index: 100; cursor: pointer; }
        #pause-modal { position: absolute; top: 0; left: 0; z-index: 300; background: rgba(0,0,0,0.8); }
        .popup-content { background: #111; border: 4px solid #fff; padding: 20px; display: flex; flex-direction: column; gap: 15px; width: 90%; max-width: 380px; }
        .popup-content p { font-size: 1.2rem; margin: 0 0 10px 0; }
        .popup-buttons { display: flex; gap: 15px; }

        #level-up-overlay {
            position: fixed; top: 0; right: 0; bottom: 0; left: 0;
            align-items: center; justify-content: center; z-index: 500;
            pointer-events: none; background-color: rgba(0, 0, 0, 0.5);
        }
        .level-up-text {
            animation: level-up-anim 2.5s forwards;
            font-family: 'Press Start 2P', cursive;
            font-size: 6rem;
            color: #4ade80;
            text-shadow: 4px 4px 0 #000;
        }
        @keyframes level-up-anim {
            0% { opacity: 0; transform: scale(0.5); }
            20% { opacity: 1; transform: scale(1.2); }
            80% { opacity: 1; transform: scale(1); }
            100% { opacity: 0; transform: scale(1); }
        }
        #boss-warning-overlay { position: absolute; top: 50%; left: 50%; transform: translate(-50%,-50%); font-family: 'Press Start 2P', cursive; z-index: 400; font-size: clamp(4rem, 15vw, 8rem); animation: boss-warning-anim 2s forwards; }
        @keyframes boss-warning-anim {
            0%, 100% { opacity: 0; transform: translate(-50%, -50%) scale(2); }
            10%, 90% { opacity: 1; transform: translate(-50%, -50%) scale(1); }
            0%, 20%, 40%, 60%, 80% { color: var(--damage-color); text-shadow: 0 0 30px var(--damage-color); }
            10%, 30%, 50%, 70%, 90% { color: white; text-shadow: 0 0 20px #fff; }
        }
        
        #ritual-terop { background-color: transparent; z-index: 1000; cursor: pointer; }
        .terop-content { background-color: #000; border: 4px solid #000; padding: 20px; width: 90%; max-width: 600px; }
        .terop-content p { color: #ff0000; font-size: 1.3rem; margin: 0; line-height: 1.6; }

    </style>
</head>
<body>

    <div id="titleScreen" class="screen">
        <button id="secretButton"></button>
        <h1 class="title">英語王</h1>
        <div class="menu"><button id="attackButton" class="menu-button">単語アタック</button><button id="bookButton" class="menu-button">単語帳</button></div>
    </div>

    <div id="levelSelectScreen" class="screen hidden">
        <div class="level-select-menu">
            <button class="level-button" data-level="1">LEVEL 1</button><button class="level-button" data-level="2">LEVEL 2</button>
            <button class="level-button" data-level="3">LEVEL 3</button><button id="closeLevelSelect" class="close-button">閉じる</button>
        </div>
    </div>
    
    <div id="battleScreen" class="screen hidden">
        <div class="battle-container">
            <div id="pause-button">
                <svg width="40" height="40" viewBox="0 0 10 10" style="image-rendering: pixelated;"><path d="M2 2 h2 v6 h-2 z M6 2 h2 v6 h-2 z" fill="white"/></svg>
            </div>
            <div class="battle-info-top">
                <div class="status-box"><span>PLAYER LV:<span id="player-level">1</span></span><div>HP: <span id="player-hp">100</span>/<span id="player-max-hp">100</span></div><div class="hp-bar-container"><div id="player-hp-bar" class="hp-bar"></div></div></div>
                <div class="exp-box"><span>SCORE: <span id="score">0</span></span><br><span>EXP</span><div class="exp-bar-container"><div id="exp-bar" class="exp-bar"></div></div><span id="exp-text">0/6</span></div>
            </div>
            <div class="enemy-area"><div class="status-box enemy-status"><span><span id="enemy-name"></span></span><div>HP: <span id="enemy-hp"></span>/<span id="enemy-max-hp"></span></div><div class="hp-bar-container"><div id="enemy-hp-bar" class="hp-bar enemy"></div></div></div><div id="enemy-sprite"></div></div>
            <div id="question-box"><p id="question-word"></p></div>
            <div id="choices-grid">
                <button class="choice-button"></button><button class="choice-button"></button><button class="choice-button"></button>
                <button class="choice-button"></button><button class="choice-button"></button><button class="choice-button"></button>
            </div>
            <div id="boss-warning-overlay" class="hidden">BOSS</div>
        </div>
        <div id="battle-message-box" class="hidden"><p id="battle-message-text"></p></div>
        <div class="damage-indicator player"></div>
    </div>
    
    <div id="pause-modal" class="screen hidden">
        <div class="popup-content">
            <div id="pause-menu">
                <button id="quit-button" class="popup-button">クイズをやめる</button>
                <button id="resume-button" class="popup-button">閉じる</button>
            </div>
            <div id="quit-confirm" class="hidden">
                <p>本当にやめますか？</p>
                <div class="popup-buttons">
                    <button id="quit-no-button" class="popup-button">いいえ</button>
                    <button id="quit-yes-button" class="popup-button">はい</button>
                </div>
            </div>
        </div>
    </div>
    
    <div id="level-up-overlay" class="fixed inset-0 hidden items-center justify-center z-50 pointer-events-none bg-black bg-opacity-50">
        <h1 class="level-up-text">LEVEL UP!</h1>
    </div>

    <div id="wordbookModal" class="screen hidden">
        <!-- 省略しません -->
    </div>

    <div id="secretInputModal" class="screen hidden">
        <div class="popup-content">
            <input type="text" id="secretInput" class="secret-input" placeholder="入力">
            <div class="popup-buttons">
                <button id="secretEnterButton" class="popup-button">けってい</button>
                <button id="secretCloseButton" class="popup-button">とじる</button>
            </div>
        </div>
    </div>

    <div id="ritual-terop" class="screen hidden">
        <div class="terop-content">
            <p>あなたは儀式を成功させてしまいました。もう後戻りはできない。あなたは後悔することとなるだろう。</p>
        </div>
    </div>

    <script>
        const wordData = [
            // Level 1
            { word: 'abandon', meaning: '捨てる', level: 1 }, { word: 'accept', meaning: '受け入れる', level: 1 }, { word: 'accurate', meaning: '正確な', level: 1 }, { word: 'adapt', meaning: '適応する', level: 1 }, { word: 'admire', meaning: '称賛する', level: 1 }, { word: 'balance', meaning: '釣り合いをとる', level: 1 }, { word: 'belong', meaning: '所属する', level: 1 }, { word: 'benefit', meaning: '利益を得る', level: 1 }, { word: 'blame', meaning: '非難する', level: 1 }, { word: 'borrow', meaning: '借りる', level: 1 },
            { word: 'calculate', meaning: '計算する', level: 1 }, { word: 'capture', meaning: '捕らえる', level: 1 }, { word: 'cause', meaning: '引き起こす', level: 1 }, { word: 'celebrate', meaning: '祝う', level: 1 }, { word: 'compare', meaning: '比較する', level: 1 }, { word: 'decide', meaning: '決定する', level: 1 }, { word: 'deliver', meaning: '届ける', level: 1 }, { word: 'depend', meaning: '頼る', level: 1 }, { word: 'describe', meaning: '描写する', level: 1 }, { word: 'develop', meaning: '発展する', level: 1 },
            { word: 'educate', meaning: '教育する', level: 1 }, { word: 'encourage', meaning: '励ます', level: 1 }, { word: 'enjoy', meaning: '楽しむ', level: 1 }, { word: 'environmental', meaning: '環境の', level: 1 }, { word: 'establish', meaning: '設立する', level: 1 }, { word: 'fail', meaning: '失敗する', level: 1 }, { word: 'familiar', meaning: 'よく知られた', level: 1 }, { word: 'feature', meaning: '特徴づける', level: 1 }, { word: 'figure', meaning: '理解する', level: 1 }, { word: 'focus', meaning: '集中する', level: 1 },
            { word: 'gain', meaning: '得る', level: 1 }, { word: 'gather', meaning: '集める', level: 1 }, { word: 'general', meaning: '一般的な', level: 1 }, { word: 'guard', meaning: '守る', level: 1 }, { word: 'guess', meaning: '推測する', level: 1 }, { word: 'handle', meaning: '扱う', level: 1 }, { word: 'hesitate', meaning: 'ためらう', level: 1 }, { word: 'honest', meaning: '正直な', level: 1 }, { word: 'hopeful', meaning: '希望に満ちた', level: 1 }, { word: 'hurry', meaning: '急ぐ', level: 1 },
            { word: 'identify', meaning: '識別する', level: 1 }, { word: 'ignore', meaning: '無視する', level: 1 }, { word: 'imagine', meaning: '想像する', level: 1 }, { word: 'improve', meaning: '改善する', level: 1 }, { word: 'include', meaning: '含む', level: 1 }, { word: 'judge', meaning: '判断する', level: 1 }, { word: 'join', meaning: '参加する', level: 1 }, { word: 'journey', meaning: '旅する（比喩的にも）', level: 1 }, { word: 'justify', meaning: '正当化する', level: 1 }, { word: 'keep', meaning: '保つ', level: 1 },
            { word: 'lack', meaning: '欠けている', level: 1 }, { word: 'laughable', meaning: 'ばかげた', level: 1 }, { word: 'lead', meaning: '導く', level: 1 }, { word: 'limit', meaning: '制限する', level: 1 }, { word: 'likely', meaning: '〜しそうな', level: 1 }, { word: 'maintain', meaning: '維持する', level: 1 }, { word: 'manage', meaning: '管理する', level: 1 }, { word: 'mention', meaning: '言及する', level: 1 }, { word: 'mistake', meaning: '誤解する', level: 1 }, { word: 'modern', meaning: '現代的な', level: 1 },
            { word: 'notice', meaning: '気づく', level: 1 }, { word: 'necessary', meaning: '必要な', level: 1 }, { word: 'neither', meaning: 'どちらも〜ない', level: 1 }, { word: 'nervous', meaning: '緊張した', level: 1 }, { word: 'normal', meaning: '普通の', level: 1 }, { word: 'observe', meaning: '観察する', level: 1 }, { word: 'obtain', meaning: '得る', level: 1 }, { word: 'occur', meaning: '起こる', level: 1 }, { word: 'offer', meaning: '提供する', level: 1 }, { word: 'ordinary', meaning: '普通の', level: 1 },
            { word: 'participate', meaning: '参加する', level: 1 }, { word: 'particular', meaning: '特定の', level: 1 }, { word: 'peaceful', meaning: '平和な', level: 1 }, { word: 'perform', meaning: '演じる・行う', level: 1 }, { word: 'prefer', meaning: '好む', level: 1 }, { word: 'qualify', meaning: '資格を与える', level: 1 }, { word: 'quality', meaning: '質の良い', level: 1 }, { word: 'question', meaning: '疑問に思う', level: 1 }, { word: 'quiet', meaning: '静かな', level: 1 }, { word: 'quit', meaning: 'やめる', level: 1 },
            { word: 'realize', meaning: '気づく', level: 1 }, { word: 'receive', meaning: '受け取る', level: 1 }, { word: 'recommend', meaning: '勧める', level: 1 }, { word: 'reduce', meaning: '減らす', level: 1 }, { word: 'remain', meaning: '残る', level: 1 }, { word: 'satisfy', meaning: '満足させる', level: 1 }, { word: 'select', meaning: '選ぶ', level: 1 }, { word: 'serious', meaning: '真剣な', level: 1 }, { word: 'similar', meaning: '似ている', level: 1 }, { word: 'solve', meaning: '解く', level: 1 },
            { word: 'teach', meaning: '教える', level: 1 }, { word: 'tend', meaning: '傾向がある', level: 1 }, { word: 'treat', meaning: '扱う', level: 1 }, { word: 'trust', meaning: '信頼する', level: 1 }, { word: 'try', meaning: '試みる', level: 1 }, { word: 'understand', meaning: '理解する', level: 1 }, { word: 'update', meaning: '更新する', level: 1 }, { word: 'upset', meaning: '動揺させる', level: 1 }, { word: 'useful', meaning: '役立つ', level: 1 }, { word: 'usual', meaning: 'いつもの', level: 1 },
            { word: 'value', meaning: '評価する', level: 1 }, { word: 'vary', meaning: '変化する', level: 1 }, { word: 'visit', meaning: '訪れる', level: 1 }, { word: 'vote', meaning: '投票する', level: 1 }, { word: 'volunteer', meaning: '自ら進んで行う', level: 1 }, { word: 'warn', meaning: '警告する', level: 1 }, { word: 'waste', meaning: '浪費する', level: 1 }, { word: 'wonder', meaning: '不思議に思う', level: 1 }, { word: 'worry', meaning: '心配する', level: 1 }, { word: 'worth', meaning: '〜の価値がある', level: 1 },
            { word: 'yearn', meaning: '切望する', level: 1 }, { word: 'yell', meaning: '叫ぶ', level: 1 }, { word: 'yield', meaning: '（結果などを）生み出す／譲る', level: 1 }, { word: 'youthful', meaning: '若々しい', level: 1 }, { word: 'youngish', meaning: 'やや若い', level: 1 }, { word: 'zeal', meaning: '熱意', level: 1 }, { word: 'zealous', meaning: '熱心な', level: 1 }, { word: 'zero', meaning: 'ゼロにする（動詞）', level: 1 }, { word: 'zip', meaning: '勢いよく進む／圧縮する', level: 1 }, { word: 'zone', meaning: '区域に分ける', level: 1 },
            // Level 2
            { word: 'abandonment', meaning: '放棄', level: 2 }, { word: 'abstract', meaning: '抽象的な', level: 2 }, { word: 'accelerate', meaning: '加速する', level: 2 }, { word: 'accomplish', meaning: '成し遂げる', level: 2 }, { word: 'adaptable', meaning: '順応性のある', level: 2 }, { word: 'behavioral', meaning: '行動の', level: 2 }, { word: 'beneficial', meaning: '有益な', level: 2 }, { word: 'bothered', meaning: '悩まされた', level: 2 }, { word: 'broadly', meaning: '広く', level: 2 }, { word: 'burden', meaning: '負担', level: 2 },
            { word: 'calculate', meaning: '算出する（数学的に）', level: 2 }, { word: 'candidate', meaning: '候補者', level: 2 }, { word: 'capable', meaning: '有能な', level: 2 }, { word: 'careless', meaning: '不注意な', level: 2 }, { word: 'circumstance', meaning: '状況', level: 2 }, { word: 'decline', meaning: '減少する／断る', level: 2 }, { word: 'demonstrate', meaning: '実演する・証明する', level: 2 }, { word: 'determined', meaning: '決意した', level: 2 }, { word: 'distinguish', meaning: '区別する', level: 2 }, { word: 'diverse', meaning: '多様な', level: 2 },
            { word: 'efficient', meaning: '効率的な', level: 2 }, { word: 'eliminate', meaning: '除去する', level: 2 }, { word: 'emerge', meaning: '現れる', level: 2 }, { word: 'enable', meaning: '可能にする', level: 2 }, { word: 'ensure', meaning: '保証する', level: 2 }, { word: 'fascinate', meaning: '魅了する', level: 2 }, { word: 'flexible', meaning: '柔軟な', level: 2 }, { word: 'fortunate', meaning: '幸運な', level: 2 }, { word: 'fundamental', meaning: '基本的な', level: 2 }, { word: 'fulfill', meaning: '果たす', level: 2 },
            { word: 'generate', meaning: '生み出す', level: 2 }, { word: 'grateful', meaning: '感謝している', level: 2 }, { word: 'guarantee', meaning: '保証する', level: 2 }, { word: 'hesitation', meaning: 'ためらい', level: 2 }, { word: 'highlight', meaning: '強調する', level: 2 }, { word: 'ideal', meaning: '理想的な', level: 2 }, { word: 'illustrate', meaning: '説明する', level: 2 }, { word: 'imply', meaning: 'ほのめかす', level: 2 }, { word: 'indicate', meaning: '示す', level: 2 }, { word: 'influence', meaning: '影響を与える', level: 2 },
            { word: 'justify', meaning: '正当化する', level: 2 }, { word: 'keen', meaning: '熱心な', level: 2 }, { word: 'knowledgeable', meaning: '知識が豊富な', level: 2 }, { word: 'label', meaning: 'ラベルを付ける', level: 2 }, { word: 'lasting', meaning: '永続的な', level: 2 }, { word: 'maintainable', meaning: '維持できる', level: 2 }, { word: 'massive', meaning: '巨大な', level: 2 }, { word: 'measure', meaning: '測定する', level: 2 }, { word: 'modify', meaning: '修正する', level: 2 }, { word: 'mystery', meaning: '謎', level: 2 },
            { word: 'negotiate', meaning: '交渉する', level: 2 }, { word: 'notable', meaning: '注目すべき', level: 2 }, { word: 'notion', meaning: '概念', level: 2 }, { word: 'numerous', meaning: '多数の', level: 2 }, { word: 'nutritional', meaning: '栄養の', level: 2 }, { word: 'observe', meaning: '観察する', level: 2 }, { word: 'occupy', meaning: '占める', level: 2 }, { word: 'operate', meaning: '操作する', level: 2 }, { word: 'oppose', meaning: '反対する', level: 2 }, { word: 'outstanding', meaning: '傑出した', level: 2 },
            { word: 'perceive', meaning: '認識する', level: 2 }, { word: 'persuade', meaning: '説得する', level: 2 }, { word: 'precise', meaning: '正確な', level: 2 }, { word: 'previous', meaning: '以前の', level: 2 }, { word: 'priority', meaning: '優先事項', level: 2 }, { word: 'qualitative', meaning: '質的な', level: 2 }, { word: 'quantity', meaning: '量', level: 2 }, { word: 'questionable', meaning: '疑わしい', level: 2 }, { word: 'quitely', meaning: '静かに（quietlyの発展形的用法）', level: 2 }, { word: 'quotation', meaning: '引用', level: 2 },
            { word: 'recognize', meaning: '認識する', level: 2 }, { word: 'reflect', meaning: '反映する', level: 2 }, { word: 'regard', meaning: 'みなす', level: 2 }, { word: 'relate', meaning: '関係づける', level: 2 }, { word: 'replace', meaning: '置き換える', level: 2 }, { word: 'significant', meaning: '重要な', level: 2 }, { word: 'simultaneous', meaning: '同時の', level: 2 }, { word: 'sincere', meaning: '誠実な', level: 2 }, { word: 'specify', meaning: '明確にする', level: 2 }, { word: 'strengthen', meaning: '強化する', level: 2 },
            { word: 'temporary', meaning: '一時的な', level: 2 }, { word: 'tremendous', meaning: '途方もない', level: 2 }, { word: 'threaten', meaning: '脅す', level: 2 }, { word: 'tolerate', meaning: '我慢する', level: 2 }, { word: 'transfer', meaning: '移す', level: 2 }, { word: 'unite', meaning: '団結させる', level: 2 }, { word: 'universal', meaning: '普遍的な', level: 2 }, { word: 'urgent', meaning: '緊急の', level: 2 }, { word: 'utilize', meaning: '利用する', level: 2 }, { word: 'utter', meaning: '（声を）発する', level: 2 },
            { word: 'varying', meaning: '変化する', level: 2 }, { word: 'verbal', meaning: '言葉の', level: 2 }, { word: 'visible', meaning: '目に見える', level: 2 }, { word: 'vital', meaning: '極めて重要な', level: 2 }, { word: 'vivid', meaning: '生き生きとした', level: 2 }, { word: 'widespread', meaning: '広く行き渡った', level: 2 }, { word: 'worthwhile', meaning: '価値のある', level: 2 }, { word: 'weaken', meaning: '弱める', level: 2 }, { word: 'withdraw', meaning: '引き出す・撤退する', level: 2 }, { word: 'wonderful', meaning: '素晴らしい', level: 2 },
            { word: 'yielding', meaning: '柔軟な・従順な', level: 2 }, { word: 'youthfulness', meaning: '若々しさ', level: 2 }, { word: 'yearly', meaning: '年に一度の', level: 2 }, { word: 'yawn', meaning: 'あくびをする', level: 2 }, { word: 'yogic', meaning: 'ヨガの', level: 2 }, { word: 'zealousness', meaning: '熱心さ', level: 2 }, { word: 'zephyr', meaning: 'そよ風', level: 2 }, { word: 'zenith', meaning: '頂点', level: 2 }, { word: 'zero-sum', meaning: '得失ゼロの', level: 2 }, { word: 'zest', meaning: '熱意', level: 2 },
            // Level 3
            { word: 'abide', meaning: '我慢する／従う', level: 3 }, { word: 'abolish', meaning: '廃止する', level: 3 }, { word: 'abundant', meaning: '豊富な', level: 3 }, { word: 'accelerated', meaning: '加速された', level: 3 }, { word: 'acclaimed', meaning: '高く評価された', level: 3 }, { word: 'bewilder', meaning: '当惑させる', level: 3 }, { word: 'bizarre', meaning: '奇妙な', level: 3 }, { word: 'blunt', meaning: '鈍い／率直すぎる', level: 3 }, { word: 'boastful', meaning: '自慢好きな', level: 3 }, { word: 'brisk', meaning: '活発な', level: 3 },
            { word: 'cease', meaning: 'やめる', level: 3 }, { word: 'coherent', meaning: '筋の通った', level: 3 }, { word: 'collaborate', meaning: '協力する', level: 3 }, { word: 'compelling', meaning: '説得力のある', level: 3 }, { word: 'composed', meaning: '落ち着いた', level: 3 }, { word: 'dedicate', meaning: '捧げる', level: 3 }, { word: 'deliberate', meaning: '慎重な／熟考する', level: 3 }, { word: 'deteriorate', meaning: '悪化する', level: 3 }, { word: 'devastate', meaning: '壊滅させる', level: 3 }, { word: 'diminish', meaning: '減少させる', level: 3 },
            { word: 'elaborate', meaning: '手の込んだ／詳述する', level: 3 }, { word: 'endure', meaning: '耐える', level: 3 }, { word: 'enlighten', meaning: '啓発する', level: 3 }, { word: 'entail', meaning: '伴う', level: 3 }, { word: 'envision', meaning: '心に描く', level: 3 }, { word: 'flourish', meaning: '繁栄する', level: 3 }, { word: 'formidable', meaning: '手ごわな', level: 3 }, { word: 'frustrate', meaning: '挫折させる', level: 3 }, { word: 'futile', meaning: '無駄な', level: 3 }, { word: 'foster', meaning: '育成する', level: 3 },
            { word: 'gratify', meaning: '満足させる', level: 3 }, { word: 'grim', meaning: '険しい／厳しい', level: 3 }, { word: 'gripping', meaning: '心を奪うような', level: 3 }, { word: 'guileless', meaning: '純真な', level: 3 }, { word: 'guise', meaning: '見せかける（〜のふりをする）', level: 3 }, { word: 'hinder', meaning: '妨げる', level: 3 }, { word: 'humble', meaning: '謙虚な', level: 3 }, { word: 'hostile', meaning: '敵意のある', level: 3 }, { word: 'hypothetical', meaning: '仮定の', level: 3 }, { word: 'heedless', meaning: '不注意な', level: 3 },
            { word: 'illustrative', meaning: '説明的な', level: 3 }, { word: 'immense', meaning: '非常に大きい', level: 3 }, { word: 'imminent', meaning: '差し迫った', level: 3 }, { word: 'imperative', meaning: '非常に重要な', level: 3 }, { word: 'impartial', meaning: '公平な', level: 3 }, { word: 'jeopardize', meaning: '危険にさらす', level: 3 }, { word: 'jubilant', meaning: '大喜びの', level: 3 }, { word: 'judicious', meaning: '賢明な', level: 3 }, { word: 'justifiable', meaning: '正当化できる', level: 3 }, { word: 'juvenile', meaning: '未熟な／若者の', level: 3 },
            { word: 'keen-eyed', meaning: '目ざとい', level: 3 }, { word: 'knowledge-seeking', meaning: '知識を求める', level: 3 }, { word: 'knotted', meaning: '複雑に絡んだ', level: 3 }, { word: 'kinetic', meaning: '運動の', level: 3 }, { word: 'kindhearted', meaning: '心の優しい', level: 3 }, { word: 'lament', meaning: '悲しむ', level: 3 }, { word: 'legitimate', meaning: '正当な', level: 3 }, { word: 'lingering', meaning: '長引く', level: 3 }, { word: 'lofty', meaning: '高尚な', level: 3 }, { word: 'lucid', meaning: '明快な', level: 3 },
            { word: 'manipulate', meaning: '操る', level: 3 }, { word: 'meticulous', meaning: '細心の注意を払う', level: 3 }, { word: 'momentous', meaning: '重大な', level: 3 }, { word: 'mournful', meaning: '悲しみに満ちた', level: 3 }, { word: 'mundane', meaning: '平凡な', level: 3 }, { word: 'negligent', meaning: '怠慢な', level: 3 }, { word: 'noteworthy', meaning: '注目に値する', level: 3 }, { word: 'novel', meaning: '斬新な', level: 3 }, { word: 'nurture', meaning: '育てる', level: 3 }, { word: 'neutralize', meaning: '中和する', level: 3 },
            { word: 'oblivious', meaning: '気づかない', level: 3 }, { word: 'obsolete', meaning: '時代遅れの', level: 3 }, { word: 'omit', meaning: '省略する', level: 3 }, { word: 'oppressive', meaning: '過酷な', level: 3 }, { word: 'outspoken', meaning: '率直な', level: 3 }, { word: 'perplex', meaning: '困惑させる', level: 3 }, { word: 'plausible', meaning: 'もっともらしい', level: 3 }, { word: 'predominant', meaning: '支配的な', level: 3 }, { word: 'prevalent', meaning: '広く行き渡った', level: 3 }, { word: 'provoke', meaning: '引き起こす', level: 3 },
            { word: 'quench', meaning: '抑える／（渇きを）癒す', level: 3 }, { word: 'quizzical', meaning: 'いぶかしげな', level: 3 }, { word: 'quaint', meaning: '古風で趣のある', level: 3 }, { word: 'qualm', meaning: '不安を感じる', level: 3 }, { word: 'quarrelsome', meaning: 'けんか好きな', level: 3 }, { word: 'rebuke', meaning: '非難する', level: 3 }, { word: 'refrain', meaning: '控える', level: 3 }, { word: 'relinquish', meaning: '放棄する', level: 3 }, { word: 'resilient', meaning: '回復力のある', level: 3 }, { word: 'rigid', meaning: '厳格な', level: 3 },
            { word: 'sophisticated', meaning: '洗練された', level: 3 }, { word: 'speculative', meaning: '推測の', level: 3 }, { word: 'substantial', meaning: 'かなりの／本質的な', level: 3 }, { word: 'succumb', meaning: '屈する', level: 3 }, { word: 'surpass', meaning: '超える', level: 3 }, { word: 'tangible', meaning: '明確な／触れられる', level: 3 }, { word: 'thrive', meaning: '繁栄する', level: 3 }, { word: 'tranquil', meaning: '穏やかな', level: 3 }, { word: 'tedious', meaning: '退屈な', level: 3 }, { word: 'timid', meaning: '臆病な', level: 3 },
            { word: 'ultimate', meaning: '究極の', level: 3 }, { word: 'unprecedented', meaning: '前例のない', level: 3 }, { word: 'upright', meaning: '誠実な／直立した', level: 3 }, { word: 'utilitarian', meaning: '実用的な', level: 3 }, { word: 'unyielding', meaning: '頑固な', level: 3 }, { word: 'versatile', meaning: '多才な', level: 3 }, { word: 'vigorous', meaning: '精力的な', level: 3 }, { word: 'vulnerable', meaning: '傷つきやすい', level: 3 }, { word: 'vindicate', meaning: '潔白を証明する', level: 3 }, { word: 'vividly', meaning: '鮮やかに', level: 3 },
            { word: 'wither', meaning: 'しおれる', level: 3 }, { word: 'withdrawn', meaning: '内向的な', level: 3 }, { word: 'witty', meaning: '機知に富んだ', level: 3 }, { word: 'willful', meaning: '意図的な', level: 3 }, { word: 'wistful', meaning: 'もの悲しい', level: 3 }, { word: 'yearning', meaning: '切望している', level: 3 }, { word: 'yieldless', meaning: '譲らない', level: 3 }, { word: 'yonder', meaning: '向こうの', level: 3 }, { word: 'yawning', meaning: '退屈な／大きく開いた', level: 3 }, { word: 'youth-deprived', meaning: '若さを失った', level: 3 },
            { word: 'zealous', meaning: '熱狂的な', level: 3 }, { word: 'zestful', meaning: '熱意に満ちた', level: 3 }, { word: 'zonal', meaning: '帯状の', level: 3 }, { word: 'zenlike', meaning: '穏やかで静かな', level: 3 },
        ];

        const enemySprites = {
            "スライム": `<svg width="80" height="60" viewBox="0 0 20 15" style="transform: scale(4); image-rendering: pixelated;"><path d="M7 3 h6 v1 h-6 z M6 4 h8 v1 h-8 z M5 5 h10 v1 h-10 z M4 6 h12 v1 h-12 z M3 7 h14 v1 h-14 z M4 8 h12 v1 h-12 z M5 9 h10 v1 h-10 z" fill="#67E8F9"/></svg>`,
            "ゴブリン": `<svg width="80" height="64" viewBox="0 0 20 16" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 3 h4 v1 h-4 z M7 4 h6 v1 h-6 z M6 5 h8 v1 h-8 z M5 6 h1 v1 h1 v1 h4 v-1 h1 v-1 h1 v3 h-1 v1 h-1 v1 h1 v1 h-1 v1 h-6 v-1 h-1 v-1 h-1 v-3 z M9 9 h2 v1 h-2 z M6 13 h8 v1 h-8 z" fill="#4ADE80"/></svg>`,
            "魔王": `<svg width="96" height="80" viewBox="0 0 24 20" style="transform: scale(4); image-rendering: pixelated;"><path d="M9 2 h6 v1 h-6 z M8 3 h8 v1 h-8 z M7 4 h10 v1 h-10 z M6 5 h12 v1 h-12 z M5 6 h1 v1 h12 v-1 h1 v3 h-1 v1 h-1 v1 h-1 v1 h1 v1 h-1 v1 h-8 v-1 h-1 v-1 h1 v-1 h-1 v-1 h-1 v-1 h-1 z M11 11 h2 v1 h-2 z M8 15 h8 v1 h-8 z" fill="#A78BFA"/></svg>`,
            "スライムα": `<svg width="80" height="60" viewBox="0 0 20 15" style="transform: scale(4); image-rendering: pixelated;"><path d="M7 3 h6 v1 h-6 z M6 4 h8 v1 h-8 z M5 5 h10 v1 h-10 z M4 6 h12 v1 h-12 z M3 7 h14 v1 h-14 z M4 8 h12 v1 h-12 z M5 9 h10 v1 h-10 z" fill="#4ADE80"/></svg>`,
            "ゴブリンα": `<svg width="80" height="64" viewBox="0 0 20 16" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 3 h4 v1 h-4 z M7 4 h6 v1 h-6 z M6 5 h8 v1 h-8 z M5 6 h1 v1 h1 v1 h4 v-1 h1 v-1 h1 v3 h-1 v1 h-1 v1 h1 v1 h-1 v1 h-6 v-1 h-1 v-1 h-1 v-3 z M9 9 h2 v1 h-2 z M6 13 h8 v1 h-8 z" fill="#EF4444"/></svg>`,
            "悪魔之王": `<svg width="96" height="80" viewBox="0 0 24 20" style="transform: scale(4); image-rendering: pixelated;"><path d="M4 5 h1 v-1 h1 v-1 h1 v-1 h1 v-1 h1 v1 h1 v1 h4 v-1 h1 v-1 h1 v1 h1 v1 h1 v1 h1 v1 h-1 v1 h-1 v1 h-1 v1 h-1 v1 h-1 v1 h-1 v-1 h-4 v1 h-1 v-1 h-1 v-1 h-1 v-1 h-1 v-1 h-1 z M11 11 h2 v1 h-2 z M8 15 h8 v1 h-8 z" fill="#8B5CF6"/></svg>`,
            "スケルトン": `<svg width="80" height="64" viewBox="0 0 20 16" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 3 h4 v1 h-4 z M7 4 h6 v1 h-6 z M6 5 h8 v2 h-1 v-1 h-1 v1 h-4 v-1 h-1 v1 h-1 z M9 6 h2 v1 h-2 z M7 8 h6 v1 h-1 v1 h-1 v1 h-2 v-1 h-1 v-1 h-1 z M7 12 h6 v1 h-6 z M8 13 h1 v1 h-1 z M11 13 h1 v1 h-1 z" fill="#E5E7EB"/></svg>`,
            "ゴブリンβ": `<svg width="80" height="64" viewBox="0 0 20 16" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 3 h4 v1 h-4 z M7 4 h6 v1 h-6 z M6 5 h8 v1 h-8 z M5 6 h1 v1 h1 v1 h4 v-1 h1 v-1 h1 v3 h-1 v1 h-1 v1 h1 v1 h-1 v1 h-6 v-1 h-1 v-1 h-1 v-3 z M9 9 h2 v1 h-2 z M6 13 h8 v1 h-8 z" fill="#A78BFA"/></svg>`,
            "スライムβ": `<svg width="80" height="60" viewBox="0 0 20 15" style="transform: scale(4); image-rendering: pixelated;"><path d="M7 3 h6 v1 h-6 z M6 4 h8 v1 h-8 z M5 5 h10 v1 h-10 z M4 6 h12 v1 h-12 z M3 7 h14 v1 h-14 z M4 8 h12 v1 h-12 z M5 9 h10 v1 h-10 z" fill="#F87171"/></svg>`,
            "邪神 ルミナス": `<svg width="120" height="96" viewBox="0 0 30 24" style="transform: scale(4); image-rendering: pixelated;"><path d="M11 4 h8 v1 h-8 z M10 5 h10 v1 h-10 z M9 6 h12 v1 h-12 z M8 7 h14 v1 h-14 z M7 8 h16 v8 h-16 z M8 16 h14 v1 h-14 z M9 17 h12 v1 h-12 z M10 18 h10 v1 h-10 z M11 19 h8 v1 h-8 z" fill="#DC2626"/><path d="M14 6 h2 v1 h-2 z M13 7 h4 v1 h-4 z M12 8 h6 v1 h-6 z M11 9 h8 v1 h-1 v1 h-6 v-1 h-1 z M12 11 h1 v4 h-1 z M17 11 h1 v4 h-1 z M13 12 h4 v1 h-4 z M11 16 h8 v1 h-8 z M10 17 h10 v1 h-10 z" fill="#8B5CF6"/></svg>`,
            "スライムγ": `<svg width="80" height="60" viewBox="0 0 20 15" style="transform: scale(4); image-rendering: pixelated;"><path d="M7 3 h6 v1 h-6 z M6 4 h8 v1 h-8 z M5 5 h10 v1 h-10 z M4 6 h12 v1 h-12 z M3 7 h14 v1 h-14 z M4 8 h12 v1 h-12 z M5 9 h10 v1 h-10 z" fill="#FFFFFF"/></svg>`,
            "ゴブリンγ": `<svg width="80" height="64" viewBox="0 0 20 16" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 3 h4 v1 h-4 z M7 4 h6 v1 h-6 z M6 5 h8 v1 h-8 z M5 6 h1 v1 h1 v1 h4 v-1 h1 v-1 h1 v3 h-1 v1 h-1 v1 h1 v1 h-1 v1 h-6 v-1 h-1 v-1 h-1 v-3 z M9 9 h2 v1 h-2 z M6 13 h8 v1 h-8 z" fill="#881337"/></svg>`,
            "スケルトンα": `<svg width="80" height="64" viewBox="0 0 20 16" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 3 h4 v1 h-4 z M7 4 h6 v1 h-6 z M6 5 h8 v2 h-1 v-1 h-1 v1 h-4 v-1 h-1 v1 h-1 z M9 6 h2 v1 h-2 z M7 8 h6 v1 h-1 v1 h-1 v1 h-2 v-1 h-1 v-1 h-1 z M7 12 h6 v1 h-6 z M8 13 h1 v1 h-1 z M11 13 h1 v1 h-1 z" fill="#DC2626"/></svg>`,
            "閻魔大王": `<svg width="80" height="100" viewBox="0 0 20 25" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 0 h4 v1 h-4 z M7 1 h6 v1 h-6 z M6 2 h8 v1 h-8 z M5 3 h10 v1 h-10 z" fill="#8B4513"/><path d="M7 1 h1 v1 h-1 z M12 1 h1 v1 h-1 z" fill="#FFD700"/><path d="M9 1 h2 v1 h-2 z" fill="#FFD700"/><path d="M5 4 h10 v1 h-10 z M4 5 h12 v1 h-12 z M3 6 h14 v1 h-14 z M3 7 h14 v5 h-14 z" fill="#B22222"/><path d="M6 7 h2 v1 h-2 z M12 7 h2 v1 h-2 z" fill="#FFD700"/><path d="M6 6 h2 v1 h-2 z M12 6 h2 v1 h-2 z" fill="#000000"/><path d="M9 8 h2 v1 h-2 z" fill="#B22222"/><path d="M6 10 h8 v1 h-8 z M7 11 h1 v1 h-1 z M13 11 h1 v1 h-1 z" fill="#000000"/><path d="M8 11 h1 v1 h-1 z M11 11 h1 v1 h-1 z" fill="#FFFFFF"/><path d="M4 12 h12 v1 h-12 z M3 13 h14 v1 h-14 z M2 14 h16 v1 h-16 z M2 15 h16 v2 h-16 z" fill="#800080"/><path d="M3 15 h1 v1 h-1 z M15 15 h1 v1 h-1 z" fill="#FFD700"/><path d="M4 17 h12 v1 h-12 z M5 18 h10 v1 h-10 z M6 19 h8 v1 h-8 z" fill="#800080"/><path d="M1 14 h1 v2 h-1 z M17 14 h1 v2 h-1 z" fill="#FECACA"/><path d="M0 16 h2 v1 h-2 z M17 16 h2 v1 h-2 z" fill="#800080"/><path d="M0 17 h1 v1 h-1 z M18 17 h1 v1 h-1 z" fill="#FECACA"/></svg>`,
            "キングスライム":`<svg width="100" height="100" viewBox="0 0 25 25" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 7 h9 v1 h-9 z M7 8 h11 v1 h-11 z M6 9 h13 v1 h-13 z M5 10 h15 v1 h-15 z M4 11 h17 v1 h-17 z M3 12 h19 v1 h-19 z M2 13 h21 v2 h-21 z M3 15 h19 v1 h-19 z M4 16 h17 v1 h-17 z M5 17 h15 v1 h-15 z" fill="#800080"/><path d="M10 5 h5 v1 h-5 z M9 6 h1 v1 h-1 z M11 6 h3 v1 h-3 z M15 6 h1 v1 h-1 z" fill="#FFD700"/><path d="M8 11 h1 v1 h-1z M9 12 h1 v1 h-1z M16 11 h1 v1 h-1z M15 12 h1 v1 h-1z" fill="#FF0000"/></svg>`,
            "シャドウ": `<svg width="80" height="80" viewBox="0 0 20 20" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 4 h4 v1 h-4 z M7 5 h6 v1 h-6 z M6 6 h8 v1 h-8 z M5 7 h10 v5 h-1 v1 h-1 v1 h-6 v-1 h-1 v-1 h-1 z M4 13 h1 v1 h-1 z M15 13 h1 v1 h-1 z M5 14 h2 v1 h-2 z M13 14 h2 v1 h-2 z M7 15 h6 v1 h-6 z" fill="#581c87"/><path d="M7 8 h1 v1 h-1z M8 9 h1 v1 h-1z M13 8 h1 v1 h-1z M12 9 h1 v1 h-1z" fill="#FF0000"/></svg>`,
            "ゴーレム": `<svg width="96" height="96" viewBox="0 0 24 24" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 4 h8 v2 h-8 z M7 6 h10 v2 h-10 z M6 8 h12 v6 h-12 z" fill="#71717a"/><path d="M6 14 h4 v6 h-4 z M14 14 h4 v6 h-4 z" fill="#71717a"/><path d="M4 8 h2 v4 h-2 z M18 8 h2 v4 h-2 z" fill="#a1a1aa"/><path d="M9 10 h2 v2 h-2 z M13 10 h2 v2 h-2 z" fill="#38bdf8"/></svg>`,
            "Blood Slime": `<svg width="80" height="60" viewBox="0 0 20 15" style="transform: scale(4); image-rendering: pixelated;"><path d="M7 3 h6 v1 h-6 z M6 4 h8 v1 h-8 z M5 5 h10 v1 h-10 z M4 6 h12 v1 h-12 z M3 7 h14 v1 h-14 z M4 8 h12 v1 h-12 z M5 9 h10 v1 h-10 z" fill="#FF0000"/></svg>`,
            "Blood Goblin": `<svg width="80" height="64" viewBox="0 0 20 16" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 3 h4 v1 h-4 z M7 4 h6 v1 h-6 z M6 5 h8 v1 h-8 z M5 6 h1 v1 h1 v1 h4 v-1 h1 v-1 h1 v3 h-1 v1 h-1 v1 h1 v1 h-1 v1 h-6 v-1 h-1 v-1 h-1 v-3 z M9 9 h2 v1 h-2 z M6 13 h8 v1 h-8 z" fill="#FF0000"/></svg>`,
            "Blood Skeleton": `<svg width="80" height="64" viewBox="0 0 20 16" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 3 h4 v1 h-4 z M7 4 h6 v1 h-6 z M6 5 h8 v2 h-1 v-1 h-1 v1 h-4 v-1 h-1 v1 h-1 z M9 6 h2 v1 h-2 z M7 8 h6 v1 h-1 v1 h-1 v1 h-2 v-1 h-1 v-1 h-1 z M7 12 h6 v1 h-6 z M8 13 h1 v1 h-1 z M11 13 h1 v1 h-1 z" fill="#FF0000"/></svg>`,
            "Blood Golem": `<svg width="96" height="96" viewBox="0 0 24 24" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 4 h8 v2 h-8 z M7 6 h10 v2 h-10 z M6 8 h12 v6 h-12 z" fill="#FF0000"/><path d="M6 14 h4 v6 h-4 z M14 14 h4 v6 h-4 z" fill="#FF0000"/><path d="M4 8 h2 v4 h-2 z M18 8 h2 v4 h-2 z" fill="#FF0000"/><path d="M9 10 h2 v2 h-2 z M13 10 h2 v2 h-2 z" fill="#8A0707"/></svg>`,
            "Blood Shadow": `<svg width="80" height="80" viewBox="0 0 20 20" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 4 h4 v1 h-4 z M7 5 h6 v1 h-6 z M6 6 h8 v1 h-8 z M5 7 h10 v5 h-1 v1 h-1 v1 h-6 v-1 h-1 v-1 h-1 z M4 13 h1 v1 h-1 z M15 13 h1 v1 h-1 z M5 14 h2 v1 h-2 z M13 14 h2 v1 h-2 z M7 15 h6 v1 h-6 z" fill="#8A0707"/><path d="M7 8 h1 v1 h-1z M8 9 h1 v1 h-1z M13 8 h1 v1 h-1z M12 9 h1 v1 h-1z" fill="#FF0000"/></svg>`,
            "Blood Lord": `<svg width="96" height="80" viewBox="0 0 24 20" style="transform: scale(4); image-rendering: pixelated;"><path d="M9 2 h6 v1 h-6 z M8 3 h8 v1 h-8 z M7 4 h10 v1 h-10 z M6 5 h12 v1 h-12 z M5 6 h1 v1 h12 v-1 h1 v3 h-1 v1 h-1 v1 h-1 v1 h1 v1 h-1 v1 h-8 v-1 h-1 v-1 h1 v-1 h-1 v-1 h-1 v-1 h-1 z M11 11 h2 v1 h-2 z M8 15 h8 v1 h-8 z" fill="#FF0000"/></svg>`,
            "Blood Devil-King": `<svg width="96" height="80" viewBox="0 0 24 20" style="transform: scale(4); image-rendering: pixelated;"><path d="M4 5 h1 v-1 h1 v-1 h1 v-1 h1 v-1 h1 v1 h1 v1 h4 v-1 h1 v-1 h1 v1 h1 v1 h1 v1 h1 v1 h-1 v1 h-1 v1 h-1 v1 h-1 v1 h-1 v1 h-1 v-1 h-4 v1 h-1 v-1 h-1 v-1 h-1 v-1 h-1 v-1 h-1 z M11 11 h2 v1 h-2 z M8 15 h8 v1 h-8 z" fill="#FF0000"/></svg>`,
            "Blood Luminous": `<svg width="120" height="96" viewBox="0 0 30 24" style="transform: scale(4); image-rendering: pixelated;"><path d="M11 4 h8 v1 h-8 z M10 5 h10 v1 h-10 z M9 6 h12 v1 h-12 z M8 7 h14 v1 h-14 z M7 8 h16 v8 h-16 z M8 16 h14 v1 h-14 z M9 17 h12 v1 h-12 z M10 18 h10 v1 h-10 z M11 19 h8 v1 h-8 z" fill="#DC2626"/><path d="M14 6 h2 v1 h-2 z M13 7 h4 v1 h-4 z M12 8 h6 v1 h-6 z M11 9 h8 v1 h-1 v1 h-6 v-1 h-1 z M12 11 h1 v4 h-1 z M17 11 h1 v4 h-1 z M13 12 h4 v1 h-4 z M11 16 h8 v1 h-8 z M10 17 h10 v1 h-10 z" fill="#8A0707"/></svg>`,
            "Blood Enma": `<svg width="80" height="100" viewBox="0 0 20 25" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 0 h4 v1 h-4 z M7 1 h6 v1 h-6 z M6 2 h8 v1 h-8 z M5 3 h10 v1 h-10 z" fill="#8B0000"/><path d="M7 1 h1 v1 h-1 z M12 1 h1 v1 h-1 z" fill="#FFD700"/><path d="M9 1 h2 v1 h-2 z" fill="#FFD700"/><path d="M5 4 h10 v1 h-10 z M4 5 h12 v1 h-12 z M3 6 h14 v1 h-14 z M3 7 h14 v5 h-14 z" fill="#8A0707"/><path d="M6 7 h2 v1 h-2 z M12 7 h2 v1 h-2 z" fill="#FFD700"/><path d="M6 6 h2 v1 h-2 z M12 6 h2 v1 h-2 z" fill="#000000"/><path d="M9 8 h2 v1 h-2 z" fill="#B22222"/><path d="M6 10 h8 v1 h-8 z M7 11 h1 v1 h-1 z M13 11 h1 v1 h-1 z" fill="#000000"/><path d="M8 11 h1 v1 h-1 z M11 11 h1 v1 h-1 z" fill="#FF0000"/><path d="M4 12 h12 v1 h-12 z M3 13 h14 v1 h-14 z M2 14 h16 v1 h-16 z M2 15 h16 v2 h-16 z" fill="#7C0A02"/><path d="M3 15 h1 v1 h-1 z M15 15 h1 v1 h-1 z" fill="#FFD700"/><path d="M4 17 h12 v1 h-12 z M5 18 h10 v1 h-10 z M6 19 h8 v1 h-8 z" fill="#600000"/><path d="M1 14 h1 v2 h-1 z M17 14 h1 v2 h-1 z" fill="#B22222"/><path d="M0 16 h2 v1 h-2 z M17 16 h2 v1 h-2 z" fill="#7C0A02"/><path d="M0 17 h1 v1 h-1 z M18 17 h1 v1 h-1 z" fill="#8B0000"/></svg>`,
            "Blood King Slime": `<svg width="100" height="100" viewBox="0 0 25 25" style="transform: scale(4); image-rendering: pixelated;"><path d="M8 7 h9 v1 h-9 z M7 8 h11 v1 h-11 z M6 9 h13 v1 h-13 z M5 10 h15 v1 h-15 z M4 11 h17 v1 h-17 z M3 12 h19 v1 h-19 z M2 13 h21 v2 h-21 z M3 15 h19 v1 h-19 z M4 16 h17 v1 h-17 z M5 17 h15 v1 h-15 z" fill="#8A0707"/><path d="M10 5 h5 v1 h-5 z M9 6 h1 v1 h-1 z M11 6 h3 v1 h-3 z M15 6 h1 v1 h-1 z" fill="#FFD700"/><path d="M8 11 h1 v1 h-1z M9 12 h1 v1 h-1z M16 11 h1 v1 h-1z M15 12 h1 v1 h-1z" fill="#FF0000"/></svg>`
        };
        
        const dom = {
            titleScreen: document.getElementById('titleScreen'), levelSelectScreen: document.getElementById('levelSelectScreen'), battleScreen: document.getElementById('battleScreen'),
            player: { level: document.getElementById('player-level'), hp: document.getElementById('player-hp'), maxHp: document.getElementById('player-max-hp'), hpBar: document.getElementById('player-hp-bar') },
            exp: { bar: document.getElementById('exp-bar'), text: document.getElementById('exp-text') }, score: document.getElementById('score'),
            enemy: { name: document.getElementById('enemy-name'), hp: document.getElementById('enemy-hp'), maxHp: document.getElementById('enemy-max-hp'), hpBar: document.getElementById('enemy-hp-bar'), sprite: document.getElementById('enemy-sprite') },
            quiz: { word: document.getElementById('question-word'), grid: document.getElementById('choices-grid'), buttons: document.querySelectorAll('.choice-button') },
            message: { box: document.getElementById('battle-message-box'), text: document.getElementById('battle-message-text') },
            damage: { player: document.querySelector('.damage-indicator.player') },
            pause: { button: document.getElementById('pause-button'), modal: document.getElementById('pause-modal'), menu: document.getElementById('pause-menu'), confirm: document.getElementById('quit-confirm') },
            levelUpOverlay: document.getElementById('level-up-overlay'),
            bossWarning: document.getElementById('boss-warning-overlay'),
            secret: {
                button: document.getElementById('secretButton'),
                modal: document.getElementById('secretInputModal'),
                input: document.getElementById('secretInput'),
                enterButton: document.getElementById('secretEnterButton'),
                closeButton: document.getElementById('secretCloseButton')
            },
            ritualTerop: document.getElementById('ritual-terop')
        };

        let playerStatus = {}, enemyStatus = {}, currentQuestion = {}, quizWords = [];
        let isAnswering = false, isPaused = false, currentQuizLevel = 1, enemyDefeatedCount = 0, score = 0, correctStreak = 0, correctAnswersCount = 0, bossEncounterCount = 0, isMaohDefeatedOnce = false, isAkumaDefeatedOnce = false, isLuminusDefeatedOnce = false;
        let isRitualMode = false;

        const consts = {
            expTable: {}, 
            playerHpTable: {},
            enemyHpTable: {
                1:{s:[10,15],g:[15,20]}, 2:{s:[12,15],g:[16,21]}, 3:{s:[14,20],g:[20,30]}, 4:{s:[18,28],g:[25,36]}, 5:{s:[20,30],g:[30,45]},
                6:{s:[25,35],g:[35,50]}, 7:{s:[30,40],g:[40,55]}, 8:{s:[35,45],g:[45,60]}, 9:{s:[40,50],g:[50,65]}, 10:{s:[50,60],g:[60,75]}
            },
            bossHpTable: {
                "魔王": { 1:30, 2:42, 3:55, 4:62, 5:66 }, "悪魔之王": { 1:57, 2:83, 3:102, 4:122, 5:149 },
                "邪神 ルミナス": { 1:63, 2:94, 3:113, 4:142, 5:162 }, "閻魔大王": { 1:80, 2:110, 3:145, 4:180, 5:215 },
                "キングスライム": {1:100, 2:130, 3:165, 4:200, 5:240}
            },
            advancedEnemyHpTable: {
                1:{sa:[20,25],ga:[25,30],sb:[25,30],gb:[30,35],sk:[30,35],ska:[45,60],sg:[30,40],gg:[35,45],sh:[55,75],go:[60,80]}, 
                2:{sa:[25,40],ga:[30,55],sb:[30,45],gb:[35,60],sk:[40,60],ska:[55,75],sg:[40,55],gg:[45,70],sh:[65,90],go:[75,95]}, 
                3:{sa:[35,55],ga:[40,68],sb:[40,60],gb:[45,75],sk:[50,70],ska:[65,85],sg:[50,70],gg:[55,90],sh:[80,105],go:[90,115]}, 
                4:{sa:[45,70],ga:[45,80],sb:[50,75],gb:[50,85],sk:[60,80],ska:[75,95],sg:[60,85],gg:[65,110],sh:[90,120],go:[100,130]}, 
                5:{sa:[55,70],ga:[65,100],sb:[60,80],gb:[70,110],sk:[70,90],ska:[85,105],sg:[70,95],gg:[80,125],sh:[100,135],go:[115,150]}
            },
            bloodEnemyHpTable: {
                1: { s: [45,60], g: [55,70], sk: [65,85], go: [75,95], sh: [85,105] }, 2: { s: [60,75], g: [70,85], sk: [80,100], go: [90,110], sh: [100,125] },
                3: { s: [70,90], g: [85,100], sk: [90,115], go: [100,125], sh: [120,145] }, 4: { s: [80,105], g: [100,120], sk: [100,130], go: [120,145], sh: [135,160] },
                5: { s: [90,120], g: [115,135], sk: [110,145], go: [130,160], sh: [150,180] }
            },
            bloodBossHpTable: {
                "Blood Lord": { 1: 120, 2: 150, 3: 180, 4: 210, 5: 240 }, "Blood Devil-King": { 1: 160, 2: 190, 3: 230, 4: 260, 5: 300 },
                "Blood Luminous": { 1: 190, 2: 220, 3: 260, 4: 295, 5: 330 }, "Blood Enma": { 1: 220, 2: 260, 3: 300, 4: 340, 5: 380 },
                "Blood King Slime": { 1: 270, 2: 320, 3: 370, 4: 420, 5: 470 }
            },
            bloodBossAttackLimits: { "Blood Lord": 151, "Blood Devil-King": 173, "Blood Luminous": 183, "Blood Enma": 201, "Blood King Slime": 213 },
            bossList: ["魔王", "悪魔之王", "邪神 ルミナス", "閻魔大王", "キングスライム", "Blood Lord", "Blood Devil-King", "Blood Luminous", "Blood Enma", "Blood King Slime"],
            expGains: {
                "スライム": { attack: 1, defeat: 3 }, "ゴブリン": { attack: 2, defeat: 5 }, "スライムα": { attack: 2, defeat: 4 }, "ゴブリンα": { attack: 3, defeat: 6 },
                "魔王": { attack: 4, defeat: 20 }, "悪魔之王": { attack: 5, defeat: 50 }, "スライムβ": { attack: 3, defeat: 15 }, "ゴブリンβ": { attack: 5, defeat: 25 },
                "スケルトン": { attack: 5, defeat: 20 }, "邪神 ルミナス": { attack: 10, defeat: 100 }, "スケルトンα": { attack: 6, defeat: 25 }, "スライムγ": { attack: 4, defeat: 20 },
                "ゴブリンγ": { attack: 6, defeat: 30 }, "閻魔大王": { attack: 15, defeat: 150 }, "キングスライム": {attack: 20, defeat: 200}, "シャドウ": {attack: 7, defeat: 40}, "ゴーレム": {attack: 8, defeat: 45},
                "Blood Slime": { attack: 6, defeat: 13 }, "Blood Goblin": { attack: 6, defeat: 17 }, "Blood Skeleton": { attack: 6, defeat: 17 }, "Blood Golem": { attack: 6, defeat: 19 }, "Blood Shadow": { attack: 6, defeat: 17 },
                "Blood Lord": { attack: 13, defeat: 67 }, "Blood Devil-King": { attack: 13, defeat: 89 }, "Blood Luminous": { attack: 17, defeat: 103 }, "Blood Enma": { attack: 17, defeat: 127 }, "Blood King Slime": { attack: 19, defeat: 151 }
            }
        };

        function generateTables() {
            consts.expTable[1] = 6; consts.expTable[2] = 20; consts.expTable[3] = 50; consts.expTable[4] = 100; consts.expTable[5] = 120;
            consts.expTable[6] = 140; consts.expTable[7] = 150; consts.expTable[8] = 175; consts.expTable[9] = 200;
            for(let i = 10; i < 20; i++) { consts.expTable[i] = consts.expTable[i-1] + 5; }

            consts.playerHpTable[1] = 100; consts.playerHpTable[2] = 125; consts.playerHpTable[3] = 150; consts.playerHpTable[4] = 175; consts.playerHpTable[5] = 200;
            consts.playerHpTable[6] = 220; consts.playerHpTable[7] = 250; consts.playerHpTable[8] = 320; consts.playerHpTable[9] = 400; consts.playerHpTable[10] = 500;
            for(let i = 11; i <= 20; i++) { consts.playerHpTable[i] = consts.playerHpTable[i-1] + 50; }
        }

        function initPlayer() {
            playerStatus = { level: 1, exp: 0, hp: consts.playerHpTable[1], maxHp: consts.playerHpTable[1] };
        }

        function startBattle(level) {
            currentQuizLevel = level; initPlayer(); enemyDefeatedCount = 0; bossEncounterCount = 0; score = 0; correctStreak = 0; correctAnswersCount = 0; isLuminusDefeatedOnce = false; isAkumaDefeatedOnce = false; isMaohDefeatedOnce = false;
            dom.levelSelectScreen.classList.add('hidden'); dom.battleScreen.classList.remove('hidden');
            spawnEnemy();
            updateAllUI();
            showBattleMessage(`${enemyStatus.name}が現れた！`, () => { showNextQuestion(); });
        }
        
        function calculateEnemyAttack(enemyName) {
            if (enemyDefeatedCount === 0) return 1;
            let baseAtk = 0;
            let limit = Infinity;

            if (isRitualMode) {
                if (enemyName.includes('Slime')) { baseAtk = 6 * enemyDefeatedCount; limit = 110; } 
                else if (enemyName.includes('Goblin')) { baseAtk = 10 * enemyDefeatedCount; limit = 150; } 
                else if (enemyName.includes('Skeleton')) { baseAtk = 4 * enemyDefeatedCount; limit = 145; } 
                else if (enemyName.includes('Golem')) { baseAtk = 60 * correctAnswersCount / (enemyDefeatedCount || 1); limit = 180; } 
                else if (enemyName.includes('Shadow')) { baseAtk = 3 * correctAnswersCount / (enemyDefeatedCount || 1) * playerStatus.level; limit = 175; } 
                else { // Blood Bosses
                    baseAtk = 60 * correctAnswersCount / (enemyDefeatedCount || 1);
                    limit = consts.bloodBossAttackLimits[enemyName] || Infinity;
                }
            } else { // Normal Mode
                if (enemyName.includes('スライム')) {
                    baseAtk = 3 * enemyDefeatedCount / 3;
                    if (enemyName === 'スライム') limit = 20; else if (enemyName === 'スライムα') limit = 35;
                    else if (enemyName === 'スライムβ') limit = 50; else limit = 65;
                } else if (enemyName.includes('ゴブリン')) {
                    baseAtk = 5 / 3 * enemyDefeatedCount;
                    if (enemyName === 'ゴブリン') limit = 25; else if (enemyName === 'ゴブリンα') limit = 40;
                    else if (enemyName === 'ゴブリンβ') limit = 55; else limit = 70;
                } else if (enemyName.includes('スケルトン')) {
                    baseAtk = 2 / 3 * enemyDefeatedCount;
                    if (enemyName === 'スケルトン') limit = 50; else if (enemyName === 'スケルトンα') limit = 65;
                } else if (enemyName.includes('ゴーレム')) {
                    baseAtk = 10 * correctAnswersCount / (enemyDefeatedCount || 1);
                    limit = 45; // No evolutions for Golem/Shadow in normal mode yet
                } else if (enemyName.includes('シャドウ')) {
                    baseAtk = correctAnswersCount / (enemyDefeatedCount || 1) * playerStatus.level / 2;
                    limit = 45;
                } else { // Normal Bosses
                    baseAtk = 10 * correctAnswersCount / (enemyDefeatedCount || 1);
                    if (enemyName === '魔王') limit = 60; else if (enemyName === '悪魔之王') limit = 70;
                    else if (enemyName === '邪神 ルミナス') limit = 80; else if (enemyName === '閻魔大王') limit = 90;
                    else if (enemyName === 'キングスライム') limit = 100;
                }
            }
            return Math.min(Math.round(baseAtk), limit);
        }

        function spawnEnemy() {
            const isBossTime = (enemyDefeatedCount > 0 && enemyDefeatedCount % 4 === 0);
            const pLevel = playerStatus.level > 10 ? 10 : playerStatus.level; 
            const pLevelForHp = pLevel > 5 ? 5 : pLevel;
            let enemyData;

            if (isRitualMode) {
                if (isBossTime) {
                    bossEncounterCount++;
                    const bossCycle = bossEncounterCount % 5;
                    const bossNames = ["Blood Lord", "Blood Devil-King", "Blood Luminous", "Blood Enma", "Blood King Slime"];
                    const bossName = bossNames[bossCycle === 0 ? 4 : bossCycle - 1];
                    const hp = consts.bloodBossHpTable[bossName][pLevelForHp];
                    const attack = calculateEnemyAttack(bossName);
                    enemyData = { name: bossName, hp, maxHp: hp, attack };
                } else {
                    const enemyPool = ["Blood Slime", "Blood Goblin", "Blood Skeleton", "Blood Golem", "Blood Shadow"];
                    const enemyName = enemyPool[Math.floor(Math.random() * enemyPool.length)];
                    let hpRangeKey;
                    if (enemyName.includes('Slime')) hpRangeKey = 's';
                    else if (enemyName.includes('Goblin')) hpRangeKey = 'g';
                    else if (enemyName.includes('Skeleton')) hpRangeKey = 'sk';
                    else if (enemyName.includes('Golem')) hpRangeKey = 'go';
                    else if (enemyName.includes('Shadow')) hpRangeKey = 'sh';
                    const [min, max] = consts.bloodEnemyHpTable[pLevelForHp][hpRangeKey];
                    const hp = getRandomInt(min, max);
                    const attack = calculateEnemyAttack(enemyName);
                    enemyData = { name: enemyName, hp, maxHp: hp, attack };
                }
            } else { // Normal Mode
                if (isBossTime) {
                    bossEncounterCount++;
                    const bossCycle = bossEncounterCount % 5;
                    let bossName = (bossCycle === 1) ? "魔王" : (bossCycle === 2) ? "悪魔之王" : (bossCycle === 3) ? "邪神 ルミナス" : (bossCycle === 4) ? "閻魔大王" : "キングスライム";
                    const hp = consts.bossHpTable[bossName][pLevelForHp];
                    const attack = calculateEnemyAttack(bossName);
                    enemyData = { name: bossName, hp, maxHp: hp, attack: attack };
                } else {
                    let enemyPool = [];
                    if (isLuminusDefeatedOnce) { 
                        enemyPool = ['スライムα', 'ゴブリンα', 'スライムβ', 'ゴブリンβ', 'スケルトン', 'スライムγ', 'ゴブリンγ', 'スケルトンα', 'ゴーレム', 'シャドウ'];
                    } else if (isAkumaDefeatedOnce) {
                        enemyPool = ['スライムα', 'ゴブリンα', 'スライムβ', 'ゴブリンβ', 'スケルトン'];
                    } else if (isMaohDefeatedOnce) {
                        enemyPool = ['スライム', 'ゴブリン', 'スライムα', 'ゴブリンα']; 
                    } else { 
                        enemyPool = ['スライム', 'ゴブリン'];
                    }
                    const enemyName = enemyPool[Math.floor(Math.random() * enemyPool.length)];
                    const [min, max] = getEnemyHpRange(enemyName, pLevel);
                    const hp = getRandomInt(min, max);
                    const attack = calculateEnemyAttack(enemyName);
                    enemyData = { name: enemyName, hp, maxHp: hp, attack: attack };
                }
            }
            enemyStatus = { ...enemyData };
            dom.enemy.sprite.innerHTML = enemySprites[enemyData.name];
        }
        
        function getEnemyHpRange(enemyName, pLevel) {
            const pLevelForHp = pLevel > 5 ? 5 : pLevel;
            let table, key;

            if (isLuminusDefeatedOnce || isAkumaDefeatedOnce) {
                table = consts.advancedEnemyHpTable[pLevelForHp];
                if (enemyName.includes('シャドウ')) key = 'sh';
                else if (enemyName.includes('ゴーレム')) key = 'go';
                else {
                    const typeKey = enemyName.includes('スケルトン') ? 'sk' : (enemyName.includes('スライム') ? 's' : 'g');
                    const rankKey = enemyName.includes('α') ? 'a' : (enemyName.includes('β') ? 'b' : (enemyName.includes('γ') ? 'g' : ''));
                    key = typeKey + rankKey;
                }
            } else {
                table = consts.enemyHpTable[pLevelForHp];
                key = enemyName.includes('スライム') ? 's' : 'g';
            }
            return table[key];
        }

        function showNextQuestion() {
            if (isPaused) return; 
            isAnswering = false;
            const isBossTime = (enemyDefeatedCount > 0 && enemyDefeatedCount % 4 === 0);
            const quizLevels = [currentQuizLevel];
            if (isBossTime && currentQuizLevel < 3) quizLevels.push(currentQuizLevel + 1);
            quizWords = wordData.filter(w => quizLevels.includes(w.level));

            const correctWord = quizWords[Math.floor(Math.random() * quizWords.length)]; currentQuestion = correctWord;
            const dummies = []; const tempWords = [...wordData];
            while (dummies.length < 5) {
                const dummyWord = tempWords.splice(Math.floor(Math.random() * tempWords.length), 1)[0];
                if (dummyWord && dummyWord.word !== correctWord.word && !dummies.some(d => d.word === dummyWord.word)) dummies.push(dummyWord);
            }
            const choices = [correctWord, ...dummies].sort(() => Math.random() - 0.5);
            dom.quiz.word.textContent = correctWord.word;
            dom.quiz.buttons.forEach((button, i) => { button.textContent = choices[i] ? choices[i].meaning : ''; button.disabled = false; button.className = 'choice-button'; });
        }
        
        dom.quiz.grid.addEventListener('click', async e => {
            if (e.target.tagName !== 'BUTTON' || isAnswering) return;
            isAnswering = true; 
            dom.quiz.buttons.forEach(b => b.disabled = true);
            const isCorrect = (e.target.textContent === currentQuestion.meaning);
            
            if (isCorrect) { e.target.classList.add('correct'); } else { e.target.classList.add('incorrect'); dom.quiz.buttons.forEach(b => { if (b.textContent === currentQuestion.meaning) b.classList.add('correct-answer'); }); }
            
            await new Promise(r => setTimeout(r, 1200));

            if (isCorrect) { correctStreak++; correctAnswersCount++; await playerAttack(); } else { correctStreak = 0; await enemyAttack(); }
        });

        async function playerAttack() {
            isAnswering = true;
            let baseAttack = (3 * playerStatus.level) + correctStreak;
            let damage = Math.min(100, baseAttack);
            let isCritical = false;
            let critRate = playerStatus.level < 11 ? (playerStatus.level < 6 ? 1/6 : 1/3) : 1/2;
            let critMultiplier = playerStatus.level < 11 ? 1.5 : 2.1;
            if (Math.random() < critRate) { damage = Math.round(damage * critMultiplier); isCritical = true; }
            
            showDamage(false, damage, isCritical);
            dom.enemy.sprite.classList.add('damaged');
            await new Promise(r => setTimeout(r, 200));
            dom.enemy.sprite.classList.remove('damaged');

            enemyStatus.hp = Math.max(0, enemyStatus.hp - damage);
            playerStatus.hp = Math.min(playerStatus.maxHp, playerStatus.hp + Math.trunc(damage / 3));
            score += Math.round(10 * correctAnswersCount * (enemyDefeatedCount + 1) / 5 * correctStreak / 3);
            
            addExp(consts.expGains[enemyStatus.name].attack);
            updateAllUI();

            if (enemyStatus.hp <= 0) {
                if (await checkLevelUp()) { await showLevelUpAnimation(); }
                
                await new Promise(resolve => showBattleMessage(`${enemyStatus.name}を倒した！`, resolve));
                
                if (!consts.bossList.includes(enemyStatus.name)) {
                    enemyDefeatedCount++;
                }

                addExp(consts.expGains[enemyStatus.name].defeat);

                if (!isRitualMode) {
                    if (enemyStatus.name === '魔王') isMaohDefeatedOnce = true;
                    if (enemyStatus.name === '悪魔之王') isAkumaDefeatedOnce = true;
                    if (enemyStatus.name === '邪神 ルミナス') isLuminusDefeatedOnce = true;
                }

                if (await checkLevelUp()) { await showLevelUpAnimation(); }
                
                const nextSpawnIsBoss = (enemyDefeatedCount > 0 && (enemyDefeatedCount) % 4 === 0);
                if (nextSpawnIsBoss) { await showBossWarning(); }
                
                spawnEnemy(); 
                updateAllUI();
                await new Promise(resolve => showBattleMessage(`${enemyStatus.name}が現れた！`, resolve));
                showNextQuestion();
            } else {
                if (await checkLevelUp()) { await showLevelUpAnimation(); }
                showNextQuestion();
            }
        }
        
        async function enemyAttack() {
            isAnswering = true;
            let damage = enemyStatus.attack, isCritical = false;
            if (Math.random() < 1/4) { damage = Math.round(damage * 1.5); isCritical = true; }
            showDamage(true, damage, isCritical);
            document.body.classList.add('player-damaged'); 
            await new Promise(r => setTimeout(r, 300));
            document.body.classList.remove('player-damaged');
            
            playerStatus.hp = Math.max(0, playerStatus.hp - damage);
            enemyStatus.hp = Math.min(enemyStatus.maxHp, enemyStatus.hp + Math.trunc(damage / 2));
            updatePlayerUI(); updateEnemyUI();
            
            if (playerStatus.hp <= 0) { gameOver(); } else { showNextQuestion(); }
        }
        
        function gameOver() { showBattleMessage(`GAME OVER... Final Score: ${score}`, () => { dom.battleScreen.classList.add('hidden'); dom.titleScreen.classList.remove('hidden'); }, 5000); }
        
        function addExp(amount) {
            if (playerStatus.level >= 20) return;
            playerStatus.exp += amount; 
        }

        async function checkLevelUp() {
            if (playerStatus.level >= 20) return false;
            return playerStatus.exp >= (consts.expTable[playerStatus.level] || Infinity);
        }

        function showLevelUpAnimation(callback) {
            return new Promise(resolve => {
                const overlay = dom.levelUpOverlay;
                overlay.classList.remove('hidden');
                overlay.classList.add('flex');
                setTimeout(() => {
                    overlay.classList.add('hidden');
                    overlay.classList.remove('flex');
                    levelUp();
                    if (callback) callback();
                    resolve();
                }, 2500);
            });
        }
        
        function levelUp(){
            while(playerStatus.level < 20 && playerStatus.exp >= (consts.expTable[playerStatus.level] || Infinity)) {
                const expNeeded = consts.expTable[playerStatus.level];
                playerStatus.level++; 
                playerStatus.exp -= expNeeded;
            }
            if(playerStatus.level >= 20) { playerStatus.level = 20; playerStatus.exp = 0; }
            playerStatus.maxHp = consts.playerHpTable[playerStatus.level];
            playerStatus.hp = playerStatus.maxHp;
            updatePlayerUI(); updateExpBar();
        }
        
        function showDamage(isPlayer, damage, isCritical) {
            const container = isPlayer ? document.body : dom.enemy.sprite;
            if (!container) return;
            const indicator = document.createElement('div');
            indicator.className = `damage-indicator ${isPlayer ? 'player' : 'enemy'}`;
            indicator.textContent = damage;
            indicator.style.color = isCritical ? 'var(--critical-color)' : 'var(--damage-color)';
            container.appendChild(indicator);
            setTimeout(() => indicator.remove(), 1000);
        }

        function showBossWarning() {
            return new Promise(resolve => {
                dom.bossWarning.classList.remove('hidden');
                setTimeout(() => {
                    dom.bossWarning.classList.add('hidden');
                    resolve();
                }, 2000);
            });
        }

        function togglePause(show) { isPaused = show; dom.pause.modal.classList.toggle('hidden', !show); if (!show) { dom.pause.menu.classList.remove('hidden'); dom.pause.confirm.classList.add('hidden'); } }
        function updateAllUI() { updatePlayerUI(); updateEnemyUI(); updateExpBar(); updateScoreUI(); }
        function updatePlayerUI() { dom.player.level.textContent = playerStatus.level; dom.player.hp.textContent = playerStatus.hp; dom.player.maxHp.textContent = playerStatus.maxHp; dom.player.hpBar.style.width = `${(playerStatus.hp / playerStatus.maxHp) * 100}%`; }
        function updateEnemyUI() { dom.enemy.name.textContent = enemyStatus.name; dom.enemy.hp.textContent = enemyStatus.hp; dom.enemy.maxHp.textContent = enemyStatus.maxHp; dom.enemy.hpBar.style.width = `${(enemyStatus.hp / enemyStatus.maxHp) * 100}%`; }
        function updateExpBar() { if (playerStatus.level >= 20) { dom.exp.bar.style.width = '100%'; dom.exp.text.textContent = 'MAX'; dom.exp.bar.classList.add('max'); } else { const next = consts.expTable[playerStatus.level] || 999; dom.exp.bar.style.width = `${Math.min(100, (playerStatus.exp / next) * 100)}%`; dom.exp.text.textContent = `${playerStatus.exp}/${next}`; dom.exp.bar.classList.remove('max'); } }
        function updateScoreUI() { dom.score.textContent = score; }
        function showBattleMessage(msg, cb, dur=2000) { dom.message.text.innerHTML = msg; dom.message.box.classList.remove('hidden'); setTimeout(() => { dom.message.box.classList.add('hidden'); if(cb)cb(); }, dur); }
        function getRandomInt(min, max) { return Math.floor(Math.random()*(max-min+1))+min; }

        // --- 初期化 ---
        generateTables();
        document.querySelectorAll('.level-button').forEach(b => b.addEventListener('click', () => startBattle(parseInt(b.dataset.level))));
        document.getElementById('closeLevelSelect').addEventListener('click', () => { dom.levelSelectScreen.classList.add('hidden'); dom.titleScreen.classList.remove('hidden'); });
        document.getElementById('attackButton').addEventListener('click', () => { dom.titleScreen.classList.add('hidden'); dom.levelSelectScreen.classList.remove('hidden'); });
        
        // Pause Menu
        dom.pause.button.addEventListener('click', () => togglePause(true));
        document.getElementById('resume-button').addEventListener('click', () => togglePause(false));
        document.getElementById('quit-button').addEventListener('click', () => { dom.pause.menu.classList.add('hidden'); dom.pause.confirm.classList.remove('hidden'); });
        document.getElementById('quit-no-button').addEventListener('click', () => { dom.pause.menu.classList.remove('hidden'); dom.pause.confirm.classList.add('hidden'); });
        document.getElementById('quit-yes-button').addEventListener('click', () => { togglePause(false); dom.battleScreen.classList.add('hidden'); dom.titleScreen.classList.remove('hidden'); });

        // Secret Input
        dom.secret.button.addEventListener('click', () => {
            dom.secret.modal.classList.remove('hidden');
            dom.secret.input.focus();
        });
        dom.secret.closeButton.addEventListener('click', () => {
            dom.secret.modal.classList.add('hidden');
            dom.secret.input.value = '';
        });

        dom.secret.enterButton.addEventListener('click', () => {
            const command = dom.secret.input.value.trim();
            dom.secret.modal.classList.add('hidden');
            dom.secret.input.value = '';

            if (command === 'b100d e1g0 0h') {
                isRitualMode = true;
                dom.ritualTerop.classList.remove('hidden');
                dom.ritualTerop.addEventListener('click', () => {
                    dom.ritualTerop.classList.add('hidden');
                    if(dom.secret.button) {
                        dom.secret.button.remove();
                        dom.secret.button = null;
                    }
                    document.body.style.backgroundColor = '#490000';
                }, { once: true });
            }
        });

    </script>
</body>
</html>
