<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>我的網站</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
    }

    /* 首頁 Banner 滿版 */
    .home-banner {
      background: url('https://picsum.photos/1920/400?random=1') center/cover no-repeat;
      width: 100%;       /* 滿螢幕寬度 */
      height: 300px;      
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
      font-size: 2.5rem;
      font-weight: bold;
    }

    /* 固定導覽列 */
    nav {
      position: sticky;
      top: 0;
      z-index: 1000;
      background-color: #333;
      width: 100%;       /* 滿螢幕寬度 */
      padding: 10px 20px;
    }

    nav ul {
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: flex-start; /* 導覽列靠左 */
      list-style: none;
    }

    nav ul li {
      margin: 0 20px;
    }

    nav ul li a {
      color: white;
      text-decoration: none;
      font-size: 1.1rem;
    }

    nav ul li a:hover {
      text-decoration: underline;
    }

    /* 區段 Banner 滿版 */
    .section-banner {
      width: 100%;       /* 滿螢幕寬度 */
      height: 300px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 2rem;
      font-weight: bold;
      color: white;
      background-size: cover;
      background-position: center;
    }

    .section1-banner { background-image: url('https://picsum.photos/1920/500?random=2'); }
    .section2-banner { background-image: url('https://picsum.photos/1920/500?random=3'); }
    .section3-banner { background-image: url('https://picsum.photos/1920/500?random=5'); }

    /* 區段內容區塊 */
    .content-wrapper {
      display: flex;
      justify-content: center;
      padding: 80px 0;
      background: #f9f9f9;
    }

    .content-box {
      width: 50%;       /* 灰色方塊寬度 */
      min-height: 200px; /* 高度縮短，保留白色留白 */
      background: #e0e0e0;
      padding: 50px;
      border-radius: 10px;
      text-align: center;
      font-size: 1.2rem;
      line-height: 1.8;
    }
  </style>
</head>
<body>
  <!-- 首頁 Banner -->
  <div class="home-banner" id="home">
    我的網站首頁
  </div>

  <!-- 導覽列 -->
  <nav>
    <ul>
      <li><a href="#home">首頁</a></li>
      <li><a href="#section1">區段1</a></li>
      <li><a href="#section2">區段2</a></li>
      <li><a href="#section3">區段3</a></li>
    </ul>
  </nav>

  <!-- 區段 1 -->
  <div class="section-banner section1-banner" id="section1">區段 1</div>
  <div class="content-wrapper">
    <div class="content-box">
      在未來城市的街道上，無人車與空中運輸系統共存，人們的日常生活被科技與綠色能源完美融合。
    </div>
  </div>

  <!-- 區段 2 -->
  <div class="section-banner section2-banner" id="section2">區段 2</div>
  <div class="content-wrapper">
    <div class="content-box">
      在神秘的森林深處，有一片閃爍著萤火光的湖泊，夜晚的微風帶來花香與自然的低語。
    </div>
  </div>

  <!-- 區段 3 -->
  <div class="section-banner section3-banner" id="section3">區段 3</div>
  <div class="content-wrapper">
    <div class="content-box">
      科學家在太空站進行實驗，探索宇宙的奧秘，同時研究如何讓地球與其他星球的生命共生。
    </div>
  </div>

  <!-- JS 平滑滾動（首頁除外） -->
  <script>
    document.querySelectorAll('nav a').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = this.getAttribute('href');
        if(target === '#home') {
          window.scrollTo(0, 0); // 直接到頁面最上方
        } else {
          document.querySelector(target).scrollIntoView({
            behavior: 'smooth' // 其他區段平滑滾動
          });
        }
      });
    });
  </script>
</body>
</html>
