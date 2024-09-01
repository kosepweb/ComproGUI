<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Nama Perusahaan Anda</title>
  <link rel="stylesheet" href="styles.css" />
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link
    href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap"
    rel="stylesheet"
  />
  <style>
    /* General Styles */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Poppins', sans-serif;
      line-height: 1.6;
      color: #333;
      background-color: #f4f4f4;
    }

    .container {
      width: 90%;
      max-width: 1200px;
      margin: auto;
      padding: 40px 0;
    }

    h1, h2, h3, h4 {
      margin-bottom: 20px;
      font-weight: 600;
    }

    /* Header */
    header {
      background: #fff;
      padding: 20px 0;
      position: fixed;
      width: 100%;
      top: 0;
      z-index: 100;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    .header-content {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .logo {
      height: 60px;
    }

    .company-name h1 {
      font-size: 1.75rem;
      color: #007bff;
      margin-bottom: 5px;
    }

    .company-name p {
      font-size: 1rem;
      color: #666;
    }

    /* Hero Section */
    .hero {
      background: linear-gradient(to right, rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('foto1.jpg') no-repeat center center/cover;
      height: 100vh;
      display: flex;
      align-items: center;
      color: #fff;
      text-align: center;
      position: relative;
      padding-top: 100px;
    }

    .hero h1 {
      font-size: 3rem;
      margin-bottom: 20px;
      animation: fadeInDown 1s ease-in-out;
    }

    .hero h1 span {
      color: #ffc107;
    }

    .hero p {
      font-size: 1.25rem;
      margin-bottom: 30px;
      animation: fadeInUp 1s ease-in-out;
    }

    .btn {
      display: inline-block;
      padding: 12px 30px;
      background-color: #007bff;
      color: #fff;
      border-radius: 50px;
      text-decoration: none;
      font-weight: 500;
      transition: background-color 0.3s, transform 0.3s;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .btn:hover {
      background-color: #0056b3;
      transform: scale(1.05);
    }

    /* About Section */
    .about {
      background-color: #fff;
      padding: 80px 0;
      text-align: center;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      margin-top: 60px;
    }

    .about-content {
      animation: fadeIn 1s ease-in-out;
    }

    .about h2 {
      margin-bottom: 20px;
      font-size: 2.25rem;
      color: #007bff;
    }

    .about p {
      margin: 0 auto;
      max-width: 800px;
      color: #666;
      font-size: 1.1rem;
      line-height: 1.7;
    }

    /* Services Section */
    .services {
      padding: 80px 0;
      text-align: center;
    }

    .services-wrapper {
      display: flex;
      flex-wrap: wrap;
      gap: 30px;
      justify-content: center;
    }

    .service-item {
      background-color: #fff;
      padding: 20px;
      border-radius: 15px;
      width: 300px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
      transition: transform 0.3s, box-shadow 0.3s;
      animation: fadeInUp 1s ease-in-out;
    }

    .service-item:hover {
      transform: translateY(-10px);
      box-shadow: 0 6px 16px rgba(0, 0, 0, 0.2);
    }

    .service-item img {
      height: 80px;
      margin-bottom: 20px;
    }

    .service-item h3 {
      margin-bottom: 15px;
      font-size: 1.5rem;
      color: #007bff;
    }

    .service-item p {
      color: #666;
    }

    /* Portfolio Section */
    .portfolio {
      padding: 80px 0;
      text-align: center;
    }

    .portfolio-wrapper {
      display: flex;
      flex-wrap: wrap;
      gap: 30px;
      justify-content: center;
    }

    .portfolio-item {
      background-color: #fff;
      padding: 15px;
      border-radius: 15px;
      width: 300px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
      cursor: pointer;
      transition: transform 0.3s, box-shadow 0.3s;
    }

    .portfolio-item:hover {
      transform: scale(1.05);
      box-shadow: 0 6px 16px rgba(0, 0, 0, 0.2);
    }

    .portfolio-item img {
      width: 100%;
      height: auto;
      border-radius: 10px;
    }

    /* Modal Container */
    .modal {
      display: none; /* Hide by default */
      position: fixed;
      z-index: 1000;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: auto;
      background-color: rgba(0, 0, 0, 0.8); /* Background overlay */
      justify-content: center;
      align-items: center;
    }

    /* Modal Content */
    .modal-content {
      background-color: #fff;
      margin: 15px;
      padding: 20px;
      border-radius: 15px;
      max-width: 80%;
      max-height: 80%;
      overflow: hidden;
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    /* Image inside Modal */
    .modal-content img {
      max-width: 100%;
      max-height: 100%;
      object-fit: contain;
      display: none;
    }

    /* Show the current image */
    .modal-content img.active {
      display: block;
    }

    /* Close Button */
    .modal-close {
      color: #aaa;
      float: right;
      font-size: 28px;
      font-weight: bold;
      cursor: pointer;
    }

    .modal-close:hover,
    .modal-close:focus {
      color: black;
      text-decoration: none;
    }

    /* Navigation Buttons */
    .modal-prev, .modal-next {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background-color: rgba(0, 0, 0, 0.6);
      color: #fff;
      border: none;
      padding: 10px;
      cursor: pointer;
      font-size: 24px;
      border-radius: 50%;
      z-index: 1001;
    }

    .modal-prev {
      left: 10px;
    }

    .modal-next {
      right: 10px;
    }

    .modal-prev:hover,
    .modal-next:hover {
      background-color: rgba(0, 0, 0, 0.8);
    }

    /* Footer */
    footer {
      background-color: #007bff;
      color: #fff;
      padding: 20px 0;
      text-align: center;
      position: relative;
    }

    footer a {
      color: #fff;
      text-decoration: none;
      font-weight: 500;
    }

    footer a:hover {
      text-decoration: underline;
    }

    /* Animations */
    @keyframes fadeInDown {
      from {
        opacity: 0;
        transform: translateY(-30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
      }
      to {
        opacity: 1;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="container header-content">
      <div class="header-inner">
        <img src="logo.png" alt="Logo Perusahaan" class="logo" />
        <div class="company-name">
          <h1>Nama Perusahaan</h1>
          <p>Tagline atau Deskripsi Singkat</p>
        </div>
      </div>
    </div>
  </header>

  <section class="hero">
    <div class="container">
      <h1>Selamat Datang di <span>Nama Perusahaan</span></h1>
      <p>Kami menyediakan solusi terbaik untuk kebutuhan Anda.</p>
      <a href="#contact" class="btn">Kontak Kami</a>
    </div>
  </section>

  <section class="about">
    <div class="container about-content">
      <h2>Tentang Kami</h2>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla vel turpis eu mauris bibendum dapibus. Donec vitae enim ut dolor ultricies aliquet.</p>
    </div>
  </section>

  <section class="services">
    <div class="container">
      <h2>Layanan Kami</h2>
      <div class="services-wrapper">
        <div class="service-item">
          <img src="service1.png" alt="Layanan 1" />
          <h3>Layanan 1</h3>
          <p>Deskripsi singkat layanan 1.</p>
        </div>
        <div class="service-item">
          <img src="service2.png" alt="Layanan 2" />
          <h3>Layanan 2</h3>
          <p>Deskripsi singkat layanan 2.</p>
        </div>
        <div class="service-item">
          <img src="service3.png" alt="Layanan 3" />
          <h3>Layanan 3</h3>
          <p>Deskripsi singkat layanan 3.</p>
        </div>
      </div>
    </div>
  </section>

  <section class="portfolio">
    <div class="container">
      <h2>Portofolio Kami</h2>
      <div class="portfolio-wrapper">
        <div class="portfolio-item" data-modal="modal1">
          <img src="portfolio1.jpg" alt="Proyek 1" />
          <h3>Proyek 1</h3>
        </div>
        <div class="portfolio-item" data-modal="modal2">
          <img src="portfolio2.jpg" alt="Proyek 2" />
          <h3>Proyek 2</h3>
        </div>
        <div class="portfolio-item" data-modal="modal3">
          <img src="portfolio3.jpg" alt="Proyek 3" />
          <h3>Proyek 3</h3>
        </div>
      </div>
    </div>
  </section>

  <!-- Modal 1 -->
  <div id="modal1" class="modal">
    <div class="modal-content">
      <span class="modal-close">&times;</span>
      <img src="portfolio1-1.jpg" class="active" alt="Proyek 1 - 1" />
      <img src="portfolio1-2.jpg" alt="Proyek 1 - 2" />
      <img src="portfolio1-3.jpg" alt="Proyek 1 - 3" />
      <button class="modal-prev">&#10094;</button>
      <button class="modal-next">&#10095;</button>
    </div>
  </div>

  <!-- Modal 2 -->
  <div id="modal2" class="modal">
    <div class="modal-content">
      <span class="modal-close">&times;</span>
      <img src="portfolio2-1.jpg" class="active" alt="Proyek 2 - 1" />
      <img src="portfolio2-2.jpg" alt="Proyek 2 - 2" />
      <img src="portfolio2-3.jpg" alt="Proyek 2 - 3" />
      <button class="modal-prev">&#10094;</button>
      <button class="modal-next">&#10095;</button>
    </div>
  </div>

  <!-- Modal 3 -->
  <div id="modal3" class="modal">
    <div class="modal-content">
      <span class="modal-close">&times;</span>
      <img src="portfolio3-1.jpg" class="active" alt="Proyek 3 - 1" />
      <img src="portfolio3-2.jpg" alt="Proyek 3 - 2" />
      <img src="portfolio3-3.jpg" alt="Proyek 3 - 3" />
      <button class="modal-prev">&#10094;</button>
      <button class="modal-next">&#10095;</button>
    </div>
  </div>

  <footer>
    <div class="container">
      <p>&copy; 2024 Nama Perusahaan. Semua Hak Dilindungi.</p>
      <a href="#contact" class="btn">Kontak Kami</a>
    </div>
  </footer>

  <script>
    // JavaScript for modal functionality
    const modals = document.querySelectorAll('.modal');
    const portfolioItems = document.querySelectorAll('.portfolio-item');

    portfolioItems.forEach(item => {
      item.addEventListener('click', () => {
        const modalId = item.getAttribute('data-modal');
        const modal = document.getElementById(modalId);
        modal.style.display = 'flex';
      });
    });

    const closeButtons = document.querySelectorAll('.modal-close');
    closeButtons.forEach(button => {
      button.addEventListener('click', () => {
        button.closest('.modal').style.display = 'none';
      });
    });

    // Modal navigation
    const prevButtons = document.querySelectorAll('.modal-prev');
    const nextButtons = document.querySelectorAll('.modal-next');

    prevButtons.forEach(button => {
      button.addEventListener('click', () => {
        const modal = button.closest('.modal');
        const images = modal.querySelectorAll('.modal-content img');
        const current = modal.querySelector('.modal-content img.active');
        let index = Array.from(images).indexOf(current);

        if (index > 0) {
          images[index].classList.remove('active');
          images[index - 1].classList.add('active');
        }
      });
    });

    nextButtons.forEach(button => {
      button.addEventListener('click', () => {
        const modal = button.closest('.modal');
        const images = modal.querySelectorAll('.modal-content img');
        const current = modal.querySelector('.modal-content img.active');
        let index = Array.from(images).indexOf(current);

        if (index < images.length - 1) {
          images[index].classList.remove('active');
          images[index + 1].classList.add('active');
        }
      });
    });

    // Close modal if clicked outside
    window.addEventListener('click', event => {
      if (event.target.classList.contains('modal')) {
        event.target.style.display = 'none';
      }
    });
  </script>
</body>
</html>
