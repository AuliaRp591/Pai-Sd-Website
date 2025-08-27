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
