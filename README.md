
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
   
    <style>
        /* Mengambil font elegan dari Google Fonts */
        @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600&family=Great+Vibes&family=Playfair+Display:ital,wght@0,400;0,600;1,400&display=swap');
        /* Gaya Tambahan untuk Formulir RSVP */
        .rsvp-form {
            background-color: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(210, 166, 90, 0.3);
            padding: 25px;
            border-radius: 10px;
            width: 85%;
            max-width: 400px;
            box-sizing: border-box;
            margin: 20px 0;
        }

        .form-input {
            width: 100%;
            padding: 12px;
            margin-bottom: 15px;
            border: 1px solid #d2a65a;
            background-color: rgba(0, 0, 0, 0.2);
            color: #fff;
            border-radius: 5px;
            font-family: 'Playfair Display', serif;
            box-sizing: border-box;
            font-size: 0.9rem;
        }

        .form-input::placeholder {
            color: rgba(255, 255, 255, 0.6);
        }

        .form-input:focus {
            outline: none;
            border-color: #fff;
            background-color: rgba(0, 0, 0, 0.4);
        }

        .btn-kirim {
            width: 100%;
            padding: 12px;
            background-color: #d2a65a;
            color: #55131b;
            border: none;
            border-radius: 5px;
            font-family: 'Cinzel', serif;
            font-weight: 600;
            font-size: 0.9rem;
            cursor: pointer;
            transition: background 0.3s;
        }

        .btn-kirim:hover {
            background-color: #e5ba6e;
        }

        /* Pengaturan Dasar */
        body, html {
            margin: 0;
            padding: 0;
            background-color: #55131b; /* Warna Burgundy/Marun Gelap */
            color: #ffffff;
            font-family: 'Playfair Display', serif;
            scroll-behavior: smooth; /* Efek scroll halus */
        }

        /* Warna Emas untuk Teks Khusus */
        .gold {
            color: #d2a65a;
        }

        /* Pengaturan Setiap Halaman (Satu Layar Penuh) */
        .page {
            height: 100vh;
            width: 100vw;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 20px;
            box-sizing: border-box;
            position: relative;
        }
        /* Gaya Tombol Musik Melayang */
        #musicBtn {
            position: fixed;
            bottom: 25px;
            right: 25px;
            width: 50px;
            height: 50px;
            background-color: #d2a65a;
            color: #55131b;
            border: 2px solid #fff;
            border-radius: 50%;
            font-size: 1.5rem;
            cursor: pointer;
            z-index: 9999; /* Memastikan tombol selalu berada di lapisan paling atas */
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
            transition: transform 0.3s ease;
        }

        /* Efek berputar lambat saat musik menyala (Opsional tapi keren) */
        .spinning {
            animation: spin 3s linear infinite;
        }
        @keyframes spin {
            100% { transform: rotate(360deg); }
        }
<audio id="weddingMusic" loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>


    <button id="musicBtn" onclick="toggleMusic()">🎵</button>

        /* Ornamen Atas dan Bawah meniru pola di video */
        .ornament {
            font-size: 1.2rem;
            color: #d2a65a;
            letter-spacing: 5px;
            margin: 30px 0;
            opacity: 0.8;
        }

        .ornament::before {
            content: "❖ ┈ ❖ ┈ ❖"; /* Pola pengganti batik/bintang */
        }

        /* Tipografi */
        h1, h2, h3, h4 {
            margin: 0;
            font-weight: normal;
        }

        .subtitle {
            font-family: 'Cinzel', serif;
            font-size: 0.9rem;
            letter-spacing: 3px;
            margin-bottom: 20px;
        }

        .initials {
            font-family: 'Great Vibes', cursive;
            font-size: 5rem;
            line-height: 1;
            margin: 10px 0;
            color: #d2a65a;
        }

        .names {
            font-family: 'Great Vibes', cursive;
            font-size: 3.5rem;
            color: #d2a65a;
            margin: 20px 0;
            line-height: 1.2;
        }

        .date-number {
            font-family: 'Cinzel', serif;
            font-size: 3rem;
            color: #d2a65a;
            margin: 5px 0;
        }

        .text-regular {
            font-size: 0.95rem;
            line-height: 1.6;
            margin: 15px 0;
            font-style: italic;
            max-width: 80%;
        }

        .address-box {
            font-family: 'Cinzel', serif;
            font-size: 0.8rem;
            letter-spacing: 1px;
            line-height: 1.8;
            margin-top: 20px;
        }

        .hashtag {
            font-family: 'Cinzel', serif;
            font-size: 0.75rem;
            letter-spacing: 2px;
            margin-top: 30px;
            border: 1px solid #d2a65a;
            padding: 8px 15px;
            border-radius: 5px;
            color: #d2a65a;
        }
        #musicBtn {
    position: fixed;
    bottom: 25px;
    right: 25px;
    width: 50px;
    height: 50px;
    background-color: #d2a65a; /* Warna Emas */
    color: #55131b; /* Warna Marun */
    border: 2px solid #fff;
    border-radius: 50%;
    font-size: 1.5rem;
    cursor: pointer;
    z-index: 99999 !important; /* Kita naikkan nilainya dan beri !important agar mutlak di paling atas */
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 4px 10px rgba(0,0,0,0.3);
}

        /* Efek Panah Scroll di Halaman 1 */
        .scroll-down {
            position: absolute;
            bottom: 30px;
            font-size: 0.8rem;
            color: #d2a65a;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {transform: translateY(0);}
            40% {transform: translateY(-10px);}
            60% {transform: translateY(-5px);}
        }
                /* Footer */
        footer {
            background-color: var(webkit-box-decoration-break: );
            color: black;
            text-align: center;
            padding: 20px;
            margin-top: 50px;
        }
    </style>
</head>
<body>

    <section class="page" id="page1">
        <div class="ornament"></div>
        <div class="subtitle">UNDANGAN PERNIKAHAN</div>
        
        <div class="initials">KR</div>
        
        <div class="text-regular" style="font-style: normal; margin-top: 30px;">
            <span class="gold">08.06.2026</span>
        </div>
        <div class="ornament"></div>
        <div class="scroll-down">Scroll ke bawah ↓</div>
    </section>

    <section class="page" id="page2">
        <div class="ornament"></div>
        <p class="text-regular">
            Dengan rahmat Tuhan Yang Maha Esa,<br>
            kami mengundang Anda untuk hadir dalam acara<br>
            pernikahan kami.
        </p>
        
        <div class="names">
            Ayman Kudus<br>
            <span style="font-size: 2.5rem;">&</span><br>
            Ririn
        </div>
        <div class="ornament"></div>
    </section>

    <section class="page" id="page3">
        <div class="ornament"></div>
        
        <div class="text-regular" style="font-style: italic;">Senin</div>
        <div class="date-number">08</div>
        <div class="subtitle gold" style="margin-bottom: 30px;">JUNI 2026</div>

        <div class="text-regular" style="font-style: italic; margin-bottom: 0;">Pukul</div>
        <div class="date-number" style="font-size: 2.5rem;">08.00</div>
        <div class="subtitle gold" style="font-size: 0.75rem;">SAMPAI SELESAI</div>

        <div class="address-box">
            TEMPAT KEDIAMAN MEMPELAI WANITA<br>
            KP. BOJONG LOA, RT. 01, RW. 03,<br>
            DESA CIBITUNG, KECAMATAN RONGGA
        </div>
        <div class="ornament"></div>
    </section>

    <section class="page" id="page4">
            <section class="page" id="page4" style="height: auto; padding: 40px 20px;">
        <div class="ornament"></div>
        
        <div class="initials" style="font-size: 3rem;">KR</div>
        
        <p class="text-regular">
            Kehadiran Anda akan<br>
            sangat berarti bagi kami,<br>
            terima kasih!
        </p>

        <div class="rsvp-form">
            <h3 class="gold" style="font-family: 'Cinzel', serif; font-size: 1rem; letter-spacing: 2px; margin-bottom: 20px;">KONFIRMASI KEHADIRAN</h3>
            
            <form action="https://formsubmit.co/dedenabdulaziz98@gmail.com" method="POST">
    
    <input type="hidden" name="_captcha" value="false">

    <input type="text" name="Nama Tamu" placeholder="Nama Lengkap Anda" required class="form-input">
    
    <select name="Status Kehadiran" required class="form-input">
        <option value="" disabled selected style="color: #333;">Apakah Anda akan hadir?</option>
        <option value="Hadir" style="color: #333;">Ya, Saya Akan Hadir</option>
        <option value="Tidak Hadir" style="color: #333;">Maaf, Saya Tidak Bisa Hadir</option>
    </select>

    <input type="number" name="Jumlah Pasangan/Tamu" placeholder="Jumlah Orang Yang Hadir" min="1" max="5" class="form-input">

    <button type="submit" class="btn-kirim">KIRIM KONFIRMASI</button>
</form>


            </form>
        </div>

        <div class="address-box" style="margin-top: 30px;">
            YANG BERBAHAGIA,<br>
            <span class="gold">KUDUS & RIRIN</span>
        </div>

        <div class="hashtag">
            #THEWEDDINGOFKUDUS&RIRIN
        </div>
        <div class="ornament"></div>
    </section>
</section> <script>
        var music = document.getElementById("weddingMusic");
        var musicBtn = document.getElementById("musicBtn");

        function toggleMusic() {
            if (music.paused) {
                music.play(); 
                musicBtn.classList.add("spinning"); 
                musicBtn.innerText = "🎵";
            } else {
                music.pause(); 
                musicBtn.classList.remove("spinning"); 
                musicBtn.innerText = "🔇";
            }
        }
        
        // Otomatis putar musik begitu tamu menyentuh atau melakukan scroll pertama kali
        document.addEventListener('click', function() {
            if (music.paused) { 
                music.play(); 
                musicBtn.classList.add("spinning"); 
            }
        }, { once: true });
        function toggleMusic() {
            if (music.paused) {
                music.play(); 
                musicBtn.classList.add("spinning"); 
                musicBtn.innerText = "🎵";
            } else {
                music.pause(); 
                musicBtn.classList.remove("spinning"); 
                musicBtn.innerText = "🔇";
            }
        }
        
        // Otomatis putar musik begitu tamu menyentuh atau melakukan scroll pertama kali
        document.addEventListener('click', function() {
            if (music.paused) { 
                music.play(); 
                musicBtn.classList.add("spinning"); 
            }
        }, { once: true });
    </script>

    <p style="text-align: center; color: rgba(255,255,255,0.3); font-size: 0.7rem; margin-bottom: 20px;">
        © 2026 D2N OFFICIAL.
    </p>

</body> </html>