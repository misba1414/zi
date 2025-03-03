<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ulang Tahun Ziyana Walidah</title>
    <style>
        body {
            background: linear-gradient(135deg, #ff9a9e, #fad0c4); /* Gradien pink */
            font-family: 'Arial', sans-serif;
            text-align: center;
            padding-top: 50px;
            margin: 0;
            overflow: hidden;
        }
        .hidden {
            display: none;
        }
        .visible {
            display: block;
        }
        button {
            padding: 15px 30px;
            font-size: 18px;
            background-color: #ff6f61; /* Warna tombol coral */
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
            transition: transform 0.2s, box-shadow 0.2s;
        }
        button:hover {
            transform: scale(1.1);
            box-shadow: 0 6px 8px rgba(0, 0, 0, 0.3);
        }
        h1 {
            color: white;
            font-size: 50px;
            margin-top: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            animation: float 3s ease-in-out infinite;
        }
        p {
            color: white;
            font-size: 24px;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
        }
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #ffcc00;
            animation: confetti-fall 5s linear infinite;
        }
        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }
        @keyframes confetti-fall {
            0% {
                transform: translateY(-100vh) rotate(0deg);
            }
            100% {
                transform: translateY(100vh) rotate(360deg);
            }
        }
    </style>
</head>
<body>
    <!-- Tombol "Masuk" -->
    <button onclick="showMessage()">Masuk</button>

    <!-- Pesan ulang tahun (awalnya tersembunyi) -->
    <div id="message" class="hidden">
        <h1>Selamat Ulang Tahun Ziyana Walidah!</h1>
        <p>Semoga panjang umur, sehat selalu, dan bahagia!</p>
    </div>

    <!-- Efek confetti -->
    <div id="confetti-container"></div>

    <!-- Efek suara -->
    <audio id="birthday-audio" src="https://www.soundjay.com/human/birthday-song-1.mp3" preload="auto"></audio>

    <script>
        // Fungsi untuk menampilkan pesan ulang tahun
        function showMessage() {
            document.body.style.opacity = '0'; // Ubah opacity halaman menjadi 0
            setTimeout(function() {
                document.getElementById('message').classList.remove('hidden'); // Tampilkan pesan
                document.getElementById('message').classList.add('visible');
                document.body.style.opacity = '1'; // Kembalikan opacity halaman ke 1
                playAudio(); // Mainkan suara ulang tahun
                createConfetti(); // Tampilkan confetti
            }, 1000); // Delay 1 detik
        }

        // Fungsi untuk memainkan suara ulang tahun
        function playAudio() {
            const audio = document.getElementById('birthday-audio');
            audio.play();
        }

        // Fungsi untuk membuat confetti
        function createConfetti() {
            const confettiContainer = document.getElementById('confetti-container');
            for (let i = 0; i < 100; i++) {
                const confetti = document.createElement('div');
                confetti.classList.add('confetti');
                confetti.style.left = `${Math.random() * 100}vw`;
                confetti.style.animationDuration = `${Math.random() * 3 + 2}s`;
                confetti.style.backgroundColor = `hsl(${Math.random() * 360}, 100%, 70%)`;
                confettiContainer.appendChild(confetti);
            }
        }
    </script>
</body>
</html>
