<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>演出付きじゃんけんゲーム</title>
    <style>
        body {
            font-family: 'Helvetica Neue', Arial, sans-serif;
            text-align: center;
            background-color: #f0f2f5;
            margin: 0;
            padding: 20px;
        }
        .container {
            max-width: 500px;
            margin: 30px auto;
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        h1 {
            color: #333;
            margin-bottom: 20px;
            transition: color 0.3s;
        }
        /* チート有効時のタイトルスタイル */
        h1.cheat-active {
            color: #d4af37; /* ゴールド */
            text-shadow: 1px 1px 2px rgba(0,0,0,0.2);
        }
        .setup-box {
            margin-bottom: 20px;
            font-size: 16px;
            color: #4a5568;
        }
        .setup-box select {
            font-size: 16px;
            padding: 5px 10px;
            border-radius: 5px;
            border: 1px solid #cbd5e1;
            cursor: pointer;
        }
        .score-board {
            font-size: 18px;
            font-weight: bold;
            color: #4a5568;
            background-color: #edf2f7;
            padding: 10px;
            border-radius: 8px;
            margin-bottom: 25px;
        }
        .choices {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
        }
        button {
            font-size: 24px;
            padding: 15px 25px;
            cursor: pointer;
            border: none;
            border-radius: 10px;
            background-color: #4ea8de;
            color: white;
            transition: transform 0.1s, background-color 0.2s, opacity 0.2s;
        }
        button:hover:not(:disabled) {
            background-color: #5390d9;
            transform: scale(1.05);
        }
        button:active:not(:disabled) {
            transform: scale(0.95);
        }
        button:disabled {
            background-color: #cbd5e1;
            cursor: not-allowed;
            opacity: 0.6;
        }
        .result-box {
            margin-top: 20px;
            padding: 15px;
            border-radius: 10px;
            background-color: #f8f9fa;
            min-height: 140px;
        }
        .details {
            font-size: 18px;
            color: #666;
            margin: 10px 0;
            line-height: 1.8;
            text-align: left;
            display: inline-block;
        }
        .shuffling {
            font-size: 18px;
            color: #3182ce;
            font-weight: bold;
        }
        .outcome {
            font-size: 28px;
            font-weight: bold;
            margin: 15px 0 10px 0;
        }
        .win { color: #2a9d8f; }
        .lose { color: #e76f51; }
        .draw { color: #f4a261; }
    </style>
</head>
<body>

<div class="container">
    <h1 id="game-title">じゃんけんゲーム</h1>
    
    <div class="setup-box">
        <label for="cpu-count">対戦相手の人数: </label>
        <select id="cpu-count" onchange="resetScore()">
            <option value="1" selected>1人 (1vs1)</option>
            <option value="2">2人 (3人対戦)</option>
            <option value="3">3人 (4人対戦)</option>
        </select>
    </div>

    <div class="score-board" id="score-board">
        0勝 0敗 0分 (勝率: 0%)
    </div>
    
    <div class="choices">
        <button onclick="startJanken(0)" id="btn-0">✊ グー</button>
        <button onclick="startJanken(1)" id="btn-1">✌️ チョキ</button>
        <button onclick="startJanken(2)" id="btn-2">✋ パー</button>
    </div>

    <div class="result-box">
        <div id="details" class="details">ボタンを押して勝負してね！<br><small style="color:#a0aec0;">　</small></div>
        <div id="outcome" class="outcome"></div>
    </div>
</div>

<script>
    let wins = 0;
    let losses = 0;
    let draws = 0;
    const hands = ['✊ グー', '✌️ チョキ', '✋ パー'];

    // 隠しコマンド用の変数
    let inputBuffer = '';
    const secretCommand = 'win';
    let isCheatActive = false;

    // キーボード入力を監視するイベントリスナー
    window.addEventListener('keydown', (e) => {
        // 入力された文字を小文字にしてバッファに追加
        inputBuffer += e.key.toLowerCase();
        
        // コマンドの長さ以上の文字列になったら、古い文字を切り捨てる
        if (inputBuffer.length > secretCommand.length) {
            inputBuffer = inputBuffer.substring(inputBuffer.length - secretCommand.length);
        }
        
        // コマンドが一致したか判定
        if (inputBuffer === secretCommand) {
            isCheatActive = !isCheatActive; // モード反転
            inputBuffer = ''; // バッファクリア
            
            const titleElement = document.getElementById('game-title');
            if (isCheatActive) {
                titleElement.textContent = '最強じゃんけんゲーム（チート有効）';
                titleElement.className = 'cheat-active';
                alert('隠しコマンド起動！絶対に負けなくなりました。');
            } else {
                titleElement.textContent = 'じゃんけんゲーム';
                titleElement.className = '';
                alert('隠しコマンド解除。通常モードに戻りました。');
            }
        }
    });

    function resetScore() {
        wins = 0;
        losses = 0;
        draws = 0;
        document.getElementById('score-board').textContent = `0勝 0敗 0分 (勝率: 0%)`;
        document.getElementById('details').innerHTML = `人数を変更しました。ボタンを押して勝負してね！`;
        document.getElementById('outcome').textContent = '';
    }

    function startJanken(userChoice) {
        setButtonsDisabled(true);
        document.getElementById('cpu-count').disabled = true;
        
        const detailsElement = document.getElementById('details');
        const outcomeElement = document.getElementById('outcome');
        outcomeElement.textContent = '';
        
        const cpuCount = parseInt(document.getElementById('cpu-count').value);
        
        let count = 0;
        const shuffleInterval = setInterval(() => {
            let shuffleText = `あなた: <strong>${hands[userChoice]}</strong><br>`;
            for (let i = 1; i <= cpuCount; i++) {
                const randomHand = hands[Math.floor(Math.random() * 3)];
                shuffleText += `<span class="shuffling">あいて${i}: 🌀 ${randomHand} 🌀</span><br>`;
            }
            
            detailsElement.innerHTML = shuffleText;
            count++;
            
            if (count >= 10) {
                clearInterval(shuffleInterval);
                executeResult(userChoice, cpuCount);
            }
        }, 100);
    }

    function executeResult(userChoice, cpuCount) {
        const cpuChoices = [];
        
        for (let i = 0; i < cpuCount; i++) {
            if (isCheatActive) {
                // チート有効時：プレイヤーの手に対して「必ず負ける手」をCPUに割り当てる
                // プレイヤーがグー(0)なら、CPUは全員チョキ(1)
                // プレイヤーがチョキ(1)なら、CPUは全員パー(2)
                // プレイヤーがパー(2)なら、CPUは全員グー(0)
                cpuChoices.push((userChoice + 1) % 3);
            } else {
                // 通常時：ランダム
                cpuChoices.push(Math.floor(Math.random() * 3));
            }
        }
        
        const allChoices = [userChoice, ...cpuChoices];
        const uniqueChoices = [...new Set(allChoices)];
        
        let resultMessage = '';
        let resultClass = '';
        
        if (uniqueChoices.length === 1 || uniqueChoices.length === 3) {
            resultMessage = 'あいこです！';
            resultClass = 'draw';
            draws++;
        } else {
            const handA = uniqueChoices[0];
            const handB = uniqueChoices[1];
            
            let winningHand;
            if ((handA === 0 && handB === 1) || (handA === 1 && handB === 0)) winningHand = 0;
            else if ((handA === 1 && handB === 2) || (handA === 2 && handB === 1)) winningHand = 1;
            else winningHand = 2;
            
            if (userChoice === winningHand) {
                resultMessage = 'あなたの勝ち！🎉';
                resultClass = 'win';
                wins++;
            } else {
                resultMessage = 'あなたの負け…😢';
                resultClass = 'lose';
                losses++;
            }
        }
        
        const totalGames = wins + losses + draws;
        const winRate = Math.round((wins / totalGames) * 100);
        document.getElementById('score-board').textContent = `${wins}勝 ${losses}敗 ${draws}分 (勝率: ${winRate}%)`;
        
        let resultText = `あなた: <strong>${hands[userChoice]}</strong><br>`;
        cpuChoices.forEach((choice, index) => {
            resultText += `あいて${index + 1}: <strong>${hands[choice]}</strong><br>`;
        });
        
        document.getElementById('details').innerHTML = resultText;
            
        const outcomeElement = document.getElementById('outcome');
        outcomeElement.textContent = resultMessage;
        outcomeElement.className = 'outcome ' + resultClass;
        
        setButtonsDisabled(false);
        document.getElementById('cpu-count').disabled = false;
    }

    function setButtonsDisabled(disabled) {
        document.getElementById('btn-0').disabled = disabled;
        document.getElementById('btn-1').disabled = disabled;
        document.getElementById('btn-2').disabled = disabled;
    }
</script>

</body>
</html>
