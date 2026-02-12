# web-baru
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>Profil Lucu & Romantis 💕</title>

<style>
body {
    margin: 0;
    font-family: "Segoe UI", sans-serif;
    background: linear-gradient(270deg,
        #ff9a9e,
        #fad0c4,
        #a1c4fd,
        #c2e9fb,
        #fbc2eb,
        #a6c1ee
    );
    background-size: 800% 800%;
    animation: gradient 15s ease infinite;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

/* Animasi background */
@keyframes gradient {
    0% {background-position: 0% 50%;}
    50% {background-position: 100% 50%;}
    100% {background-position: 0% 50%;}
}

.container {
    background: rgba(255,255,255,0.95);
    width: 90%;
    max-width: 430px;
    padding: 30px;
    border-radius: 25px;
    box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    text-align: center;
}

h1 {
    color: #e84393;
}

input {
    width: 90%;
    padding: 10px;
    margin: 7px 0;
    border-radius: 12px;
    border: 1px solid #ccc;
    font-size: 15px;
}

button {
    background: linear-gradient(to right, #fd79a8, #74b9ff);
    color: white;
    border: none;
    padding: 12px 25px;
    border-radius: 25px;
    font-size: 15px;
    cursor: pointer;
    margin-top: 15px;
}

button:hover {
    opacity: 0.9;
}

.slide {
    display: none;
}

.active {
    display: block;
}

p {
    color: #444;
    line-height: 1.7;
    font-size: 16px;
}

.notice {
    background: #ffeaa7;
    padding: 10px;
    border-radius: 12px;
    margin: 12px 0;
    display: none;
    font-size: 14px;
}

.highlight {
    color: #e84393;
    font-weight: bold;
}

.emoji {
    font-size: 28px;
    margin-bottom: 10px;
}
</style>
</head>

<body>

<div class="container">

<!-- SLIDE 1 -->
<div class="slide active" id="slide1">
    <div class="emoji">🌸😊💗✨</div>
    <h1>Kenalan Yuk 💕</h1>

    <input type="text" id="nama" placeholder="Nama 💌">
    <input type="number" id="umur" placeholder="Umur 🎂">

    <button onclick="goSlide2()">Lanjut ➡️💞</button>
</div>

<!-- SLIDE 2 -->
<div class="slide" id="slide2">
    <div class="emoji">🌈😄🍭💙💖</div>
    <h1>Tentang Kamu ✨</h1>

    <input type="text" id="warna" placeholder="Warna Favorit 🎨">
    <input type="number" id="sepatu" placeholder="Ukuran Sepatu 👟">
    <input type="date" id="lahir">
    <input type="text" id="food" placeholder="Makanan Favorit 🍔🍕">
    <input type="text" id="drink" placeholder="Minuman Favorit 🥤🧋">

    <div class="notice" id="notice">
        🎉 Yeay! Slide 1 & 2 sudah diisi 😍💝
    </div>

    <button onclick="goSlide3()">Lanjut ➡️💓</button>
    <br><br>
    <button onclick="back1()">⬅️ Kembali 💙</button>
</div>

<!-- SLIDE 3 -->
<div class="slide" id="slide3">
    <div class="emoji">💖🥰🌟💐💝</div>
    <h1>Untuk Kamu 💕</h1>

    <p id="hasil"></p>

    <button onclick="back2()">⬅️ Kembali 💗</button>
</div>

</div>

<script>

function goSlide2() {

    let nama = document.getElementById("nama").value;
    let umur = document.getElementById("umur").value;

    if(nama === "" || umur === "") {
        alert("Isi dulu ya 😊💗");
        return;
    }

    document.getElementById("slide1").classList.remove("active");
    document.getElementById("slide2").classList.add("active");
}

function goSlide3() {

    let warna = document.getElementById("warna").value;
    let sepatu = document.getElementById("sepatu").value;
    let lahir = document.getElementById("lahir").value;
    let food = document.getElementById("food").value;
    let drink = document.getElementById("drink").value;

    if(warna === "" || sepatu === "" || lahir === "" || food === "" || drink === "") {
        alert("Lengkapi semua ya 😄💞");
        return;
    }

    document.getElementById("notice").style.display = "block";

    setTimeout(() => {
        document.getElementById("slide2").classList.remove("active");
        document.getElementById("slide3").classList.add("active");
    }, 1200);

    let nama = document.getElementById("nama").value;
    let umur = document.getElementById("umur").value;

    let teks = `
    <span class="highlight">${nama}</span> (${umur} tahun) adalah sosok yang
    cantik luar dan dalam 😊💖<br><br>

    Dengan kepribadian yang hangat,
    pintar, dan berwawasan luas 📚✨<br><br>

    Ia dikenal sebagai pribadi yang
    rajin, ulet, pekerja keras,
    dan selalu berusaha menjadi
    versi terbaik dari dirinya 💪🌟<br><br>

    Kesukaannya pada ${food} dan ${drink}
    membuatnya terlihat sederhana
    namun menyenangkan 😋🥤💗<br><br>

    Secara keseluruhan,
    ${nama} adalah pribadi yang
    membanggakan, menginspirasi,
    dan layak mendapatkan
    kebahagiaan terbaik 🌈💝🥰
    `;

    document.getElementById("hasil").innerHTML = teks;
}

function back1() {
    document.getElementById("slide2").classList.remove("active");
    document.getElementById("slide1").classList.add("active");
}

function back2() {
    document.getElementById("slide3").classList.remove("active");
    document.getElementById("slide2").classList.add("active");
}

</script>

</body>
</html>
