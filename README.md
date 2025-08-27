project-pai-sd/
│── index.html
│── style.css
│── app.js
│── assets/
│     ├── modul-akhlak.pdf
│     └── images/
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Website Pembelajaran PAI SD</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <!-- Navbar -->
  <header>
    <h1>PAI SD Online</h1>
    <nav>
      <a href="#home">Home</a>
      <a href="#kelas">Kelas</a>
      <a href="#materi">Materi</a>
      <a href="#tentang">Tentang Kami</a>
      <a href="#blog">Blog</a>
      <a href="#testimoni">Testimoni</a>
      <a href="#kontak">Kontak</a>
    </nav>
  </header>

  <!-- Home -->
  <section id="home">
    <h2>Belajar Menjadi Lebih Mudah dan Menyenangkan ✨</h2>
    <p>Platform pembelajaran PAI untuk siswa Sekolah Dasar.</p>
    <button onclick="scrollToSection('kelas')">Mulai Belajar</button>
  </section>

  <!-- Kelas -->
  <section id="kelas">
    <h2>Daftar Kelas</h2>
    <ul>
      <li><button onclick="showMateri('kelas3')">Kelas 3 - Akhlak Terpuji</button></li>
      <li><button disabled>Kelas 4 - Coming Soon</button></li>
    </ul>
  </section>

  <!-- Materi -->
  <section id="materi">
    <h2>Detail Materi</h2>
    <div id="kelas3" class="materi-detail">
      <h3>Kelas 3 – Akhlak Terpuji</h3>
      <p>Pada materi ini siswa belajar tentang pentingnya akhlak terpuji dalam kehidupan sehari-hari.</p>
      <a href="assets/modul-akhlak.pdf" target="_blank" class="btn">📖 Download Modul PDF</a>
      <div class="video-container">
        <iframe width="560" height="315" src="https://www.youtube.com/embed/yQqYXhQvA1g" title="YouTube video pembelajaran PAI" frameborder="0" allowfullscreen></iframe>
      </div>
      <button onclick="startQuiz()">Mulai Kuis</button>
      <div id="quiz"></div>
    </div>
  </section>

  <!-- Tentang Kami -->
  <section id="tentang">
    <h2>Tentang Kami</h2>
    <p>Website pembelajaran ini dibuat untuk membantu siswa SD memahami Pendidikan Agama Islam dengan cara yang interaktif dan menyenangkan.</p>
    <p><strong>Visi:</strong> Menjadi platform PAI digital terbaik untuk anak SD.</p>
    <p><strong>Misi:</strong> Memberikan pembelajaran yang mudah, interaktif, dan islami.</p>
    <p><em>👩‍💻 Dikembangkan oleh Aulia Rahmah Puteri</em></p>
  </section>

  <!-- Blog -->
  <section id="blog">
    <h2>Blog</h2>
    <article>
      <h3>Tips Belajar PAI Lebih Menyenangkan</h3>
      <p>Gunakan video, modul, dan diskusi untuk meningkatkan pemahaman siswa.</p>
    </article>
  </section>

  <!-- Testimoni -->
  <section id="testimoni">
    <h2>Testimoni</h2>
    <blockquote>"Belajar PAI jadi lebih seru!" - Siswa Kelas 3</blockquote>
    <blockquote>"Platform ini sangat membantu guru." - Guru SD</blockquote>
  </section>

  <!-- Kontak -->
  <section id="kontak">
    <h2>Kontak</h2>
    <form>
      <input type="text" placeholder="Nama" required>
      <input type="email" placeholder="Email" required>
      <textarea placeholder="Pesan"></textarea>
      <button type="submit">Kirim</button>
    </form>
    <p>Email: admin@paisd.com | WhatsApp: 0812-3456-7890</p>
    <p>Ikuti kami: Instagram | TikTok | YouTube | WhatsApp Group</p>
  </section>

  <!-- Footer -->
  <footer>
    <p>© 2025 Website Pembelajaran PAI SD | Dikembangkan oleh <strong>Aulia Rahmah Puteri</strong></p>
  </footer>

  <script src="app.js"></script>
</body>
</html>
body {
  font-family: 'Poppins', sans-serif;
  margin: 0;
  padding: 0;
  background: #f9fafc;
  color: #333;
}

header {
  background: #88c8bc;
  color: white;
  padding: 15px;
  text-align: center;
}

nav a {
  margin: 0 10px;
  color: white;
  text-decoration: none;
  font-weight: 600;
}

section {
  padding: 40px;
  text-align: center;
}

h2 {
  color: #2c3e50;
}

button, .btn {
  background: #88c8bc;
  color: white;
  border: none;
  padding: 10px 20px;
  margin: 10px;
  border-radius: 8px;
  cursor: pointer;
  text-decoration: none;
  font-size: 16px;
}

button:hover, .btn:hover {
  background: #5aa89d;
}

.video-container {
  margin: 20px auto;
  max-width: 560px;
}

footer {
  background: #2c3e50;
  color: white;
  text-align: center;
  padding: 15px;
}
function scrollToSection(id) {
  document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
}

function showMateri(id) {
  document.querySelectorAll('.materi-detail').forEach(el => {
    el.style.display = 'none';
  });
  document.getElementById(id).style.display = 'block';
}

function startQuiz() {
  const quizDiv = document.getElementById('quiz');
  quizDiv.innerHTML = `
    <h4>Kuis Akhlak Terpuji</h4>
    <p>1. Apa arti akhlak terpuji?</p>
    <button onclick="checkAnswer(true)">Perilaku baik yang diridhoi Allah</button>
    <button onclick="checkAnswer(false)">Perilaku buruk yang merugikan</button>
  `;
}

function checkAnswer(correct) {
  const quizDiv = document.getElementById('quiz');
  if (correct) {
    quizDiv.innerHTML = "<p>✅ Benar! Kamu hebat!</p>";
  } else {
    quizDiv.innerHTML = "<p>❌ Salah. Coba lagi ya!</p>";
  }
}

