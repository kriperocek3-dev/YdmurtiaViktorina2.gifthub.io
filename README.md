# YdmurtiaViktorina2.gifthub.io
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Викторина: Удмуртия</title>
  <style>
    :root{
      --bg: #f2f2f4;
      --card: #ffffff;
      --text: #1f2937;
      --muted: #6b7280;
      --accent: #6b7280;
      --shadow: 0 4px 12px rgba(0,0,0,.08);
      --radius: 12px;
      --green: #10b981;
      --red: #f87171;
      --blue: #3b82f6;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: Arial, Helvetica, sans-serif;
      background: var(--bg);
      color: var(--text);
    }
    header{
      text-align:center;
      padding: 20px 16px 12px;
    }
    h1{margin:0;font-size:22px;letter-spacing:.2px}
    .container{
      max-width: 900px;
      margin: 0 auto;
      padding: 0 12px 40px;
    }
    .card{
      background: var(--card);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 18px;
      display: flex;
      gap: 16px;
      align-items: center;
      min-height: 180px;
    }
    .card img{
      width: 260px;
      height: 160px;
      object-fit: cover;
      border-radius: 10px;
      flex-shrink: 0;
    }
    .card .content{flex:1}
    .title{font-size:20px;margin:0 0 6px}
    .subtitle{color:var(--muted); margin:0 0 12px}
    .options{list-style:none;padding:0;margin:0 0 6px;display:grid;gap:8px}
    .option{background:#f8f9fa;border:1px solid #e5e7eb;border-radius:8px;padding:10px 12px;cursor:pointer;user-select:none}
    .option.selected{outline:2px solid var(--blue); background:#eef6ff}
    .option.correct{border-color:var(--green); background:#e6ffed}
    .option.incorrect{border-color:var(--red); background:#ffecec}
    .controls{display:flex;gap:10px;justify-content:flex-end;margin-top:8px}
    .btn{
      padding:10px 14px;border-radius:8px;border:1px solid #d1d5db;background:#fff;
      cursor:pointer;
    }
    .btn.primary{background:#e5e7eb;border-color:#d1d5db}
    .hidden{display:none}
    footer{text-align:center;color:var(--muted);font-size:12px;margin-top:10px}
    @media (max-width: 720px){
      .card{flex-direction:column; align-items: flex-start}
      .card img{width:100%;height:180px}
    }
  </style>
</head>
<body>
  <header>
    <div class="container">
      <h1>Викторина на тему Удмуртской Республики</h1>
      <p class="subtitle">Проверь свои знания о Удмуртии. Удачи!</p>
    </div>
  </header>

  <main class="container" id="quiz">

    <!-- Обложка (Страница 1) -->
    <section id="page-0" class="card" aria-label="Обложка">
      <img src="https://picsum.photos/seed/udmurtia-cover/600/400" alt="Обложка викторины">
      <div class="content">
        <h2 class="title">Викторина на тему Удмуртской Республики</h2>
        <p class="subtitle">Увлекательное путешествие по истории, культуре и географии региона.</p>
        <div class="controls">
          <button class="btn" id="startBtn">Начать викторину</button>
        </div>
      </div>
    </section>

    <!-- Вопрос 1: национальности (Страница 2) -->
    <section id="page-1" class="hidden" aria-label="Вопрос 1">
      <div class="card">
        <img src="https://picsum.photos/seed/udmurtia-ethnicity/600/400" alt="Национальности Удмуртии">
        <div class="content">
          <h3 class="title">Сколько национальностей проживает в Удмуртии, и каков их процентный вклад?</h3>
          <p class="subtitle">Выберите наиболее близкое по данным ответ.</p>
          <ul class="options" id="options-1"></ul>
          <div class="controls">
            <button class="btn" id="next-1" disabled>Далее</button>
          </div>
        </div>
      </div>
    </section>

    <!-- Вопрос 2: памятники (Страница 3) -->
    <section id="page-2" class="hidden" aria-label="Вопрос 2">
      <div class="card">
        <img src="https://picsum.photos/seed/udmurtia-monuments/600/400" alt="Памятники Удмуртии">
        <div class="content">
          <h3 class="title">Памятники Удмуртии: какой из них является известной достопримечательностью?</h3>
          <p class="subtitle">Выберите правильный вариант.</p>
          <ul class="options" id="options-2"></ul>
          <div class="controls">
            <button class="btn" id="next-2" disabled>Далее</button>
          </div>
        </div>
      </div>
    </section>

    <!-- Вопрос 3: учебные заведения (Страница 4) -->
    <section id="page-3" class="hidden" aria-label="Вопрос 3">
      <div class="card">
        <img src="https://picsum.photos/seed/udmurtia-university/600/400" alt="Учебные заведения Удмуртии">
        <div class="content">
          <h3 class="title">Учебные заведения Удмуртии: какое из них является известным вузом?</h3>
          <p class="subtitle">Выберите правильный вариант.</p>
          <ul class="options" id="options-3"></ul>
          <div class="controls">
            <button class="btn" id="next-3" disabled>Далее</button>
          </div>
        </div>
      </div>
    </section>

    <!-- Вопрос 4: география (Страница 5) -->
    <section id="page-4" class="hidden" aria-label="Вопрос 4">
      <div class="card">
        <img src="https://picsum.photos/seed/udmurtia-map/600/400" alt="Географическое положение Удмуртии">
        <div class="content">
          <h3 class="title">Географическое положение Удмуртии: через какую реку проходит республика?</h3>
          <p class="subtitle">Выберите правильный вариант.</p>
          <ul class="options" id="options-4"></ul>
          <div class="controls">
            <button class="btn" id="next-4" disabled>Далее</button>
          </div>
        </div>
      </div>
    </section>

    <!-- Вопрос 5: культура (Страница 6) -->
    <section id="page-5" class="hidden" aria-label="Вопрос 5">
      <div class="card">
        <img src="https://picsum.photos/seed/udmurtia-culture/600/400" alt="Культура Удмуртии">
        <div class="content">
          <h3 class="title">Культура Удмуртии: какой элемент является характерной культурной особенностью?</h3>
          <p class="subtitle">Выберите правильный вариант.</p>
          <ul class="options" id="options-5"></ul>
          <div class="controls">
            <button class="btn" id="finishBtn" disabled>Завершить</button>
          </div>
        </div>
      </div>
    </section>

    <!-- Результаты -->
    <section id="results" class="hidden" aria-label="Результаты">
      <div class="card" style="align-items:stretch;flex-direction:column;">
        <img src="https://picsum.photos/seed/udmurtia-result/600/400" alt="Результаты викторины" style="width:100%;height:200px;object-fit:cover;border-radius:10px;">
        <div class="content">
          <h3 class="title" style="margin-top:8px;">Результат викторины</h3>
          <p class="subtitle" id="scoreText">Баллы: 0 из 5</p>
          <p class="subtitle" id="details"></p>
          <div class="controls" style="justify-content: flex-start">
            <button class="btn" id="retryBtn">Попробовать снова</button>
            <button class="btn" id="toStartBtn">На обложку</button>
          </div>
        </div>
      </div>
    </section>

  </main>

  <footer>© 2026 Викторина по Удмуртии</footer>

  <script>
    // Вопросы и варианты. Правильные индексы указаны в полях correctIndex (0-based)
    const q1 = {
      prompt: "Сколько национальностей проживает в Удмуртии, и каков их процентный вклад?",
      options: [
        "Русские — 64%, Удмурты — 20%, Таты — 8%, Другие — 8%",
        "Русские — 50%, Удмурты — 30%, Татар — 15%, Другие — 5%",
        "Удмурты — 40%, Русские — 35%, Башкиры — 15%, Другие — 10%",
        "Русские — 70%, Удмурты — 10%, Таты — 10%, Другие — 10%"
      ],
      correctIndex: 0
    };
    const q2 = {
      prompt: "Памятники Удмуртии: какой из них является известной достопримечательностью?",
      options: [
        "Музей Удмуртского народа",
        "Храм Нерукотворного Образа",
        "Ижевский музей оружия",
        "Сычевский монастырь"
      ],
      correctIndex: 2
    };
    const q3 = {
      prompt: "Учебные заведения Удмуртии: какое из них является известным вузом?",
      options: [
        "Удмуртский государственный университет (УдГУ)",
        "ИжГМТУ",
        "Институт архитектуры Удмуртии",
        "Санкт-Петербургский государственный университет"
      ],
      correctIndex: 0
    };
    const q4 = {
      prompt: "Географическое положение Удмуртии: через какую реку проходит республика?",
      options: [
        "Кама",
        "Иртыш",
        "Волга",
        "Сырудка"
      ],
      correctIndex: 0
    };
    const q5 = {
      prompt: "Культура Удмуртии: какой элемент является характерной культурной особенностью?",
      options: [
        "Гастионы",
        "Мошкари, кукла-идолов",
        "Игровой турнир по хоккею",
        "Народная музыка и танцы с удмуртскими элементами"
      ],
      correctIndex: 3
    };

    const pages = [
      "page-0","page-1","page-2","page-3","page-4","page-5","results"
    ];

    let current = 0; // 0 - обложка, 1..5 - вопросы, 6 - результаты
    let score = 0;
    const userAnswers = [];

    const sections = {
      0: document.getElementById("page-0"),
      1: document.getElementById("page-1"),
      2: document.getElementById("page-2"),
      3: document.getElementById("page-3"),
      4: document.getElementById("page-4"),
      5: document.getElementById("page-5"),
      6: document.getElementById("results")
    };

    function showPage(n){
      // скрыть все страницы
      for(let i=0;i<7;i++){
        const el = document.getElementById(`page-${i}`);
        if(el) el.classList.add("hidden");
      }
      // показать нужную
      if(n>=0 && n<=5){
        sections[n].classList.remove("hidden");
      } else if(n===6){
        sections[6].classList.remove("hidden");
      }
    }

    function renderResult(){
      const scoreText = document.getElementById("scoreText");
      const details = document.getElementById("details");
      scoreText.textContent = `Баллы: ${score} из 5`;
      // детальная разбивка по вопросам
      let breakdown = [];
      const preds = [q1.correctIndex, q2.correctIndex, q3.correctIndex, q4.correctIndex, q5.correctIndex];
      for(let i=0;i<5;i++){
        const got = userAnswers[i] != null ? userAnswers[i] : -1;
        const ok = got === preds[i];
        breakdown.push(`Вопрос ${i+1}: ${ok ? "правильно" : "неправильно"}`);
      }
      details.textContent = breakdown.join(" | ");
    }

    // Initialize options renderers
    function renderQuestionOptions(qObj, containerId, onSelect){
      const ul = document.getElementById(containerId);
      ul.innerHTML = "";
      qObj.options.forEach((opt, idx) => {
        const li = document.createElement("li");
        li.className = "option";
        li.textContent = opt;
        li.addEventListener("click", ()=> {
          // снять выделение с других
          ul.querySelectorAll(".option").forEach(o => o.classList.remove("selected"));
          li.classList.add("selected");
          onSelect(idx);
        });
        ul.appendChild(li);
      });
    }

    // Q1
    function prepareQ1(){
      renderQuestionOptions(q1, "options-1", (idx) => {
        userAnswers[0] = idx;
        // разблокировать кнопку
        document.getElementById("next-1").disabled = false;
      });
    }
    // Q2
    function prepareQ2(){
      renderQuestionOptions(q2, "options-2", (idx) => {
        userAnswers[1] = idx;
        document.getElementById("next-2").disabled = false;
      });
    }
    // Q3
    function prepareQ3(){
      renderQuestionOptions(q3, "options-3", (idx) => {
        userAnswers[2] = idx;
        document.getElementById("next-3").disabled = false;
      });
    }
    // Q4
    function prepareQ4(){
      renderQuestionOptions(q4, "options-4", (idx) => {
        userAnswers[3] = idx;
        document.getElementById("next-4").disabled = false;
      });
    }
    // Q5
    function prepareQ5(){
      renderQuestionOptions(q5, "options-5", (idx) => {
        userAnswers[4] = idx;
        document.getElementById("finishBtn").disabled = false;
      });
    }

    // Start button
    document.getElementById("startBtn").addEventListener("click", ()=> {
      current = 1;
      score = 0;
      // очистка ответов
      userAnswers.length = 0;
      showPage(1);
      prepareQ1();
      // сброс кнопок
      document.getElementById("next-1").disabled = true;
    });

    // Включение переходов между страницами
    document.getElementById("next-1").addEventListener("click", ()=> {
      // проверить правильность первого ответа и учесть балл
      if (typeof userAnswers[0] === "number" && userAnswers[0] === q1.correctIndex) score++;
      current = 2;
      showPage(2);
      prepareQ2();
    });

    document.getElementById("next-2").addEventListener("click", ()=> {
      if (typeof userAnswers[1] === "number" && userAnswers[1] === q2.correctIndex) score++;
      current = 3;
      showPage(3);
      prepareQ3();
    });

    document.getElementById("next-3").addEventListener("click", ()=> {
      if (typeof userAnswers[2] === "number" && userAnswers[2] === q3.correctIndex) score++;
      current = 4;
      showPage(4);
      prepareQ4();
    });

    document.getElementById("next-4").addEventListener("click", ()=> {
      if (typeof userAnswers[3] === "number" && userAnswers[3] === q4.correctIndex) score++;
      current = 5;
      showPage(5);
      prepareQ5();
    });

    document.getElementById("finishBtn").addEventListener("click", ()=> {
      if (typeof userAnswers[4] === "number" && userAnswers[4] === q5.correctIndex) score++;
      // переход к результатам
      current = 6;
      showPage(6);
      renderResult();
    });

    // Рестарт и возврат на обложку
    document.getElementById("retryBtn").addEventListener("click", ()=> {
      // вернуть к обложке
      current = 0;
      showPage(0);
    });
    document.getElementById("toStartBtn").addEventListener("click", ()=> {
      current = 0;
      showPage(0);
    });

    // По умолчанию скрыть все кроме обложки
    showPage(0);
  </script>

</body>
</html>
