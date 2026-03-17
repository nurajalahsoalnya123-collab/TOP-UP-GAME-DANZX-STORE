<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DANZX STORE • Top Up Game</title>
    <!-- Font Awesome 6 & Google Fonts Poppins -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            min-height: 100vh;
            background: linear-gradient(145deg, #0f0c1f 0%, #1a1730 50%, #0f0e1e 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 16px;
            position: relative;
            overflow-x: hidden;
        }

        /* efek glow latar belakang biruan */
        body::before {
            content: "";
            position: absolute;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(0, 160, 255, 0.2) 0%, transparent 70%);
            top: -50px;
            right: -50px;
            border-radius: 50%;
            z-index: 0;
        }
        body::after {
            content: "";
            position: absolute;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(0, 100, 255, 0.15) 0%, transparent 70%);
            bottom: -100px;
            left: -80px;
            border-radius: 50%;
            z-index: 0;
        }

        .card {
            max-width: 600px;
            width: 100%;
            background: rgba(18, 18, 30, 0.8);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(64, 128, 255, 0.3);
            border-radius: 40px;
            padding: 32px 30px;
            box-shadow: 0 30px 50px rgba(0, 0, 0, 0.7), 0 0 0 2px rgba(64, 128, 255, 0.1) inset;
            z-index: 2;
            transition: all 0.2s ease;
            overflow: hidden;
        }

        /* HEADER dengan gradasi biru dan animasi */
        .store-name {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }

        .store-name h1 {
            font-size: 3.5rem;
            font-weight: 800;
            letter-spacing: 2px;
            background: linear-gradient(135deg, #4facfe, #00f2fe, #3b8dff, #4facfe);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 0;
            white-space: nowrap;
            display: inline-block;
            padding: 0 10px;
            animation: floatBreath 3s infinite ease-in-out;
            text-shadow: 0 0 15px rgba(0,160,255,0.6), 0 0 30px rgba(0,100,255,0.4);
            max-width: 100%;
        }

        @keyframes floatBreath {
            0% {
                transform: translateY(0) scale(1);
                text-shadow: 0 0 15px rgba(0,160,255,0.6), 0 0 30px rgba(0,100,255,0.4);
            }
            50% {
                transform: translateY(-5px) scale(1.02);
                text-shadow: 0 0 25px rgba(0,200,255,0.9), 0 0 50px rgba(0,150,255,0.7);
            }
            100% {
                transform: translateY(0) scale(1);
                text-shadow: 0 0 15px rgba(0,160,255,0.6), 0 0 30px rgba(0,100,255,0.4);
            }
        }

        /* Judul halaman utama */
        .main-title {
            color: white;
            font-size: 1.5rem;
            margin-bottom: 30px;
            text-align: center;
            font-weight: 600;
            word-break: break-word;
        }

        /* Grid game selector - 2 game */
        .game-selector {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 20px;
        }

        .game-logo {
            width: 150px;
            height: 150px;
            border-radius: 30px;
            background: rgba(79, 172, 254, 0.1);
            border: 3px solid #2f4070;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            padding: 20px;
        }

        .game-logo i {
            font-size: 4rem;
            margin-bottom: 10px;
        }

        .game-logo span {
            color: white;
            font-weight: 600;
            font-size: 1.1rem;
        }

        .game-logo:hover {
            border-color: #4facfe;
            transform: scale(1.05);
            background: rgba(79, 172, 254, 0.2);
            box-shadow: 0 0 20px rgba(79, 172, 254, 0.3);
        }

        .ff-logo i {
            color: #ff6b6b;
        }

        .roblox-logo i {
            color: #00a2ff;
        }

        /* Konten game */
        .game-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .game-content.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Style untuk form elements */
        .input-group {
            margin-bottom: 28px;
        }
        .input-group label {
            display: block;
            color: #b0c8ff;
            font-weight: 500;
            font-size: 1rem;
            margin-bottom: 8px;
            letter-spacing: 0.3px;
        }
        .input-group label i {
            color: #4facfe;
            margin-right: 8px;
        }
        .input-group input {
            width: 100%;
            background: rgba(10, 8, 22, 0.7);
            border: 1px solid #3a4b6e;
            border-radius: 28px;
            padding: 16px 24px;
            font-size: 1rem;
            color: white;
            outline: none;
            transition: all 0.2s;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
        }
        .input-group input:focus {
            border-color: #4facfe;
            box-shadow: 0 0 0 3px rgba(79, 172, 254, 0.3), 0 4px 15px #000;
        }
        .input-group input::placeholder {
            color: #6a7a9e;
        }

        .section-title {
            display: flex;
            align-items: center;
            gap: 10px;
            color: #b0e0ff;
            font-weight: 600;
            font-size: 1.3rem;
            margin: 30px 0 18px 0;
            border-left: 6px solid #4facfe;
            padding-left: 16px;
            text-shadow: 0 2px 3px black;
        }
        .section-title i {
            color: #4facfe;
            font-size: 1.6rem;
        }

        .diamond-grid, .robux-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
            margin-bottom: 30px;
        }

        .diamond-option, .robux-option {
            background: rgba(22, 20, 37, 0.8);
            border: 1px solid #2f4070;
            border-radius: 20px;
            padding: 14px 14px 14px 46px;
            position: relative;
            transition: background 0.15s, border-color 0.15s, transform 0.1s;
            cursor: pointer;
            box-shadow: 0 6px 10px rgba(0,0,0,0.5);
        }
        .diamond-option:hover, .robux-option:hover {
            background: #1e2a45;
            border-color: #4facfe;
            transform: scale(1.01);
        }
        .diamond-option input[type="radio"], .robux-option input[type="radio"] {
            position: absolute;
            left: 16px;
            top: 50%;
            transform: translateY(-50%);
            width: 18px;
            height: 18px;
            accent-color: #4facfe;
            cursor: pointer;
        }
        .diamond-option .info, .robux-option .info {
            display: flex;
            flex-direction: column;
        }
        .diamond-option .diamond, .robux-option .robux {
            font-weight: 700;
            font-size: 1.2rem;
            color: white;
            letter-spacing: 0.5px;
        }
        .diamond-option .diamond i, .robux-option .robux i {
            color: #7ac7ff;
            font-size: 1rem;
            margin-left: 4px;
        }
        .diamond-option .price, .robux-option .price {
            font-weight: 600;
            color: #b8d0ff;
            background: rgba(0,0,0,0.3);
            display: inline-block;
            padding: 2px 8px;
            border-radius: 40px;
            font-size: 0.9rem;
            margin-top: 4px;
            border: 1px solid #3a5690;
        }
        .diamond-option:has(input:checked), .robux-option:has(input:checked) {
            background: #1f2c50;
            border-color: #4facfe;
            box-shadow: 0 0 0 1px #4facfe, 0 8px 12px black;
        }

        .payment-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 16px;
            margin: 20px 0 32px 0;
            justify-content: center;
        }
        .payment-item {
            flex: 1 1 130px;
            min-width: 120px;
            background: #1a1f35;
            border: 1px solid #2f4070;
            border-radius: 28px;
            padding: 16px 10px;
            text-align: center;
            cursor: pointer;
            transition: all 0.2s;
            box-shadow: 0 5px 8px #00000040;
        }
        .payment-item:hover {
            background: #22305a;
            border-color: #4facfe;
            transform: translateY(-2px);
        }
        .payment-item:has(input:checked) {
            background: #263a70;
            border-color: #4facfe;
            box-shadow: 0 0 0 2px #4facfe, 0 8px 12px black;
        }
        .payment-item input[type="radio"] {
            display: none;
        }
        .payment-item i {
            font-size: 2.2rem;
            display: block;
            margin-bottom: 8px;
            color: #7ac7ff;
        }
        .payment-item span {
            color: white;
            font-weight: 600;
            font-size: 1rem;
            background: rgba(0,0,0,0.3);
            padding: 4px 10px;
            border-radius: 40px;
        }

        .confirm-btn {
            width: 100%;
            background: linear-gradient(95deg, #2a73ff, #5faaff);
            border: none;
            border-radius: 60px;
            padding: 18px 20px;
            font-weight: 800;
            font-size: 1.7rem;
            color: white;
            text-transform: uppercase;
            letter-spacing: 2px;
            box-shadow: 0 15px 20px -8px #2a73ff80, 0 0 0 1px #ffffff40 inset;
            cursor: pointer;
            transition: 0.1s linear;
            margin: 20px 0 18px 0;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
        }
        .confirm-btn:active {
            transform: scale(0.97);
            box-shadow: 0 5px 10px black;
        }
        .confirm-btn i {
            font-size: 2rem;
            color: #ffffff;
        }

        .fun-footer {
            text-align: center;
            color: #7a8fbb;
            font-size: 0.85rem;
            border-top: 1px dashed #3a4b7a;
            padding-top: 18px;
            margin-top: 10px;
        }

        /* Halaman sukses */
        .success-page {
            text-align: center;
            padding: 20px;
            animation: fadeIn 0.5s ease;
        }

        .success-icon {
            font-size: 5rem;
            color: #4facfe;
            margin-bottom: 20px;
            animation: scaleIn 0.5s ease;
        }

        @keyframes scaleIn {
            from { transform: scale(0); }
            to { transform: scale(1); }
        }

        .success-details {
            background: rgba(79, 172, 254, 0.1);
            border: 1px solid #4facfe;
            border-radius: 20px;
            padding: 25px;
            margin: 20px 0;
        }

        .success-details p {
            color: white;
            font-size: 1.2rem;
            margin: 15px 0;
        }

        .success-details i {
            color: #4facfe;
            margin-right: 10px;
        }

        .note {
            color: #7ac7ff;
            font-size: 1rem;
            margin-top: 20px;
            padding: 15px;
            background: rgba(0,0,0,0.3);
            border-radius: 15px;
            border-left: 4px solid #4facfe;
        }

        /* Perbaikan tombol back */
        .back-btn {
            background: transparent;
            border: 2px solid #4facfe;
            color: #4facfe;
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            margin: 0 0 20px 0;
            width: 100%;
            text-align: center;
            display: inline-block;
            text-decoration: none;
        }

        .back-btn:hover {
            background: #4facfe;
            color: white;
        }

        #roblox-page .input-group:first-of-type {
            margin-top: 10px;
        }

        /* Media query untuk layar kecil */
        @media (max-width: 550px) {
            .card { padding: 20px; }
            .store-name h1 { 
                font-size: 2.2rem;
            }
            .game-selector { flex-direction: column; align-items: center; gap: 15px; }
            .game-logo { width: 120px; height: 120px; }
            .game-logo i { font-size: 3rem; }
            .diamond-grid, .robux-grid { grid-template-columns: 1fr; }
            .payment-item { flex-basis: 100%; }
            .confirm-btn { font-size: 1.4rem; }
            body::before, body::after {
                width: 150px;
                height: 150px;
                opacity: 0.5;
            }
        }

        /* Media query untuk layar sangat kecil */
        @media (max-width: 380px) {
            .store-name h1 {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <div class="card">
        <!-- HEADER - DANZX STORE -->
        <div class="store-name">
            <h1>DANZX STORE</h1>
        </div>

        <!-- Halaman Utama (Pilih Game) -->
        <div id="main-page" class="game-content active">
            <div class="main-title">
                <i class="fas fa-gamepad"></i> Pilih Game
            </div>
            <div class="game-selector">
                <!-- Free Fire -->
                <div class="game-logo ff-logo" onclick="selectGame('ff')">
                    <i class="fas fa-fire"></i>
                    <span>Free Fire</span>
                </div>
                <!-- Roblox -->
                <div class="game-logo roblox-logo" onclick="selectGame('roblox')">
                    <i class="fab fa-roblox"></i>
                    <span>Roblox</span>
                </div>
            </div>
            <div class="fun-footer" style="border-top: none; margin-top: 20px;">
                <i class="fas fa-mouse-pointer"></i> Klik logo game untuk top-up
            </div>
        </div>

        <!-- Halaman Free Fire -->
        <div id="ff-page" class="game-content">
            <button class="back-btn" onclick="backToMain()">← Kembali</button>
            <form id="ffForm" onsubmit="event.preventDefault(); processTopUp('ff');">
                <div class="input-group">
                    <label><i class="fas fa-id-card"></i> ID FREE FIRE</label>
                    <input type="text" id="ffId" placeholder="Masukkan ID kamu" autocomplete="off">
                </div>

                <div class="section-title">
                    <i class="fas fa-gem"></i> 
                    <span>Pilih Diamond</span>
                </div>
                <div class="diamond-grid">
                    <label class="diamond-option">
                        <input type="radio" name="ffDiamond" value="5 Diamond">
                        <span class="info">
                            <span class="diamond">5💎 <i class="fas fa-gem"></i></span>
                            <span class="price">Rp 1.000</span>
                        </span>
                    </label>
                    <label class="diamond-option">
                        <input type="radio" name="ffDiamond" value="12 Diamond">
                        <span class="info">
                            <span class="diamond">12💎 <i class="fas fa-gem"></i></span>
                            <span class="price">Rp 2.000</span>
                        </span>
                    </label>
                    <label class="diamond-option">
                        <input type="radio" name="ffDiamond" value="50 Diamond">
                        <span class="info">
                            <span class="diamond">50💎 <i class="fas fa-gem"></i></span>
                            <span class="price">Rp 8.000</span>
                        </span>
                    </label>
                    <label class="diamond-option">
                        <input type="radio" name="ffDiamond" value="70 Diamond">
                        <span class="info">
                            <span class="diamond">70💎 <i class="fas fa-gem"></i></span>
                            <span class="price">Rp 10.000</span>
                        </span>
                    </label>
                    <label class="diamond-option">
                        <input type="radio" name="ffDiamond" value="140 Diamond">
                        <span class="info">
                            <span class="diamond">140💎 <i class="fas fa-gem"></i></span>
                            <span class="price">Rp 20.000</span>
                        </span>
                    </label>
                    <label class="diamond-option">
                        <input type="radio" name="ffDiamond" value="355 Diamond">
                        <span class="info">
                            <span class="diamond">355💎 <i class="fas fa-gem"></i></span>
                            <span class="price">Rp 50.000</span>
                        </span>
                    </label>
                    <label class="diamond-option">
                        <input type="radio" name="ffDiamond" value="720 Diamond">
                        <span class="info">
                            <span class="diamond">720💎 <i class="fas fa-gem"></i></span>
                            <span class="price">Rp 100.000</span>
                        </span>
                    </label>
                    <label class="diamond-option">
                        <input type="radio" name="ffDiamond" value="1450 Diamond">
                        <span class="info">
                            <span class="diamond">1,450💎 <i class="fas fa-gem"></i></span>
                            <span class="price">Rp 200.000</span>
                        </span>
                    </label>
                </div>

                <div class="section-title">
                    <i class="fas fa-wallet"></i>
                    <span>Metode Pembayaran</span>
                </div>
                <div class="payment-grid">
                    <label class="payment-item">
                        <input type="radio" name="ffPayment" value="DANA">
                        <i class="fas fa-money-bill-wave"></i>
                        <span>DANA</span>
                    </label>
                    <label class="payment-item">
                        <input type="radio" name="ffPayment" value="QRIS">
                        <i class="fas fa-qrcode"></i>
                        <span>QRIS</span>
                    </label>
                    <label class="payment-item">
                        <input type="radio" name="ffPayment" value="OVO">
                        <i class="fas fa-mobile-alt"></i>
                        <span>OVO</span>
                    </label>
                    <label class="payment-item">
                        <input type="radio" name="ffPayment" value="Gopay">
                        <i class="fas fa-google-pay"></i>
                        <span>Gopay</span>
                    </label>
                </div>

                <button type="submit" class="confirm-btn">
                    <i class="fas fa-check-circle"></i> CONFIRM
                </button>
            </form>
        </div>

        <!-- Halaman Roblox -->
        <div id="roblox-page" class="game-content">
            <button class="back-btn" onclick="backToMain()">← Kembali</button>
            <form id="robloxForm" onsubmit="event.preventDefault(); processTopUp('roblox');">
                <div class="input-group">
                    <label><i class="fas fa-user"></i> Username Roblox</label>
                    <input type="text" id="robloxUser" placeholder="Masukkan username Roblox" autocomplete="off">
                </div>

                <div class="section-title">
                    <i class="fas fa-coins"></i> 
                    <span>Pilih Robux</span>
                </div>
                <div class="robux-grid">
                    <label class="robux-option">
                        <input type="radio" name="robux" value="10 Robux">
                        <span class="info">
                            <span class="robux">10 Robux <i class="fas fa-coins"></i></span>
                            <span class="price">Rp 10.000</span>
                        </span>
                    </label>
                    <label class="robux-option">
                        <input type="radio" name="robux" value="50 Robux">
                        <span class="info">
                            <span class="robux">50 Robux <i class="fas fa-coins"></i></span>
                            <span class="price">Rp 15.000</span>
                        </span>
                    </label>
                    <label class="robux-option">
                        <input type="radio" name="robux" value="100 Robux">
                        <span class="info">
                            <span class="robux">100 Robux <i class="fas fa-coins"></i></span>
                            <span class="price">Rp 30.000</span>
                        </span>
                    </label>
                    <label class="robux-option">
                        <input type="radio" name="robux" value="200 Robux">
                        <span class="info">
                            <span class="robux">200 Robux <i class="fas fa-coins"></i></span>
                            <span class="price">Rp 40.000</span>
                        </span>
                    </label>
                    <label class="robux-option">
                        <input type="radio" name="robux" value="500 Robux">
                        <span class="info">
                            <span class="robux">500 Robux <i class="fas fa-coins"></i></span>
                            <span class="price">Rp 100.000</span>
                        </span>
                    </label>
                    <label class="robux-option">
                        <input type="radio" name="robux" value="1000 Robux">
                        <span class="info">
                            <span class="robux">1,000 Robux <i class="fas fa-coins"></i></span>
                            <span class="price">Rp 150.000</span>
                        </span>
                    </label>
                </div>

                <div class="section-title">
                    <i class="fas fa-wallet"></i>
                    <span>Metode Pembayaran</span>
                </div>
                <div class="payment-grid">
                    <label class="payment-item">
                        <input type="radio" name="robloxPayment" value="DANA">
                        <i class="fas fa-money-bill-wave"></i>
                        <span>DANA</span>
                    </label>
                    <label class="payment-item">
                        <input type="radio" name="robloxPayment" value="QRIS">
                        <i class="fas fa-qrcode"></i>
                        <span>QRIS</span>
                    </label>
                    <label class="payment-item">
                        <input type="radio" name="robloxPayment" value="OVO">
                        <i class="fas fa-mobile-alt"></i>
                        <span>OVO</span>
                    </label>
                    <label class="payment-item">
                        <input type="radio" name="robloxPayment" value="Gopay">
                        <i class="fas fa-google-pay"></i>
                        <span>Gopay</span>
                    </label>
                </div>

                <button type="submit" class="confirm-btn">
                    <i class="fas fa-check-circle"></i> CONFIRM
                </button>
            </form>
        </div>

        <!-- Halaman Sukses -->
        <div id="success-page" class="game-content">
            <div class="success-page">
                <div class="success-icon">
                    <i class="fas fa-check-circle"></i>
                </div>
                <h2 style="color: white; margin-bottom: 20px;">TRANSAKSI BERHASIL!</h2>
                
                <div class="success-details" id="successDetails">
                    <!-- Akan diisi JavaScript -->
                </div>

                <div class="note" id="successNote">
                    <!-- Note khusus -->
                </div>

                <button class="back-btn" onclick="backToMain()">
                    <i class="fas fa-arrow-left"></i> Kembali ke Menu
                </button>
            </div>
        </div>

        <div class="fun-footer">
            © 2025 DANZX STORE • top up terpercaya (di jamin amanah✅)
        </div>
    </div>

    <script>
        function selectGame(game) {
            document.querySelectorAll('.game-content').forEach(content => content.classList.remove('active'));
            if (game === 'ff') {
                document.getElementById('ff-page').classList.add('active');
            } else if (game === 'roblox') {
                document.getElementById('roblox-page').classList.add('active');
            }
        }

        function backToMain() {
            document.querySelectorAll('.game-content').forEach(content => content.classList.remove('active'));
            document.getElementById('main-page').classList.add('active');
        }

        function processTopUp(game) {
            if (game === 'ff') {
                const userId = document.getElementById('ffId').value.trim();
                const diamond = document.querySelector('input[name="ffDiamond"]:checked');
                const payment = document.querySelector('input[name="ffPayment"]:checked');

                if (!userId) {
                    alert('📛 Masukkan ID Free Fire dulu ya!');
                    return;
                }
                if (!diamond) {
                    alert('🔥 Pilih nominal diamond terlebih dahulu!');
                    return;
                }
                if (!payment) {
                    alert('💳 Pilih metode pembayaran!');
                    return;
                }

                showSuccessPage({
                    game: 'Free Fire',
                    uid: userId,  // Menggunakan uid untuk Free Fire
                    item: diamond.value,
                    payment: payment.value
                });

            } else if (game === 'roblox') {
                const username = document.getElementById('robloxUser').value.trim();
                const robux = document.querySelector('input[name="robux"]:checked');
                const payment = document.querySelector('input[name="robloxPayment"]:checked');

                if (!username) {
                    alert('📛 Masukkan username Roblox dulu ya!');
                    return;
                }
                if (!robux) {
                    alert('🔥 Pilih nominal Robux terlebih dahulu!');
                    return;
                }
                if (!payment) {
                    alert('💳 Pilih metode pembayaran!');
                    return;
                }

                showSuccessPage({
                    game: 'Roblox',
                    username: username,
                    item: robux.value,
                    payment: payment.value
                });
            }
        }

        function showSuccessPage(data) {
            document.querySelectorAll('.game-content').forEach(content => content.classList.remove('active'));
            document.getElementById('success-page').classList.add('active');

            const details = document.getElementById('successDetails');
            
            // Tampilkan UID untuk Free Fire, Username untuk Roblox
            if (data.game === 'Free Fire') {
                details.innerHTML = `
                    <p><i class="fas fa-gamepad"></i> Game: ${data.game}</p>
                    <p><i class="fas fa-id-card"></i> UID: ${data.uid}</p>
                    <p><i class="fas fa-shopping-cart"></i> Item: ${data.item}</p>
                    <p><i class="fas fa-credit-card"></i> Pembayaran: ${data.payment}</p>
                `;
            } else {
                details.innerHTML = `
                    <p><i class="fas fa-gamepad"></i> Game: ${data.game}</p>
                    <p><i class="fas fa-user"></i> Username: ${data.username}</p>
                    <p><i class="fas fa-shopping-cart"></i> Item: ${data.item}</p>
                    <p><i class="fas fa-credit-card"></i> Pembayaran: ${data.payment}</p>
                `;
            }

            const note = document.getElementById('successNote');
            if (data.game === 'Roblox') {
                note.innerHTML = '<i class="fas fa-clock"></i> Tunggu selama 7 hari agar Robux kamu masuk';
                note.style.display = 'block';
            } else {
                note.style.display = 'none';
            }
        }

        document.getElementById('ffId').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                e.preventDefault();
                processTopUp('ff');
            }
        });

        document.getElementById('robloxUser').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                e.preventDefault();
                processTopUp('roblox');
            }
        });
    </script>
</body>
</html>
