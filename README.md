<!doctype html>
<html lang="id">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Workshop Media Pembelajaran Interaktif</title>
  <style>
    body {
      box-sizing: border-box;
    }
    
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html, body {
      height: 100%;
      width: 100%;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: #333;
      line-height: 1.6;
      overflow-x: hidden;
    }

    .main-wrapper {
      width: 100%;
      height: 100%;
      overflow-y: auto;
      overflow-x: hidden;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
    }

    /* Header Section */
    .header-section {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 60px 20px;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    }

    .header-content {
      max-width: 800px;
      color: white;
    }

    .header-icon {
      font-size: 80px;
      margin-bottom: 30px;
      animation: float 3s ease-in-out infinite;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-20px); }
    }

    .header-content h1 {
      font-size: 3em;
      font-weight: 800;
      margin-bottom: 20px;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
    }

    .header-content h2 {
      font-size: 1.5em;
      font-weight: 400;
      margin-bottom: 20px;
      opacity: 0.95;
    }

    .header-content p {
      font-size: 1.2em;
      margin-bottom: 40px;
      opacity: 0.9;
    }

    .btn-primary {
      background: white;
      color: #667eea;
      padding: 18px 45px;
      font-size: 1.2em;
      font-weight: 700;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    }

    .btn-primary:hover {
      transform: translateY(-3px);
      box-shadow: 0 15px 35px rgba(0,0,0,0.3);
      background: #f8f9ff;
    }

    /* Content Sections */
    .content-section {
      background: white;
      padding: 80px 20px;
    }

    .section-title {
      text-align: center;
      font-size: 2.5em;
      font-weight: 700;
      color: #667eea;
      margin-bottom: 50px;
    }

    /* Goals Cards */
    .goals-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 30px;
      margin-bottom: 40px;
    }

    .goal-card {
      background: linear-gradient(135deg, #f5f7ff 0%, #e8ebff 100%);
      padding: 30px;
      border-radius: 20px;
      text-align: center;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 5px 15px rgba(102, 126, 234, 0.1);
      position: relative;
      overflow: hidden;
    }

    .goal-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      opacity: 0;
      transition: opacity 0.3s ease;
      z-index: 0;
    }

    .goal-card:hover::before {
      opacity: 0.1;
    }

    .goal-card:hover {
      transform: translateY(-10px) scale(1.03);
      box-shadow: 0 15px 35px rgba(102, 126, 234, 0.3);
    }

    .goal-card-content {
      position: relative;
      z-index: 1;
    }

    .goal-icon {
      font-size: 50px;
      margin-bottom: 20px;
    }

    .goal-card h3 {
      font-size: 1.2em;
      color: #667eea;
      margin-bottom: 15px;
      font-weight: 700;
    }

    .goal-detail {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.3s ease;
      color: #555;
      font-size: 0.95em;
      margin-top: 10px;
    }

    .goal-card:hover .goal-detail {
      max-height: 200px;
    }

    /* Quote Section */
    .quote-section {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      padding: 80px 20px;
      text-align: center;
      color: white;
    }

    .quote-box {
      max-width: 800px;
      margin: 0 auto;
    }

    .quote-text {
      font-size: 2.5em;
      font-weight: 700;
      margin-bottom: 30px;
      line-height: 1.3;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
    }

    .btn-secondary {
      background: white;
      color: #667eea;
      padding: 12px 30px;
      font-size: 1.1em;
      font-weight: 600;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .btn-secondary:hover {
      transform: scale(1.05);
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
    }

    .quote-explanation {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.4s ease;
      margin-top: 30px;
      background: rgba(255,255,255,0.15);
      border-radius: 15px;
      padding: 0 30px;
      backdrop-filter: blur(10px);
    }

    .quote-explanation.active {
      max-height: 500px;
      padding: 30px;
    }

    .quote-explanation p {
      font-size: 1.1em;
      line-height: 1.8;
      margin-bottom: 15px;
    }

    /* Stepper Section */
    .stepper-section {
      background: #f8f9ff;
      padding: 80px 20px;
    }

    .stepper {
      display: flex;
      justify-content: space-between;
      max-width: 1000px;
      margin: 0 auto 50px;
      position: relative;
    }

    .stepper::before {
      content: '';
      position: absolute;
      top: 40px;
      left: 10%;
      width: 80%;
      height: 4px;
      background: #e0e0e0;
      z-index: 0;
    }

    .step {
      flex: 1;
      text-align: center;
      position: relative;
      z-index: 1;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .step-number {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      background: white;
      border: 4px solid #e0e0e0;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 20px;
      font-size: 2em;
      font-weight: 700;
      color: #999;
      transition: all 0.3s ease;
    }

    .step.active .step-number {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      border-color: #667eea;
      color: white;
      transform: scale(1.1);
    }

    .step:hover .step-number {
      transform: scale(1.05);
      border-color: #667eea;
    }

    .step-title {
      font-size: 1.1em;
      font-weight: 600;
      color: #333;
      margin-bottom: 10px;
    }

    .step-content {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.4s ease;
      background: white;
      border-radius: 15px;
      margin-top: 20px;
      padding: 0 20px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    }

    .step.active .step-content {
      max-height: 300px;
      padding: 25px;
    }

    .step-description {
      color: #555;
      font-size: 1em;
      line-height: 1.7;
    }

    .btn-continue {
      display: block;
      margin: 50px auto 0;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
      padding: 15px 40px;
      font-size: 1.1em;
      font-weight: 600;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .btn-continue:hover {
      transform: translateY(-3px);
      box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
    }

    /* Praktikum Section */
    .praktikum-section {
      background: white;
      padding: 80px 20px;
    }

    .accordion {
      max-width: 900px;
      margin: 0 auto;
    }

    .accordion-item {
      background: white;
      border-radius: 15px;
      margin-bottom: 20px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.1);
      overflow: hidden;
      transition: all 0.3s ease;
    }

    .accordion-item:hover {
      box-shadow: 0 8px 25px rgba(102, 126, 234, 0.2);
    }

    .accordion-header {
      padding: 25px 30px;
      background: linear-gradient(135deg, #f5f7ff 0%, #e8ebff 100%);
      cursor: pointer;
      display: flex;
      justify-content: space-between;
      align-items: center;
      transition: all 0.3s ease;
    }

    .accordion-header:hover {
      background: linear-gradient(135deg, #e8ebff 0%, #dde3ff 100%);
    }

    .accordion-header.active {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
    }

    .accordion-title {
      font-size: 1.3em;
      font-weight: 700;
      display: flex;
      align-items: center;
      gap: 15px;
    }

    .accordion-icon {
      font-size: 1.8em;
    }

    .accordion-arrow {
      font-size: 1.5em;
      transition: transform 0.3s ease;
    }

    .accordion-header.active .accordion-arrow {
      transform: rotate(180deg);
    }

    .accordion-content {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.4s ease;
      padding: 0 30px;
    }

    .accordion-content.active {
      max-height: 2000px;
      padding: 30px;
    }

    .accordion-text {
      color: #555;
      font-size: 1.05em;
      line-height: 1.8;
      margin-bottom: 20px;
    }

    .example-list {
      list-style: none;
      margin: 20px 0;
    }

    .example-list li {
      padding: 12px 20px;
      background: #f5f7ff;
      margin-bottom: 10px;
      border-radius: 10px;
      border-left: 4px solid #667eea;
      font-weight: 600;
      color: #333;
    }

    .code-box {
      background: #2d3748;
      color: #68d391;
      padding: 20px;
      border-radius: 10px;
      font-family: 'Courier New', monospace;
      font-size: 0.95em;
      line-height: 1.6;
      margin: 20px 0;
      overflow-x: auto;
    }

    .tips-box {
      background: #fff9e6;
      border-left: 5px solid #ffd700;
      padding: 20px;
      border-radius: 10px;
      margin: 20px 0;
      display: flex;
      gap: 15px;
      align-items: flex-start;
    }

    .tips-icon {
      font-size: 2em;
      color: #ffd700;
    }

    .tips-text {
      flex: 1;
      color: #666;
      line-height: 1.7;
    }

    .two-columns {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px;
      margin-top: 20px;
    }

    .column-box {
      background: #f5f7ff;
      padding: 25px;
      border-radius: 15px;
      border: 2px solid #e8ebff;
    }

    .column-box h4 {
      color: #667eea;
      font-size: 1.2em;
      margin-bottom: 15px;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .column-box ul {
      list-style: none;
    }

    .column-box ul li {
      padding: 8px 0;
      color: #555;
      border-bottom: 1px solid #e8ebff;
    }

    .column-box ul li:last-child {
      border-bottom: none;
    }

    .column-box ul li::before {
      content: '���� ';
      color: #667eea;
      font-weight: 700;
      margin-right: 8px;
    }

    .prompt-examples {
      margin: 20px 0;
    }

    .prompt-btn {
      background: #667eea;
      color: white;
      padding: 10px 20px;
      margin: 5px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 0.95em;
      transition: all 0.3s ease;
    }

    .prompt-btn:hover {
      background: #764ba2;
      transform: translateY(-2px);
    }

    .prompt-detail {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.3s ease;
      background: #f5f7ff;
      border-radius: 10px;
      margin-top: 10px;
      padding: 0 20px;
    }

    .prompt-detail.active {
      max-height: 500px;
      padding: 20px;
      margin-top: 15px;
    }

    /* Tips & Checklist Section */
    .tips-section {
      background: #f8f9ff;
      padding: 80px 20px;
    }

    .checklist-container {
      max-width: 800px;
      margin: 0 auto;
      background: white;
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(102, 126, 234, 0.15);
    }

    .checklist-intro {
      text-align: center;
      margin-bottom: 40px;
      font-size: 1.15em;
      color: #555;
    }

    .checklist-items {
      margin-bottom: 30px;
    }

    .checklist-item {
      display: flex;
      align-items: flex-start;
      gap: 15px;
      padding: 20px;
      margin-bottom: 15px;
      background: #f5f7ff;
      border-radius: 12px;
      cursor: pointer;
      transition: all 0.3s ease;
      border: 2px solid transparent;
    }

    .checklist-item:hover {
      background: #e8ebff;
      transform: translateX(5px);
      border-color: #667eea;
    }

    .checkbox {
      width: 24px;
      height: 24px;
      min-width: 24px;
      cursor: pointer;
      accent-color: #667eea;
      margin-top: 2px;
    }

    .checklist-item label {
      cursor: pointer;
      font-size: 1.05em;
      color: #333;
      line-height: 1.6;
      flex: 1;
    }

    .success-message {
      text-align: center;
      padding: 40px;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      border-radius: 20px;
      color: white;
      opacity: 0;
      max-height: 0;
      overflow: hidden;
      transition: all 0.5s ease;
    }

    .success-message.show {
      opacity: 1;
      max-height: 300px;
      padding: 40px;
    }

    .success-icon {
      font-size: 80px;
      margin-bottom: 20px;
      animation: bounce 0.8s ease;
    }

    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-20px); }
    }

    .success-message h3 {
      font-size: 2em;
      margin-bottom: 15px;
    }

    .success-message p {
      font-size: 1.3em;
    }

    /* Media Examples Section */
    .media-examples-section {
      background: white;
      padding: 80px 20px;
    }

    .media-cards-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
    }

    .media-card {
      background: linear-gradient(135deg, #f5f7ff 0%, #ffffff 100%);
      padding: 35px;
      border-radius: 20px;
      box-shadow: 0 8px 20px rgba(102, 126, 234, 0.12);
      transition: all 0.3s ease;
      border: 2px solid #e8ebff;
    }

    .media-card:hover {
      transform: translateY(-8px);
      box-shadow: 0 15px 35px rgba(102, 126, 234, 0.25);
      border-color: #667eea;
    }

    .media-card-icon {
      font-size: 60px;
      text-align: center;
      margin-bottom: 20px;
    }

    .media-card h3 {
      text-align: center;
      color: #667eea;
      font-size: 1.6em;
      margin-bottom: 20px;
      font-weight: 700;
    }

    .media-examples {
      color: #555;
      line-height: 1.9;
      margin-bottom: 25px;
      font-size: 1.02em;
    }

    .idea-btn {
      width: 100%;
      background: #667eea;
      color: white;
      padding: 12px 20px;
      border: none;
      border-radius: 10px;
      font-size: 1em;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .idea-btn:hover {
      background: #764ba2;
      transform: scale(1.02);
    }

    .idea-box {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.4s ease;
      background: #fff9e6;
      border-radius: 10px;
      margin-top: 0;
      padding: 0 15px;
      color: #555;
      line-height: 1.7;
      font-size: 0.95em;
      border-left: 4px solid #ffd700;
    }

    .idea-box.show {
      max-height: 400px;
      padding: 20px 15px;
      margin-top: 15px;
    }

    /* Closing Section */
    .closing-section {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      padding: 80px 20px;
      color: white;
    }

    .summary-box {
      max-width: 800px;
      margin: 0 auto 50px;
      background: white;
      color: #333;
      padding: 50px;
      border-radius: 25px;
      box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
    }

    .summary-icon {
      font-size: 70px;
      text-align: center;
      margin-bottom: 25px;
    }

    .summary-box h3 {
      text-align: center;
      color: #667eea;
      font-size: 2em;
      margin-bottom: 35px;
      font-weight: 700;
    }

    .summary-list {
      list-style: none;
      margin: 0;
      padding: 0;
    }

    .summary-list li {
      padding: 18px 25px;
      background: #f5f7ff;
      margin-bottom: 15px;
      border-radius: 12px;
      font-size: 1.15em;
      line-height: 1.7;
      border-left: 5px solid #667eea;
      color: #333;
    }

    .final-motivation {
      max-width: 900px;
      margin: 0 auto;
      text-align: center;
      padding: 40px;
    }

    .motivation-text {
      font-size: 1.5em;
      font-style: italic;
      line-height: 1.8;
      margin-bottom: 20px;
      text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.2);
    }

    .author {
      font-size: 1.2em;
      font-weight: 600;
      opacity: 0.9;
    }

    @media (max-width: 768px) {
      .header-content h1 {
        font-size: 2em;
      }

      .header-content h2 {
        font-size: 1.2em;
      }

      .quote-text {
        font-size: 1.8em;
      }

      .stepper {
        flex-direction: column;
        gap: 30px;
      }

      .stepper::before {
        display: none;
      }

      .two-columns {
        grid-template-columns: 1fr;
      }

      .goals-grid {
        grid-template-columns: 1fr;
      }

      .media-cards-grid {
        grid-template-columns: 1fr;
      }

      .checklist-container {
        padding: 25px;
      }

      .summary-box {
        padding: 30px 25px;
      }

      .motivation-text {
        font-size: 1.2em;
      }
    }
  </style>
  <script src="/_sdk/element_sdk.js"></script>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
  <script src="https://cdn.tailwindcss.com" type="text/javascript"></script>
 </head>
 <body>
  <div class="main-wrapper"><!-- Header Section -->
   <section class="header-section" id="header">
    <div class="header-content">
     <div class="header-icon">
      💻🎓✨
     </div>
     <h1 id="workshopTitle">Workshop Media Pembelajaran Interaktif</h1>
     <h2 id="workshopSubtitle">Menggunakan ChatGPT + Canva AI Code untuk Semua Guru Mapel</h2>
     <p id="workshopTagline">Praktikum 100% langsung bisa, tanpa harus jago coding.</p><button class="btn-primary" onclick="scrollToSection('goals')">Mulai Belajar</button>
    </div>
   </section><!-- Goals Section -->
   <section class="content-section" id="goals">
    <div class="container">
     <h2 class="section-title">Tujuan Workshop</h2>
     <div class="goals-grid">
      <div class="goal-card">
       <div class="goal-card-content">
        <div class="goal-icon">
         ⚡
        </div>
        <h3>Media dalam Hitungan Menit</h3>
        <div class="goal-detail">
         Membuat media pembelajaran interaktif dalam hitungan menit, tanpa perlu belajar coding bertahun-tahun.
        </div>
       </div>
      </div>
      <div class="goal-card">
       <div class="goal-card-content">
        <div class="goal-icon">
         💬
        </div>
        <h3>Prompt yang Rapi &amp; Detail</h3>
        <div class="goal-detail">
         Memanfaatkan ChatGPT untuk menyusun prompt yang rapi dan detail sesuai kebutuhan pembelajaran Anda.
        </div>
       </div>
      </div>
      <div class="goal-card">
       <div class="goal-card-content">
        <div class="goal-icon">
         🎨
        </div>
        <h3>Visual &amp; Interaktif</h3>
        <div class="goal-detail">
         Menggunakan Canva AI Code untuk membangun media visual dan interaktif yang menarik bagi siswa.
        </div>
       </div>
      </div>
      <div class="goal-card">
       <div class="goal-card-content">
        <div class="goal-icon">
         🚀
        </div>
        <h3>Langsung Praktik</h3>
        <div class="goal-detail">
         Workshop berbasis praktik: guru langsung mencoba dan menghasilkan media pembelajaran sendiri.
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Quote Section -->
   <section class="quote-section" id="quote">
    <div class="container">
     <div class="quote-box">
      <p class="quote-text" id="quoteText">"Guru tidak harus jago coding, cukup jago prompting."</p><button class="btn-secondary" onclick="toggleQuoteExplanation()">Kenapa?</button>
      <div class="quote-explanation" id="quoteExplanation">
       <p><strong>AI sebagai Asisten Guru</strong></p>
       <p>AI seperti ChatGPT dan Canva AI Code adalah asisten pintar yang membantu Anda mewujudkan ide pembelajaran menjadi media interaktif. Anda tidak perlu menulis kode, cukup jelaskan apa yang Anda butuhkan dengan bahasa yang jelas.</p>
       <p><strong>Bukan Pengganti Guru</strong></p>
       <p>AI tidak menggantikan peran guru. Justru, AI memberdayakan guru untuk fokus pada pedagogi dan kreativitas, sementara tugas teknis seperti coding ditangani oleh AI.</p>
       <p><strong>Manfaat untuk Semua Mapel</strong></p>
       <p>Dari Matematika, IPA, Bahasa, Sejarah, hingga Seni - semua guru dapat menciptakan media pembelajaran yang disesuaikan dengan karakteristik mata pelajaran mereka.</p>
      </div>
     </div>
    </div>
   </section><!-- Stepper Section -->
   <section class="stepper-section" id="stepper">
    <div class="container">
     <h2 class="section-title">Alur Besar Workshop</h2>
     <div class="stepper">
      <div class="step" onclick="activateStep(0)">
       <div class="step-number">
        1
       </div>
       <div class="step-title">
        Jelaskan ke ChatGPT
       </div>
       <div class="step-content">
        <p class="step-description">Guru menyampaikan mapel, kelas, topik, tujuan pembelajaran, dan bentuk media yang diinginkan (quiz, kartu, simulasi, dll).</p>
       </div>
      </div>
      <div class="step" onclick="activateStep(1)">
       <div class="step-number">
        2
       </div>
       <div class="step-title">
        ChatGPT Buat Prompt
       </div>
       <div class="step-content">
        <p class="step-description">Guru melakukan refine, expand, transform, dan localize sampai prompt siap dan sesuai dengan kebutuhan pembelajaran.</p>
       </div>
      </div>
      <div class="step" onclick="activateStep(2)">
       <div class="step-number">
        3
       </div>
       <div class="step-title">
        Tempel ke Canva
       </div>
       <div class="step-content">
        <p class="step-description">Guru copy-paste prompt ke Canva AI Code, lalu Canva menghasilkan media interaktif secara otomatis.</p>
       </div>
      </div>
      <div class="step" onclick="activateStep(3)">
       <div class="step-number">
        4
       </div>
       <div class="step-title">
        Edit &amp; Sesuaikan
       </div>
       <div class="step-content">
        <p class="step-description">Guru menyesuaikan warna, soal, tombol, feedback, dan skor sesuai dengan identitas sekolah dan kebutuhan siswa.</p>
       </div>
      </div>
     </div><button class="btn-continue" onclick="scrollToSection('praktikum')">Lanjut ke Praktikum</button>
    </div>
   </section><!-- Praktikum Section -->
   <section class="praktikum-section" id="praktikum">
    <div class="container">
     <h2 class="section-title">Praktikum Inti: Langkah Demi Langkah</h2>
     <div class="accordion"><!-- Panel 1 -->
      <div class="accordion-item">
       <div class="accordion-header" onclick="toggleAccordion(0)">
        <div class="accordion-title"><span class="accordion-icon">👨‍🏫</span> <span>Langkah 1 – Menjelaskan Materi ke ChatGPT</span>
        </div><span class="accordion-arrow">▼</span>
       </div>
       <div class="accordion-content">
        <p class="accordion-text"><strong>Pada langkah ini, Anda akan menjelaskan kebutuhan pembelajaran kepada ChatGPT:</strong></p>
        <ul class="example-list">
         <li>📚 Tentukan mata pelajaran dan kelas (contoh: Matematika Kelas 7)</li>
         <li>📖 Tentukan topik pembelajaran (contoh: Pecahan dan Desimal)</li>
         <li>🎯 Tentukan Fase atau Kelas Siswa</li>
         <li>🎓 Jelaskan tujuan pembelajaran dan level kemampuan siswa</li>
        </ul>
        <p class="accordion-text"><strong>Contoh prompt awal:</strong></p>
        <div class="code-box">
         "Saya adalah seorang guru (isi mapel).
Tolong buatkan saya materi pembelajaran yang lengkap, terstruktur, dan mendalam mengenai topik (isi topik materi) untuk peserta didik (isi fase/kelas).

Materi harus:

1. Memenuhi tujuan pembelajaran, yaitu:
(isi tujuan pembelajaran yang diinginkan guru)
2. Disusun berdasarkan prinsip pembelajaran:
Meaningful Learning (bermakna)
Mindful Learning (sadar proses)
Joyful Learning (menyenangkan)
3. Disajikan secara:
jelas
runtut
mudah dipahami
ramah untuk siswa
kaya contoh praktis
relevan dengan kehidupan nyata
4. Materi harus mencakup:
Konsep utama
Penjelasan detail
Contoh nyata
Aktivitas atau latihan siswa
Studi kasus
Aplikasi konsep pada konteks kehidupan atau proyek
Penilaian (opsional, bila diperlukan guru)
5. Gunakan format output yang rapi dan terstruktur:
heading
subheading
poin-poin
tabel apabila perlu
contoh aplikatif
Berikan hasil berupa materi yang lengkap, kaya penjelasan, dan siap dipakai untuk mengajar.

"
        </div>
       </div>
      </div><!-- Panel 2 -->
      <div class="accordion-item">
       <div class="accordion-header" onclick="toggleAccordion(1)">
        <div class="accordion-title"><span class="accordion-icon">🔧</span> <span>Langkah 2 – Mendetailkan &amp; Memperbaiki Prompt</span>
        </div><span class="accordion-arrow">▼</span>
       </div>
       <div class="accordion-content">
        <p class="accordion-text"><strong>Teknik memperbaiki prompt:</strong></p>
        <ul class="example-list">
         <li><strong>Refine</strong> → Sesuaikan dengan kemampuan siswa (mudah/sedang/sulit)</li>
         <li><strong>Expand</strong> → Tambahkan penjelasan konsep atau sesuai dengan kebutuhan guru</li>
         <li><strong>Transform</strong> → perbaiki kuisnya </li>
         <li><strong>Localize</strong> → Sesuaikan konteks atau studi kasus(nama, contoh, situasi lokal)</li>
        </ul>
        <p class="accordion-text"><strong>Klik contoh perintah untuk melihat detail:</strong></p>
        <div class="prompt-examples"><button class="prompt-btn" onclick="togglePromptDetail(0)">Refine - Tingkat Kesulitan</button> <button class="prompt-btn" onclick="togglePromptDetail(1)">Expand - Tambah Penjelasan</button> <button class="prompt-btn" onclick="togglePromptDetail(2)">Transform - Ubah Format</button> <button class="prompt-btn" onclick="togglePromptDetail(3)">Localize - Konteks Indonesia</button>
        </div>
        <div class="prompt-detail" id="promptDetail0"><strong>Contoh Refine:</strong><br>
          "Perbaiki, buat materi yang lebih menarik, cocok dengan konteks siswa, lebih dalamkan lagi"
        </div>
        <div class="prompt-detail" id="promptDetail1"><strong>Contoh Expand:</strong><br>
          "sesusikan dengan kondisi siswa atau keseharian siswa"
        </div>
        <div class="prompt-detail" id="promptDetail2"><strong>Contoh Transform:</strong><br>
          "Tolong kuisnya akmu buat 5 soal saja dan uat leih mudah"
        </div>
        <div class="prompt-detail" id="promptDetail3"><strong>Contoh Localize:</strong><br>
          "Gunakan konteks Indonesia seperti 'membagi kue lapis' atau 'menghitung uang receh rupiah' dalam soal cerita."
        </div>
       </div>
      </div><!-- Panel 3 -->
      <div class="accordion-item">
       <div class="accordion-header" onclick="toggleAccordion(2)">
        <div class="accordion-title"><span class="accordion-icon">📋</span> <span>Langkah 3 – Copy Prompt ke Canva AI Code</span>
        </div><span class="accordion-arrow">▼</span>
       </div>
       <div class="accordion-content">
        <p class="accordion-text"><strong>Langkah praktis:</strong></p>
        <ul class="example-list">
         <li>🌐 Buka Canva dan pilih menu AI Code</li>
         <li>📝 Paste prompt yang sudah diperbaiki dari ChatGPT</li>
         <li>⚡ Klik tombol Generate dan tunggu beberapa detik</li>
         <li>🎮 Uji interaktivitas media yang dihasilkan (klik tombol, jawab soal, dll)</li>
        </ul>
        <div class="tips-box">
         <div class="tips-icon">
          💡
         </div>
         <div class="tips-text"><strong>Tips Penting:</strong> Jika hasil tidak sesuai harapan, kembali ke ChatGPT dan perbaiki prompt Anda. Jelaskan bagian mana yang kurang tepat, lalu generate ulang di Canva. Proses ini normal dan bagian dari pembelajaran!
         </div>
        </div>
       </div>
      </div><!-- Panel 4 -->
      <div class="accordion-item">
       <div class="accordion-header" onclick="toggleAccordion(3)">
        <div class="accordion-title"><span class="accordion-icon">🎨</span> <span>Langkah 4 – Mengedit Visual &amp; Interaktivitas</span>
        </div><span class="accordion-arrow">▼</span>
       </div>
       <div class="accordion-content">
        <p class="accordion-text"><strong>Sekarang saatnya personalisasi media Anda:</strong></p>
        <div class="two-columns">
         <div class="column-box">
          <h4>🎨 Edit Visual</h4>
          <ul>
           <li>Ganti warna sesuai identitas sekolah</li>
           <li>Tambahkan logo sekolah</li>
           <li>Pilih gambar atau icon yang sesuai</li>
           <li>Atur layout dan ukuran elemen</li>
           <li>Sesuaikan font dan tipografi</li>
          </ul>
         </div>
         <div class="column-box">
          <h4>⚙����� Edit Interaktivitas</h4>
          <ul>
           <li>Ganti soal atau konten</li>
           <li>Edit feedback benar/salah</li>
           <li>Atur sistem scoring/penilaian</li>
           <li>Ubah teks pada tombol</li>
           <li>Tambah petunjuk penggunaan</li>
          </ul>
         </div>
        </div>
        <div class="tips-box" style="margin-top: 25px;">
         <div class="tips-icon">
          🎯
         </div>
         <div class="tips-text"><strong>Pro Tip:</strong> Simpan versi master media Anda, lalu duplikasi untuk membuat variasi untuk kelas atau topik yang berbeda. Ini akan menghemat waktu Anda di masa mendatang!
         </div>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Tips & Checklist Section -->
   <section class="tips-section" id="tips">
    <div class="container">
     <h2 class="section-title">Checklist Keberhasilan Menggunakan ChatGPT + Canva AI Code</h2>
     <div class="checklist-container">
      <div class="checklist-intro">
       <p>✅ Centang setiap item berikut untuk memastikan Anda siap menciptakan media pembelajaran interaktif!</p>
      </div>
      <div class="checklist-items">
       <div class="checklist-item" onclick="toggleCheckbox(0)"><input type="checkbox" id="check0" class="checkbox"> <label for="check0">Saya sudah menyusun prompt dengan 4 bagian: tujuan, materi, bentuk media, dan output.</label>
       </div>
       <div class="checklist-item" onclick="toggleCheckbox(1)"><input type="checkbox" id="check1" class="checkbox"> <label for="check1">Saya mulai dari media yang sederhana (quiz 5 soal atau kartu).</label>
       </div>
       <div class="checklist-item" onclick="toggleCheckbox(2)"><input type="checkbox" id="check2" class="checkbox"> <label for="check2">Saya menyimpan prompt yang berhasil ke dalam 'prompt bank' pribadi.</label>
       </div>
       <div class="checklist-item" onclick="toggleCheckbox(3)"><input type="checkbox" id="check3" class="checkbox"> <label for="check3">Saya paham bahwa semakin lengkap input, semakin bagus output.</label>
       </div>
       <div class="checklist-item" onclick="toggleCheckbox(4)"><input type="checkbox" id="check4" class="checkbox"> <label for="check4">Saya menerapkan model 'fasilitator demo 2 menit, guru praktik 5 menit' di kelas pelatihan.</label>
       </div>
      </div>
      <div class="success-message" id="successMessage">
       <div class="success-icon">
        🎉
       </div>
       <h3>Selamat!</h3>
       <p>Anda siap menjadi guru kreator media interaktif berbasis AI!</p>
      </div>
     </div>
    </div>
   </section><!-- Contoh Media per Mapel Section -->
   <section class="media-examples-section" id="examples">
    <div class="container">
     <h2 class="section-title">Inspirasi Media per Mata Pelajaran</h2>
     <p style="text-align: center; color: #666; margin-bottom: 40px; font-size: 1.1em;">Lihat contoh media yang bisa Anda buat untuk berbagai mata pelajaran</p>
     <div class="media-cards-grid">
      <div class="media-card">
       <div class="media-card-icon">
        🔬
       </div>
       <h3>IPA</h3>
       <p class="media-examples">• Quiz sistem pencernaan<br>
         • Simulasi rantai makanan<br>
         • Diagram organ tubuh interaktif</p><button class="idea-btn" onclick="toggleIdea(0)">💡 Ide Prompt</button>
       <div class="idea-box" id="idea0">
        "Buat quiz interaktif tentang sistem pencernaan manusia untuk kelas 8, dengan 10 soal pilihan ganda, gambar organ pencernaan, dan penjelasan singkat fungsi setiap organ."
       </div>
      </div>
      <div class="media-card">
       <div class="media-card-icon">
        📚
       </div>
       <h3>Bahasa Indonesia</h3>
       <p class="media-examples">• Kartu kosakata interaktif<br>
         • Latihan teks deskripsi<br>
         • Permainan menyusun kalimat</p><button class="idea-btn" onclick="toggleIdea(1)">💡 Ide Prompt</button>
       <div class="idea-box" id="idea1">
        "Buat kartu flashcard interaktif untuk kosakata bahasa Indonesia kelas 5, dengan 20 kata sulit beserta arti, contoh kalimat, dan gambar ilustrasi."
       </div>
      </div>
      <div class="media-card">
       <div class="media-card-icon">
        🔢
       </div>
       <h3>Matematika</h3>
       <p class="media-examples">• Latihan soal langkah demi langkah<br>
         • Simulasi pecahan visual<br>
         • Kalkulator interaktif</p><button class="idea-btn" onclick="toggleIdea(2)">💡 Ide Prompt</button>
       <div class="idea-box" id="idea2">
        "Buat latihan soal matematika tentang perkalian pecahan untuk kelas 6, dengan 8 soal yang menampilkan langkah penyelesaian secara bertahap ketika siswa mengklik tombol 'Lihat Cara'."
       </div>
      </div>
      <div class="media-card">
       <div class="media-card-icon">
        🏛️
       </div>
       <h3>Sejarah</h3>
       <p class="media-examples">• Timeline peristiwa bersejarah<br>
         • Peta interaktif kerajaan Nusantara<br>
         • Quiz tokoh dan peristiwa</p><button class="idea-btn" onclick="toggleIdea(3)">💡 Ide Prompt</button>
       <div class="idea-box" id="idea3">
        "Buat timeline interaktif tentang peristiwa penting kemerdekaan Indonesia dari 1942-1949, dengan foto tokoh, deskripsi singkat tiap peristiwa, dan dapat diklik untuk detail lengkap."
       </div>
      </div>
      <div class="media-card">
       <div class="media-card-icon">
        ⚖️
       </div>
       <h3>PPKn</h3>
       <p class="media-examples">• Studi kasus nilai Pancasila<br>
         • Simulasi musyawarah<br>
         • Quiz hak dan kewajiban warga</p><button class="idea-btn" onclick="toggleIdea(4)">💡 Ide Prompt</button>
       <div class="idea-box" id="idea4">
        "Buat studi kasus interaktif tentang penerapan nilai-nilai Pancasila dalam kehidupan sehari-hari untuk kelas 9, dengan 5 skenario dan pilihan tindakan yang menunjukkan sila mana yang diterapkan."
       </div>
      </div>
      <div class="media-card">
       <div class="media-card-icon">
        🎨
       </div>
       <h3>Seni &amp; Budaya</h3>
       <p class="media-examples">• Galeri karya seni interaktif<br>
         • Quiz alat musik tradisional<br>
         • Pengenalan tarian daerah</p><button class="idea-btn" onclick="toggleIdea(5)">💡 Ide Prompt</button>
       <div class="idea-box" id="idea5">
        "Buat quiz interaktif tentang alat musik tradisional Indonesia untuk kelas 7, dengan gambar alat musik, suara (deskripsi), daerah asal, dan cara memainkannya."
       </div>
      </div>
     </div>
    </div>
   </section><!-- Penutup Section -->
   <section class="closing-section" id="closing">
    <div class="container">
     <h2 class="section-title">Ringkasan &amp; Penutup</h2>
     <div class="summary-box">
      <div class="summary-icon">
       🎯
      </div>
      <h3>Poin Penting yang Perlu Diingat</h3>
      <ul class="summary-list">
       <li>✨ Guru bisa membuat media interaktif tanpa coding rumit</li>
       <li>🤖 ChatGPT membantu menyusun dan memperbaiki prompt</li>
       <li>🎨 Canva AI Code menerjemahkan prompt menjadi media visual</li>
       <li>🔑 Kunci utama: coba, ulangi, simpan prompt yang berhasil</li>
       <li>💪 Praktek lebih penting daripada teori - langsung coba sekarang!</li>
      </ul><button class="btn-primary" onclick="scrollToSection('praktikum')" style="margin-top: 30px;"> Mulai Buat Prompt Versi Anda </button>
     </div>
     <div class="final-motivation">
      <p class="motivation-text">"Setiap guru adalah kreator. AI hanya alat bantu. Kreativitas dan dedikasi Anda terhadap pembelajaran siswa yang membuat media ini bermakna."</p>
      <p class="author">— Tim Fasilitator Workshop</p>
     </div>
    </div>
   </section>
  </div>
  <script>
    const defaultConfig = {
      workshop_title: "Workshop Media Pembelajaran Interaktif",
      workshop_subtitle: "Menggunakan ChatGPT + Canva AI Code untuk Semua Guru Mapel",
      workshop_tagline: "Praktikum 100% langsung bisa, tanpa harus jago coding.",
      quote_text: "Guru tidak harus jago coding, cukup jago prompting.",
      background_color: "#667eea",
      card_background: "#f5f7ff",
      text_color: "#333333",
      primary_action: "#667eea",
      accent_color: "#764ba2"
    };

    let currentStep = -1;
    let currentAccordion = -1;

    function scrollToSection(sectionId) {
      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
    }

    function toggleQuoteExplanation() {
      const explanation = document.getElementById('quoteExplanation');
      explanation.classList.toggle('active');
    }

    function activateStep(stepIndex) {
      const steps = document.querySelectorAll('.step');
      
      if (currentStep === stepIndex) {
        steps[stepIndex].classList.remove('active');
        currentStep = -1;
      } else {
        steps.forEach((step, index) => {
          if (index === stepIndex) {
            step.classList.add('active');
          } else {
            step.classList.remove('active');
          }
        });
        currentStep = stepIndex;
      }
    }

    function toggleAccordion(index) {
      const section = document.getElementById('praktikum');
      const headers = section.querySelectorAll('.accordion-header');
      const contents = section.querySelectorAll('.accordion-content');
      
      if (currentAccordion === index) {
        headers[index].classList.remove('active');
        contents[index].classList.remove('active');
        currentAccordion = -1;
      } else {
        headers.forEach((header, i) => {
          if (i === index) {
            header.classList.add('active');
            contents[i].classList.add('active');
          } else {
            header.classList.remove('active');
            contents[i].classList.remove('active');
          }
        });
        currentAccordion = index;
      }
    }

    let activePromptDetail = -1;

    function togglePromptDetail(index) {
      const detail = document.getElementById(`promptDetail${index}`);
      
      if (activePromptDetail === index) {
        detail.classList.remove('active');
        activePromptDetail = -1;
      } else {
        // Close all other details
        for (let i = 0; i < 4; i++) {
          document.getElementById(`promptDetail${i}`).classList.remove('active');
        }
        detail.classList.add('active');
        activePromptDetail = index;
      }
    }

    // Checklist functionality
    const checkboxStates = [false, false, false, false, false];

    function toggleCheckbox(index) {
      const checkbox = document.getElementById(`check${index}`);
      checkboxStates[index] = !checkboxStates[index];
      checkbox.checked = checkboxStates[index];
      checkAllCompleted();
    }

    function checkAllCompleted() {
      const allChecked = checkboxStates.every(state => state === true);
      const successMessage = document.getElementById('successMessage');
      
      if (allChecked) {
        successMessage.classList.add('show');
      } else {
        successMessage.classList.remove('show');
      }
    }

    // Media card idea toggle
    let activeIdea = -1;

    function toggleIdea(index) {
      const ideaBox = document.getElementById(`idea${index}`);
      
      if (activeIdea === index) {
        ideaBox.classList.remove('show');
        activeIdea = -1;
      } else {
        // Close all other ideas
        for (let i = 0; i < 6; i++) {
          const box = document.getElementById(`idea${i}`);
          if (box) {
            box.classList.remove('show');
          }
        }
        ideaBox.classList.add('show');
        activeIdea = index;
      }
    }

    async function onConfigChange(config) {
      const workshopTitle = document.getElementById('workshopTitle');
      const workshopSubtitle = document.getElementById('workshopSubtitle');
      const workshopTagline = document.getElementById('workshopTagline');
      const quoteText = document.getElementById('quoteText');

      if (workshopTitle) {
        workshopTitle.textContent = config.workshop_title || defaultConfig.workshop_title;
      }
      if (workshopSubtitle) {
        workshopSubtitle.textContent = config.workshop_subtitle || defaultConfig.workshop_subtitle;
      }
      if (workshopTagline) {
        workshopTagline.textContent = config.workshop_tagline || defaultConfig.workshop_tagline;
      }
      if (quoteText) {
        quoteText.textContent = `"${config.quote_text || defaultConfig.quote_text}"`;
      }
    }

    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig: defaultConfig,
        onConfigChange: onConfigChange,
        mapToCapabilities: (config) => ({
          recolorables: [
            {
              get: () => config.background_color || defaultConfig.background_color,
              set: (value) => {
                config.background_color = value;
                window.elementSdk.setConfig({ background_color: value });
              }
            },
            {
              get: () => config.card_background || defaultConfig.card_background,
              set: (value) => {
                config.card_background = value;
                window.elementSdk.setConfig({ card_background: value });
              }
            },
            {
              get: () => config.text_color || defaultConfig.text_color,
              set: (value) => {
                config.text_color = value;
                window.elementSdk.setConfig({ text_color: value });
              }
            },
            {
              get: () => config.primary_action || defaultConfig.primary_action,
              set: (value) => {
                config.primary_action = value;
                window.elementSdk.setConfig({ primary_action: value });
              }
            },
            {
              get: () => config.accent_color || defaultConfig.accent_color,
              set: (value) => {
                config.accent_color = value;
                window.elementSdk.setConfig({ accent_color: value });
              }
            }
          ],
          borderables: [],
          fontEditable: undefined,
          fontSizeable: undefined
        }),
        mapToEditPanelValues: (config) => new Map([
          ["workshop_title", config.workshop_title || defaultConfig.workshop_title],
          ["workshop_subtitle", config.workshop_subtitle || defaultConfig.workshop_subtitle],
          ["workshop_tagline", config.workshop_tagline || defaultConfig.workshop_tagline],
          ["quote_text", config.quote_text || defaultConfig.quote_text]
        ])
      });
    }
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9ab280a4e4f3811b',t:'MTc2NTI2MjMzNy4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
