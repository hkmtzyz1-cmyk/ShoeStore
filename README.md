# Shoe<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>متجر الأحذية الكبير - ShoeStore</title>

  <!-- CSS مدمج -->
  <style>
    /* Reset */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Arial', sans-serif;
    }

    body {
      background: #f9f9f9;
      color: #111;
      scroll-behavior: smooth;
    }

    a {
      text-decoration: none;
    }

    button {
      cursor: pointer;
    }

    /* Navbar */
    header {
      background: #1b1b1b;
      color: #fff;
      padding: 15px 0;
      position: sticky;
      top: 0;
      z-index: 100;
      box-shadow: 0 2px 10px rgba(0,0,0,0.2);
    }

    .nav-container {
      width: 90%;
      margin: auto;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 2rem;
      font-weight: bold;
      color: #ff6b00;
    }

    nav ul {
      display: flex;
      list-style: none;
      gap: 25px;
    }

    nav ul li a {
      color: #fff;
      font-weight: 500;
      transition: 0.3s;
    }

    nav ul li a:hover {
      color: #ff6b00;
    }

    .cart-icon {
      font-size: 1.3rem;
      position: relative;
    }

    .cart-icon span {
      position: absolute;
      top: -8px;
      right: -10px;
      background: #ff6b00;
      color: #fff;
      padding: 2px 6px;
      border-radius: 50%;
      font-size: 0.8rem;
      font-weight: bold;
    }

    /* Hero Section */
    .hero {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 80px 10%;
      background: linear-gradient(135deg,#ff512f,#dd2476);
      color: #fff;
      flex-wrap: wrap;
      border-bottom-left-radius: 50px;
      border-bottom-right-radius: 50px;
    }

    .hero-text {
      max-width: 500px;
      margin-bottom: 20px;
    }

    .hero-text h1 {
      font-size: 3rem;
      margin-bottom: 20px;
      line-height: 1.2;
    }

    .hero-text p {
      font-size: 1.3rem;
      margin-bottom: 30px;
      opacity: 0.9;
    }

    .btn {
      display: inline-block;
      padding: 15px 35px;
      background: #fff;
      color: #ff512f;
      font-weight: bold;
      border-radius: 50px;
      transition: 0.3s;
      font-size: 1rem;
    }

    .btn:hover {
      background: #ff6b00;
      color: #fff;
      transform: scale(1.05);
    }

    .hero-image img {
      width: 500px;
      max-width: 100%;
      border-radius: 30px;
      box-shadow: 0 20px 50px rgba(0,0,0,0.3);
      transform: rotate(-2deg);
      transition: 0.3s;
    }

    .hero-image img:hover {
      transform: rotate(0deg) scale(1.05);
    }

    /* Products Section */
    .products {
      padding: 80px 10%;
    }

    .products h2 {
      text-align: center;
      font-size: 2.8rem;
      margin-bottom: 60px;
      color: #111;
    }

    .products-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 40px;
    }

    .product-card {
      background: #fff;
      border-radius: 20px;
      box-shadow: 0 15px 35px rgba(0,0,0,0.1);
      padding: 20px;
      text-align: center;
      transition: 0.4s;
      overflow: hidden;
    }

    .product-card:hover {
      transform: translateY(-10px) scale(1.02);
      box-shadow: 0 25px 50px rgba(0,0,0,0.2);
    }

    .product-card img {
      width: 100%;
      border-radius: 20px;
      margin-bottom: 15px;
      transition: 0.3s;
    }

    .product-card img:hover {
      transform: scale(1.05);
    }

    .product-card h3 {
      font-size: 1.3rem;
      margin-bottom: 10px;
      color: #111;
    }

    .product-card .price {
      font-weight: bold;
      margin-bottom: 15px;
      font-size: 1.1rem;
      color: #ff6b00;
    }

    .product-card button {
      background: linear-gradient(45deg,#ff512f,#dd2476);
      color: white;
      border: none;
      padding: 12px 30px;
      border-radius: 50px;
      font-weight: bold;
      font-size: 1rem;
      transition: 0.3s;
    }

    .product-card button:hover {
      opacity: 0.85;
      transform: scale(1.05);
    }

    /* About Section */
    .about, .contact {
      padding: 80px 10%;
      text-align: center;
      background: #fff;
      border-radius: 30px;
      margin: 50px 0;
      box-shadow: 0 15px 40px rgba(0,0,0,0.05);
    }

    .about h2, .contact h2 {
      font-size: 2.5rem;
      margin-bottom: 25px;
      color: #111;
    }

    .about p, .contact p {
      font-size: 1.2rem;
      opacity: 0.85;
      line-height: 1.6;
    }

    .contact .btn {
      margin-top: 20px;
      font-size: 1.1rem;
      padding: 12px 35px;
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 25px;
      background: #1b1b1b;
      color: #fff;
      font-size: 0.9rem;
    }

    /* Responsive */
    @media(max-width:992px){
      .hero {
        flex-direction: column-reverse;
        text-align: center;
      }

      .hero-image {
        margin-bottom: 30px;
      }
    }

    @media(max-width:600px){
      nav ul {
        flex-direction: column;
        gap: 15px;
      }

      .hero-text h1 {
        font-size: 2.2rem;
      }

      .products-container {
        gap: 25px;
      }
    }/* ===== Hero Image Styling ===== */
.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
}

.hero-image img {
  width: 260px;              /* حجم صغير وأنيق */
  height: 260px;
  object-fit: cover;
  border-radius: 50%;        /* يجعلها دائرية */
  
  background: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(10px);
  
  box-shadow:
    0 15px 35px rgba(0, 0, 0, 0.25),
    inset 0 0 20px rgba(255, 255, 255, 0.3);

  border: 4px solid rgba(255, 255, 255, 0.4);

  transition: all 0.4s ease;
}

/* تأثير عند المرور بالماوس */
.hero-image img:hover {
  transform: scale(1.08) rotate(-3deg);
  box-shadow:
    0 25px 50px rgba(0, 0, 0, 0.35),
    inset 0 0 25px rgba(255, 255, 255, 0.4);
}

.instagram {
  background: linear-gradient(45deg, #f58529, #dd2a7b, #8134af);
  color: #fff;
}

  </style>
</head>
<body>

  <!-- Navbar -->
  <header>
    <div class="nav-container">
      <h1 class="logo">ShoeStore</h1>
      <nav>
        <ul>
          <li><a href="#home">الرئيسية</a></li>
          <li><a href="#products">الأحذية</a></li>
          <li><a href="#about">من نحن</a></li>
          <li><a href="#contact">اتصل بنا</a></li>
        </ul>
      </nav>
      <div class="cart-icon">
        🛒 <span id="cart-count">0</span>
      </div>
    </div>
  </header>

  <!-- Hero Section -->
<section id="home" class="hero">
  <div class="hero-text">
    <h1>أفضل الأحذية العصرية<br>لجميع الأعمار</h1>
    <p>اكتشف مجموعتنا الجديدة من الأحذية الرياضية والكاجوال مع خدمة توصيل سريعة وآمنة.</p>
    <a href="#products" class="btn">تسوق الآن</a>
  </div>
  <div class="hero-image">
    <img src="er.jpeg" alt="حذاء عصري">
  </div>
</section>

<!-- Products Section -->
<section id="products" class="products">
  <h2>أحذيتنا</h2>
  <div class="products-container">
    
    <!-- صف 1 -->
    <div class="product-card">
      <img src="ff.jpeg" alt="Nike Air Max">
      <h3>Nike Air Max</h3>
      <p class="price">799 DH</p>
      <button onclick="addToCart('Nike Air Max')">أضف إلى السلة</button>
    </div>
    <div class="product-card">
      <img src="fv.jpeg" alt="Adidas Superstar">
      <h3>Adidas Superstar</h3>
      <p class="price">699 DH</p>
      <button onclick="addToCart('Adidas Superstar')">أضف إلى السلة</button>
    </div>
    <div class="product-card">
      <img src="ga.jpeg" alt="Puma RS-X">
      <h3>Puma RS-X</h3>
      <p class="price">749 DH</p>
      <button onclick="addToCart('Puma RS-X')">أضف إلى السلة</button>
    </div>
    <div class="product-card">
      <img src="ghy.jpeg" alt="Reebok Classic">
      <h3>Reebok Classic</h3>
      <p class="price">689 DH</p>
      <button onclick="addToCart('Reebok Classic')">أضف إلى السلة</button>
    </div>

    <!-- صف 2 (نفس الأربعة منتجات) -->
    <div class="product-card">
      <img src="yy.jpeg" alt="Nike Air Max">
      <h3>Nike Air Max</h3>
      <p class="price">799 DH</p>
      <button onclick="addToCart('Nike Air Max')">أضف إلى السلة</button>
    </div>
    <div class="product-card">
      <img src="vvv.jpeg" alt="Adidas Superstar">
      <h3>Adidas Superstar</h3>
      <p class="price">699 DH</p>
      <button onclick="addToCart('Adidas Superstar')">أضف إلى السلة</button>
    </div>
    <div class="product-card">
      <img src="o.jpeg" alt="Puma RS-X">
      <h3>Puma RS-X</h3>
      <p class="price">749 DH</p>
      <button onclick="addToCart('Puma RS-X')">أضف إلى السلة</button>
    </div>
    <div class="product-card">
      <img src="oo.jpeg" alt="Reebok Classic">
      <h3>Reebok Classic</h3>
      <p class="price">689 DH</p>
      <button onclick="addToCart('Reebok Classic')">أضف إلى السلة</button>
    </div>

    <!-- صف 3 (نفس الأربعة منتجات) -->
    <div class="product-card">
      <img src="ggg.jpeg"alt="Nike Air Max">
      <h3>Nike Air Max</h3>
      <p class="price">799 DH</p>
      <button onclick="addToCart('Nike Air Max')">أضف إلى السلة</button>
    </div>
    <div class="product-card">
      <img src="jjjj.jpeg" alt="Adidas Superstar">
      <h3>Adidas Superstar</h3>
      <p class="price">699 DH</p>
      <button onclick="addToCart('Adidas Superstar')">أضف إلى السلة</button>
    </div>
    <div class="product-card">
      <img src="ic.jpeg" alt="Puma RS-X">
      <h3>Puma RS-X</h3>
      <p class="price">749 DH</p>
      <button onclick="addToCart('Puma RS-X')">أضف إلى السلة</button>
    </div>
    <div class="product-card">
      <img src="lx.jpeg" alt="Reebok Classic">
      <h3>Reebok Classic</h3>
      <p class="price">689 DH</p>
      <button onclick="addToCart('Reebok Classic')">أضف إلى السلة</button>
    </div>

  </div>
</section>

  <!-- About Section -->
  <section id="about" class="about">
    <h2>من نحن</h2>
    <p>متجر ShoeStore متخصص في بيع الأحذية العصرية بأفضل الأسعار. نحن نضمن جودة عالية وخدمة عملاء ممتازة لتجربة تسوق ممتعة لكل زبون.</p>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="contact">
  <h2>اتصل بنا</h2>
  <p>للطلب أو الاستفسار، راسلنا عبر واتساب:</p>
  <a href="https://wa.me/212658653193" class="btn" target="_blank">
    راسلنا الآن
  </a><a href="https://www.instagram.com/bdlzyzlkhldy331?igsh=czdjbmV2MDE0ZHZr" 
   class="btn instagram" 
   target="_blank">
  تابعنا على إنستقرام
</a>

</section>
  <!-- Footer -->
  <footer>
    <p>&copy; 2026 متجر ShoeStore - جميع الحقوق محفوظة</p>
  </footer>

  <!-- JavaScript لسلة المشتريات -->
  <script>
    let cartCount = 0;
    function addToCart(productName){
      cartCount++;
      document.getElementById('cart-count').innerText = cartCount;
      alert(productName + " تم إضافته إلى السلة!");
    }
  </script>

</body>
</html>Store
Simple shoe store website using HTML and CSS
