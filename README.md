<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
    <style>
    :root {
      --bg-color: #ffffff;
      --text-color: #000000;
      --hover-bg: #f0f0f0;
      --highlight-color: #999999;
      --active-bg: #eaeaea;
      --accent-color: rgba(0, 0, 0, 0.05);
    }
    [data-theme="dark"] {
      --bg-color: #111111;
      --text-color: #ffffff;
      --hover-bg: #333333;
      --highlight-color: #777777;
      --active-bg: #222222;
      --accent-color: rgba(255, 255, 255, 0.05);
    }

    body {
      margin: 0;
      font-family: 'Inter', sans-serif;
      background-color: var(--bg-color);
      color: var(--text-color);
      height: 100vh;
      overflow: hidden;
      transition: background-color 0.3s, color 0.3s;
    }
    .top-menu {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 2rem;
      font-size: 0.9rem;
      border-bottom: 1px solid var(--text-color);
    }
    .top-left {
      display: flex;
      align-items: center;
      gap: 1rem;
    }
    .logo-placeholder {
      width: 24px;
      height: 24px;
      background-color: var(--text-color);
      border-radius: 50%;
    }
    .top-menu nav {
      display: flex;
      gap: 1rem;
    }
    .top-menu nav a {
      text-decoration: none;
      color: var(--text-color);
      transition: color 0.2s;
    }
    .top-menu nav a:hover {
      color: gray;
    }
    .dark-toggle {
      cursor: pointer;
      font-size: 0.9rem;
    }
    .container {
      display: flex;
      height: calc(100% - 60px);
      flex-direction: row;
    }
    .sidebar {
      width: 40%;
      padding: 2rem;
      overflow-y: auto;
      position: relative;
    }
    .project-list {
      display: flex;
      flex-direction: column;
    }
    .project-item {
      font-size: 2.5rem;
      cursor: pointer;
      transition: all 0.3s ease;
      position: relative;
      padding: 2rem 1.5rem;
      padding-right: 3rem;
      background: transparent;
      border-bottom: 1px solid var(--text-color);
      text-align: center;
    }
    .project-item:hover {
      background-color: var(--hover-bg);
    }
    .project-item.selected {
      background-color: var(--accent-color);
      color: var(--highlight-color);
    }
    .project-item.selected::after {
      content: '';
      position: absolute;
      right: 20%;
      top: 50%;
      transform: translateY(-50%);
      width: 10px;
      height: 10px;
      background-color: var(--text-color);
      border-radius: 50%;
    }
    .preview-image {
      position: fixed;
      top: 55%;
      left: 400px;
      transform: translateY(-50%) scale(1.35);
      max-width: 30vw;
      max-height: 30vh;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.3s ease, transform 0.3s ease, top 0.3s;
      z-index: 10;
      border-radius: 8px;
    }
    .project-content {
      width: 60%;
      padding: 2rem;
      overflow-y: auto;
      display: flex;
      flex-direction: column;
      gap: 2rem;
      opacity: 0;
      animation: fadeIn 0.4s ease forwards;
    }
    @keyframes fadeIn {
      to {
        opacity: 1;
      }
    }
    .project-section {
      margin-bottom: 2rem;
    }
    .project-section h2 {
      font-size: 2rem;
      margin-top: 1rem;
    }
    .project-section p {
      font-size: 1.2rem;
      margin-top: 1rem;
    }
    .project-section img {
      width: 100%;
      display: block;
      margin-bottom: 1rem;
      opacity: 0;
      animation: fadeInImage 1s ease forwards;
    }
    @keyframes fadeInImage {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    .fixed-contact {
      position: fixed;
      bottom: 1rem;
      left: 2rem;
      font-size: 0.9rem;
    }
    .fixed-contact a {
      text-decoration: none;
      color: var(--text-color);
      margin-right: 1rem;
    }
    .custom-cursor {
      position: fixed;
      top: 0;
      left: 0;
      width: 24px;
      height: 24px;
      background: var(--text-color);
      border-radius: 50%;
      pointer-events: none;
      z-index: 9999;
      mix-blend-mode: difference;
      transition: transform 0.1s ease;
    }
    @media (max-width: 768px) {
      .container {
        flex-direction: column;
      }
      .sidebar, .project-content {
        width: 100%;
        padding: 1rem;
      }
      .project-item {
        font-size: 1.5rem;
      }
      .preview-image {
        display: none;
      }
    }
  </style>
</head>
<body data-theme="dark">
  <div class="custom-cursor" id="customCursor"></div>
  <div class="top-menu">
    <div class="top-left">
      <div class="logo-placeholder"></div>
      <nav><a href="#">GER+GER</a></nav>
    </div>
    <div class="dark-toggle" onclick="toggleDarkMode()">🌙</div>
  </div>
  <div class="container">
    <div class="sidebar">
      <div class="project-list">
        <div class="project-item" tabindex="0" data-img="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif" data-content='<div class="project-section"><img src="img/Image_02.jpeg"><img src="https://portorocha.com/static/a6879d967fd67d83dc9e4f101e781ccf-8181be0a6c5afcb0cdd7c1499ec6f48c.jpg"><img src="https://portorocha.com/static/99db7a38cc40c051c6755d78894c5cd0-a144629043bc3a2572d4840b1453cb2d.jpg"><img src="https://portorocha.com/static/66168103789779a3e3afe46b75ac7448-8e109d52375074ba1fe09591d71c7df4.jpg"><h2>Project One</h2><p>This is a brief description of Project One.</p></div>'>Project One</div>
        <div class="project-item" tabindex="0" data-img="https://media.giphy.com/media/xUOxfgvTfz9hD0p7Ju/giphy.gif" data-content='<div class="project-section"><img src="https://portorocha.com/static/be991b08cc13b448ecd70354934c20aa-d0f98c20fbc69cabbb81cd0bc9464791.jpg"><img src="https://portorocha.com/static/a6879d967fd67d83dc9e4f101e781ccf-8181be0a6c5afcb0cdd7c1499ec6f48c.jpg"><img src="https://portorocha.com/static/99db7a38cc40c051c6755d78894c5cd0-a144629043bc3a2572d4840b1453cb2d.jpg"><img src="https://portorocha.com/static/66168103789779a3e3afe46b75ac7448-8e109d52375074ba1fe09591d71c7df4.jpg"><h2>Project Two</h2><p>This is a brief description of Project Two.</p></div>'>Project Two</div>
        <div class="project-item" tabindex="0" data-img="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif" data-content='<div class="project-section"><img src="https://portorocha.com/static/be991b08cc13b448ecd70354934c20aa-d0f98c20fbc69cabbb81cd0bc9464791.jpg"><img src="https://portorocha.com/static/a6879d967fd67d83dc9e4f101e781ccf-8181be0a6c5afcb0cdd7c1499ec6f48c.jpg"><img src="https://portorocha.com/static/99db7a38cc40c051c6755d78894c5cd0-a144629043bc3a2572d4840b1453cb2d.jpg"><img src="https://portorocha.com/static/66168103789779a3e3afe46b75ac7448-8e109d52375074ba1fe09591d71c7df4.jpg"><h2>Project Three</h2><p>This is a brief description of Project Three.</p></div>'>Project Three</div>

        <div class="project-item" tabindex="0" data-img="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif" data-content='<div class="project-section"><img src="https://portorocha.com/static/be991b08cc13b448ecd70354934c20aa-d0f98c20fbc69cabbb81cd0bc9464791.jpg"><img src="https://portorocha.com/static/a6879d967fd67d83dc9e4f101e781ccf-8181be0a6c5afcb0cdd7c1499ec6f48c.jpg"><img src="https://portorocha.com/static/99db7a38cc40c051c6755d78894c5cd0-a144629043bc3a2572d4840b1453cb2d.jpg"><img src="https://portorocha.com/static/66168103789779a3e3afe46b75ac7448-8e109d52375074ba1fe09591d71c7df4.jpg"><h2>Project Four</h2><p>This is a brief description of Project Cuatro.</p></div>'>Project Four</div>
      </div>
    </div>
    <div class="project-content" id="projectContent"></div>
    <img class="preview-image" id="preview" src="" alt="Preview" />
  </div>
  <div class="fixed-contact">
    <a href="mailto:hello@gerry.com">Contact</a>
    <a href="https://www.instagram.com" target="_blank">Instagram</a>
    <a href="https://www.linkedin.com" target="_blank">LinkedIn</a>
  </div>
  <script>
    const preview = document.getElementById('preview');
    const items = document.querySelectorAll('.project-item');
    const projectContent = document.getElementById('projectContent');
    const toggleBtn = document.querySelector('.dark-toggle');
    const customCursor = document.getElementById('customCursor');

    document.addEventListener('mousemove', e => {
      customCursor.style.transform = `translate(${e.clientX - 12}px, ${e.clientY - 12}px)`;
    });

    items.forEach(item => {
      item.addEventListener('mouseenter', () => {
        const imgSrc = item.getAttribute('data-img');
        preview.src = imgSrc;
        preview.style.opacity = 1;
        preview.style.transform = 'translateY(-50%) scale(1.35)';
      });
      item.addEventListener('mousemove', (e) => {
        preview.style.left = `${e.clientX + 40}px`;
        const offsetY = 200; // Adjust the vertical offset here as needed
        preview.style.top = `${e.clientY + offsetY}px`;
      });
      item.addEventListener('mouseleave', () => {
        preview.style.opacity = 0;
        preview.style.transform = 'translateY(-50%) scale(1.2)';
      });
      item.addEventListener('click', () => {
        items.forEach(i => i.classList.remove('selected'));
        item.classList.add('selected');
        const content = item.getAttribute('data-content');
        projectContent.innerHTML = content;
        projectContent.scrollTo({ top: 0, behavior: 'smooth' });
      });
      item.addEventListener('keydown', (e) => {
        if (e.key === 'Enter') {
          item.click();
        }
      });
    });

    function toggleDarkMode() {
      const isDark = document.body.dataset.theme === 'dark';
      document.body.dataset.theme = isDark ? '' : 'dark';
      toggleBtn.textContent = isDark ? '🌙' : '☀️';
    }

    window.addEventListener('DOMContentLoaded', () => {
      const first = document.querySelector('.project-item');
      if (first) {
        const content = first.getAttribute('data-content');
        projectContent.innerHTML = content;
        first.classList.add('selected');
      }
    });
  </script>
</body>
</html>
