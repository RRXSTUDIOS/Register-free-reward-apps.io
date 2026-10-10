<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>CLAIM YOUR REWARD | FUTURE APP</title>
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