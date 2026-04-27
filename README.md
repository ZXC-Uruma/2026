<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AnimeVerse — лендинг аниме</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: Arial, sans-serif;
      background: #0b1026;
      color: #ffffff;
      overflow-x: hidden;
    }

    header {
      width: 100%;
      padding: 24px 8%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      position: fixed;
      top: 0;
      left: 0;
      z-index: 10;
      background: rgba(11, 16, 38, 0.75);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    }

    .logo {
      font-size: 26px;
      font-weight: 800;
      letter-spacing: 1px;
    }

    .logo span {
      color: #ff4fd8;
    }

    nav a {
      color: #ffffff;
      text-decoration: none;
      margin-left: 28px;
      font-size: 15px;
      opacity: 0.85;
      transition: 0.3s;
    }

    nav a:hover {
      color: #ff4fd8;
      opacity: 1;
    }

    .hero {
      min-height: 100vh;
      padding: 140px 8% 80px;
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      align-items: center;
      gap: 50px;
      background:
        radial-gradient(circle at 75% 25%, rgba(255, 79, 216, 0.35), transparent 30%),
        radial-gradient(circle at 20% 75%, rgba(79, 190, 255, 0.25), transparent 32%),
        #0b1026;
    }

    .hero-text h1 {
      font-size: clamp(42px, 7vw, 82px);
      line-height: 1.05;
      margin-bottom: 24px;
    }

    .hero-text h1 span {
      color: #ff4fd8;
      text-shadow: 0 0 30px rgba(255, 79, 216, 0.7);
    }

    .hero-text p {
      max-width: 560px;
      font-size: 18px;
      line-height: 1.7;
      color: #cfd6ff;
      margin-bottom: 34px;
    }

    .buttons {
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
    }

    .btn {
      display: inline-block;
      padding: 15px 26px;
      border-radius: 999px;
      text-decoration: none;
      font-weight: 700;
      transition: 0.3s;
    }

    .btn-primary {
      color: white;
      background: linear-gradient(135deg, #ff4fd8, #7c5cff);
      box-shadow: 0 12px 35px rgba(255, 79, 216, 0.35);
    }

    .btn-primary:hover {
      transform: translateY(-4px);
      box-shadow: 0 18px 45px rgba(255, 79, 216, 0.5);
    }

    .btn-secondary {
      color: white;
      border: 1px solid rgba(255, 255, 255, 0.3);
      background: rgba(255, 255, 255, 0.06);
    }

    .btn-secondary:hover {
      background: rgba(255, 255, 255, 0.14);
    }

    .poster {
      position: relative;
      min-height: 520px;
      border-radius: 32px;
      overflow: hidden;
      background:
        linear-gradient(rgba(11, 16, 38, 0.1), rgba(11, 16, 38, 0.75)),
        url('https://images.unsplash.com/photo-1618331833071-ce81bd50d300?auto=format&fit=crop&w=900&q=80') center/cover;
      box-shadow: 0 30px 90px rgba(0, 0, 0, 0.45);
      border: 1px solid rgba(255, 255, 255, 0.14);
    }

    .poster-card {
      position: absolute;
      left: 24px;
      right: 24px;
      bottom: 24px;
      padding: 22px;
      border-radius: 24px;
      background: rgba(255, 255, 255, 0.12);
      backdrop-filter: blur(18px);
      border: 1px solid rgba(255, 255, 255, 0.18);
    }

    .poster-card h3 {
      font-size: 24px;
      margin-bottom: 8px;
    }

    .poster-card p {
      color: #e4e7ff;
      line-height: 1.5;
    }

    section {
      padding: 90px 8%;
    }

    .section-title {
      text-align: center;
      font-size: clamp(32px, 5vw, 52px);
      margin-bottom: 18px;
    }

    .section-subtitle {
      text-align: center;
      color: #b8c0ee;
      max-width: 650px;
      margin: 0 auto 50px;
      line-height: 1.7;
    }

    .anime-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 26px;
    }

    .anime-card {
      padding: 28px;
      border-radius: 28px;
      background: linear-gradient(180deg, rgba(255, 255, 255, 0.11), rgba(255, 255, 255, 0.04));
      border: 1px solid rgba(255, 255, 255, 0.12);
      transition: 0.3s;
    }

    .anime-card:hover {
      transform: translateY(-10px);
      border-color: rgba(255, 79, 216, 0.55);
      box-shadow: 0 20px 55px rgba(255, 79, 216, 0.15);
    }

    .anime-card .emoji {
      font-size: 42px;
      margin-bottom: 20px;
    }

    .anime-card h3 {
      font-size: 24px;
      margin-bottom: 12px;
    }

    .anime-card p {
      color: #cbd2ff;
      line-height: 1.6;
    }

    .features {
      background: #111735;
    }

    .feature-wrap {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px;
      align-items: center;
    }

    .feature-box {
      padding: 32px;
      border-radius: 28px;
      background: rgba(255, 255, 255, 0.07);
      border: 1px solid rgba(255, 255, 255, 0.1);
    }

    .feature-box h2 {
      font-size: 38px;
      margin-bottom: 18px;
    }

    .feature-box p {
      color: #cbd2ff;
      line-height: 1.7;
      margin-bottom: 18px;
    }

    .feature-list {
      list-style: none;
    }

    .feature-list li {
      padding: 12px 0;
      color: #eef1ff;
    }

    .feature-list li::before {
      content: '✦';
      color: #ff4fd8;
      margin-right: 10px;
    }

    .cta {
      text-align: center;
      background:
        radial-gradient(circle at center, rgba(255, 79, 216, 0.22), transparent 45%),
        #0b1026;
    }

    .cta h2 {
      font-size: clamp(34px, 5vw, 58px);
      margin-bottom: 18px;
    }

    .cta p {
      color: #cbd2ff;
      max-width: 620px;
      margin: 0 auto 32px;
      line-height: 1.7;
    }

    footer {
      padding: 30px 8%;
      text-align: center;
      color: #9ca6db;
      border-top: 1px solid rgba(255, 255, 255, 0.08);
    }

    @media (max-width: 900px) {
      header {
        padding: 20px 6%;
      }

      nav {
        display: none;
      }

      .hero {
        grid-template-columns: 1fr;
        padding: 120px 6% 70px;
      }

      .poster {
        min-height: 420px;
      }

      section {
        padding: 70px 6%;
      }

      .anime-grid,
      .feature-wrap {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="logo">Anime<span>Verse</span></div>
    <nav>
      <a href="#popular">Популярное</a>
      <a href="#features">Почему мы</a>
      <a href="#join">Войти</a>
    </nav>
  </header>

  <main>
    <section class="hero">
      <div class="hero-text">
        <h1>Открой мир <span>аниме</span> без границ</h1>
        <p>
          Смотри новые серии, собирай любимые тайтлы в коллекцию и находи аниме по настроению — от романтики до киберпанка.
        </p>
        <div class="buttons">
          <a class="btn btn-primary" href="#join">Начать смотреть</a>
          <a class="btn btn-secondary" href="#popular">Топ аниме</a>
        </div>
      </div>

      <div class="poster">
        <div class="poster-card">
          <h3>Новая подборка недели</h3>
          <p>Фэнтези, экшен и школьная романтика — всё в одном месте.</p>
        </div>
      </div>
    </section>

    <section id="popular">
      <h2 class="section-title">Популярные жанры</h2>
      <p class="section-subtitle">Выбирай настроение и погружайся в истории с яркими героями, эпичными битвами и красивой атмосферой.</p>

      <div class="anime-grid">
        <article class="anime-card">
          <div class="emoji">⚔️</div>
          <h3>Сёнен</h3>
          <p>Динамичные битвы, рост героя, дружба и большие мечты.</p>
        </article>
        <article class="anime-card">
          <div class="emoji">🌸</div>
          <h3>Романтика</h3>
          <p>Тёплые истории о чувствах, школе, встречах и первых признаниях.</p>
        </article>
        <article class="anime-card">
          <div class="emoji">🚀</div>
          <h3>Фантастика</h3>
          <p>Будущее, технологии, космос и загадочные миры.</p>
        </article>
      </div>
    </section>

    <section class="features" id="features">
      <div class="feature-wrap">
        <div class="feature-box">
          <h2>Почему AnimeVerse?</h2>
          <p>Удобный интерфейс, быстрый поиск и стильные подборки для фанатов аниме любого уровня.</p>
          <ul class="feature-list">
            <li>Подборки по жанрам и настроению</li>
            <li>Адаптивный дизайн для телефона и ПК</li>
            <li>Красивые карточки и современный UI</li>
          </ul>
        </div>
        <div class="feature-box">
          <h2>Каждый день новые тайтлы</h2>
          <p>Следи за новинками сезона, сохраняй любимое и открывай неожиданные истории.</p>
          <a class="btn btn-primary" href="#join">Присоединиться</a>
        </div>
      </div>
    </section>

    <section class="cta" id="join">
      <h2>Готов начать своё аниме-путешествие?</h2>
      <p>Создай коллекцию любимых тайтлов и найди следующий сериал, который захочется посмотреть за один вечер.</p>
      <a class="btn btn-primary" href="#">Смотреть сейчас</a>
    </section>
  </main>

  <footer>
    © 2026 AnimeVerse. Лендинг создан на HTML и CSS.
  </footer>
</body>
</html>
