<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Aentigo | Coming Soon</title>
  <meta name="description" content="Aentigo connects people and opportunities instantly. Launching soon on iOS and Android." />
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      min-height: 100vh;
      font-family: Inter, Arial, sans-serif;
      background: radial-gradient(circle at top, #102a5c 0%, #071b42 38%, #050914 100%);
      color: #ffffff;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
    }

    .page {
      width: 100%;
      max-width: 1120px;
      min-height: 680px;
      border: 1px solid rgba(255,255,255,0.12);
      border-radius: 32px;
      background: rgba(255,255,255,0.045);
      backdrop-filter: blur(18px);
      box-shadow: 0 30px 90px rgba(0,0,0,0.45);
      padding: 34px;
      position: relative;
      overflow: hidden;
    }

    .glow {
      position: absolute;
      width: 420px;
      height: 420px;
      border-radius: 50%;
      background: rgba(34, 211, 238, 0.16);
      filter: blur(70px);
      right: -140px;
      top: -120px;
      pointer-events: none;
    }

    header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      position: relative;
      z-index: 2;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 800;
      letter-spacing: -0.03em;
      font-size: 22px;
    }

    .logo {
      width: 44px;
      height: 44px;
      border-radius: 14px;
      border: 1px solid rgba(255,255,255,0.2);
      display: grid;
      place-items: center;
      background: rgba(255,255,255,0.08);
      font-weight: 900;
    }

    nav {
      display: flex;
      gap: 18px;
      color: rgba(255,255,255,0.68);
      font-size: 14px;
      font-weight: 600;
    }

    main {
      position: relative;
      z-index: 2;
      display: grid;
      grid-template-columns: 1.05fr 0.95fr;
      gap: 44px;
      align-items: center;
      min-height: 560px;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 9px 13px;
      border-radius: 999px;
      background: rgba(34,211,238,0.12);
      border: 1px solid rgba(34,211,238,0.26);
      color: #9ff4ff;
      font-size: 13px;
      font-weight: 700;
      margin-bottom: 22px;
    }

    h1 {
      font-size: clamp(44px, 7vw, 78px);
      line-height: 0.95;
      letter-spacing: -0.07em;
      max-width: 680px;
      margin-bottom: 24px;
    }

    .gradient-text {
      background: linear-gradient(90deg, #ffffff, #8eeeff, #ffffff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    p {
      color: rgba(255,255,255,0.72);
      font-size: 18px;
      line-height: 1.65;
      max-width: 560px;
      margin-bottom: 32px;
    }

    .actions {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      align-items: center;
    }

    .btn {
      border: none;
      cursor: pointer;
      text-decoration: none;
      border-radius: 18px;
      padding: 15px 22px;
      font-size: 15px;
      font-weight: 800;
      transition: transform 0.2s ease, opacity 0.2s ease;
    }

    .btn:hover {
      transform: translateY(-2px);
    }

    .btn-primary {
      color: #03111f;
      background: #ffffff;
    }

    .btn-secondary {
      color: #ffffff;
      background: rgba(255,255,255,0.08);
      border: 1px solid rgba(255,255,255,0.16);
    }

    .phone-card {
      justify-self: center;
      width: min(330px, 100%);
      aspect-ratio: 0.55;
      border-radius: 42px;
      padding: 14px;
      background: linear-gradient(180deg, rgba(255,255,255,0.26), rgba(255,255,255,0.06));
      border: 1px solid rgba(255,255,255,0.18);
      box-shadow: 0 26px 80px rgba(0,0,0,0.42);
    }

    .phone-screen {
      height: 100%;
      border-radius: 32px;
      background: #070b16;
      padding: 24px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      overflow: hidden;
    }

    .app-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 13px;
      color: rgba(255,255,255,0.65);
    }

    .app-logo {
      width: 74px;
      height: 74px;
      border-radius: 24px;
      background: linear-gradient(135deg, #22d3ee, #ffffff);
      display: grid;
      place-items: center;
      color: #071b42;
      font-size: 34px;
      font-weight: 900;
      margin: 36px auto 24px;
    }

    .mock-title {
      text-align: center;
      font-size: 28px;
      font-weight: 900;
      letter-spacing: -0.04em;
      margin-bottom: 10px;
    }

    .mock-subtitle {
      text-align: center;
      font-size: 14px;
      color: rgba(255,255,255,0.58);
      line-height: 1.5;
    }

    .mock-list {
      display: grid;
      gap: 12px;
      margin-top: 28px;
    }

    .mock-item {
      height: 58px;
      border-radius: 18px;
      background: rgba(255,255,255,0.07);
      border: 1px solid rgba(255,255,255,0.08);
    }

    footer {
      position: relative;
      z-index: 2;
      color: rgba(255,255,255,0.45);
      font-size: 13px;
      display: flex;
      justify-content: space-between;
      gap: 14px;
      flex-wrap: wrap;
    }

    @media (max-width: 820px) {
      .page {
        padding: 22px;
        border-radius: 24px;
      }

      nav {
        display: none;
      }

      main {
        grid-template-columns: 1fr;
        gap: 30px;
        padding: 54px 0 34px;
      }

      .phone-card {
        width: min(280px, 100%);
      }

      p {
        font-size: 16px;
      }
    }
  </style>
</head>
<body>
  <section class="page">
    <div class="glow"></div>

    <header>
      <div class="brand">
        <div class="logo">A</div>
        <span>Aentigo</span>
      </div>
      <nav>
        <span>Coming Soon</span>
        <span>iOS</span>
        <span>Android</span>
      </nav>
    </header>

    <main>
      <div>
        <div class="badge">Launching soon</div>
        <h1>Connect with the right opportunity <span class="gradient-text">instantly.</span></h1>
        <p>
          Aentigo is a fast, modern platform for connecting people, services and real-time opportunities — built for speed, trust and simple action.
        </p>
        <div class="actions">
          <a class="btn btn-primary" href="mailto:info@aentigo.com">Contact us</a>
          <a class="btn btn-secondary" href="https://aentigo.app">Visit app domain</a>
        </div>
      </div>

      <div class="phone-card" aria-label="Aentigo app preview">
        <div class="phone-screen">
          <div class="app-top">
            <span>Aentigo</span>
            <span>Now</span>
          </div>

          <div>
            <div class="app-logo">A</div>
            <div class="mock-title">Find faster.</div>
            <div class="mock-subtitle">Real people. Real opportunities. Real-time connection.</div>
            <div class="mock-list">
              <div class="mock-item"></div>
              <div class="mock-item"></div>
              <div class="mock-item"></div>
            </div>
          </div>

          <div class="mock-subtitle">Coming soon on iOS & Android</div>
        </div>
      </div>
    </main>

    <footer>
      <span>© 2026 Aentigo. All rights reserved.</span>
      <span>aentigo.com</span>
    </footer>
  </section>
</body>
</html>
