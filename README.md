<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Akordeony</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet" />
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 3px;
    }

    html, body {
      width: 100%;
      font-family: 'Poppins', sans-serif;
      background: transparent;
      color: #ffffff;
      overflow: visible;
      height: auto;
    }

    .container {
      max-width: 670px;
      width: 100%;
      padding: 30px 16px;
      margin: 0 auto;
    }

    .accordion {
      background: rgba(255, 255, 255, 0.25);
      border-radius: 12px;
      padding: 20px;
      margin-bottom: 24px;
      box-shadow: 0 0 10px rgba(0,0,0,0.3);
    }

    .accordion h3 {
      font-size: 19px;
      margin-bottom: 8px;
      font-weight: 600;
      color: #ffffff;
    }

    .accordion p.subtitle {
      font-size: 13px;
      margin-bottom: 12px;
      color: #ffffff;
    }

    .accordion button {
      background: #FF3D00;
      color: #ffffff;
      font-weight: 600;
      border: none;
      padding: 8px 16px;
      cursor: pointer;
      border-radius: 25px;
      font-size: 13px;
    }

    .accordion-content {
      display: none;
      margin-top: 16px;
      font-size: 13px;
      color: #ffffff;
    }

    .accordion-content.open {
      display: block;
    }

    @media screen and (max-width: 800px) {
      .container {
        padding: 30px 12px;
      }

      .accordion {
        padding: 16px;
        margin-bottom: 20px;
      }

      .accordion h3 {
        font-size: 17px;
      }

      .accordion p.subtitle,
      .accordion-content,
      .accordion button {
        font-size: 13px;
      }

      .accordion button {
        padding: 10px 16px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="accordion">
      <h3>Kompleksowa obsługa Social Media</h3>
      <p class="subtitle">Oddajesz mi swoje social media – i śpisz spokojnie</p>
      <button onclick="toggleAccordion(this)">Czytaj dalej</button>
      <div class="accordion-content">
        Od pomysłów po gotowy materiał: copywriting, harmonogram treści, grafiki i dynamiczne video, które przyciągną wzrok i zaangażują odbiorców.
      </div>
    </div>

    <div class="accordion">
      <h3>Strategia komunikacji i audyt social media</h3>
      <p class="subtitle">Przeprowadzę szczegółowy audyt Twojego profilu</p>
      <button onclick="toggleAccordion(this)">Czytaj dalej</button>
      <div class="accordion-content">
        Ocenimy styl, przeanalizujemy działania i zaproponujemy strategię, która poprawi efektywność komunikacji.
      </div>
    </div>

    <div class="accordion">
      <h3>Content Marketing</h3>
      <p class="subtitle">Stworzę całościowy content dla Twojej marki</p>
      <button onclick="toggleAccordion(this)">Czytaj dalej</button>
      <div class="accordion-content">
        Od pomysłów po gotowy materiał: copywriting, harmonogram treści, grafiki i video, które przyciągną wzrok i zaangażują odbiorców.
      </div>
    </div>

    <div class="accordion">
      <h3>Konsultacje i mentoring 1:1</h3>
      <p class="subtitle">Bierzemy na warsztat Twoje social media</p>
      <button onclick="toggleAccordion(this)">Czytaj dalej</button>
      <div class="accordion-content">
        Analizujemy działania, planujemy zmiany, rozwiązujemy konkretne problemy.
      </div>
    </div>
  </div>

  <!-- Toggle logic -->
  <script>
    function toggleAccordion(button) {
      const allContents = document.querySelectorAll('.accordion-content');
      const content = button.nextElementSibling;

      allContents.forEach(el => {
        if (el !== content) el.classList.remove('open');
      });

      content.classList.toggle('open');

      // Notify parent iframe to resize
      if (window.parentIFrame) {
        setTimeout(() => window.parentIFrame.size(), 150);
      }
    }
  </script>

  <!-- Required for iframeResizer -->
  <script src="https://cdn.jsdelivr.net/npm/iframe-resizer/js/iframeResizer.contentWindow.min.js"></script>
</body>
</html>
