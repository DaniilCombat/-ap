<!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="UTF-8">
  <title>FastCap</title>
  <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Irish+Grover&family=Lobster&family=Russo+One&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Russo One', sans-serif;
      background: #fff;
    }

    .wrapper {
      display: flex;
      flex-direction: row;
      min-height: 100vh;
    }

    /* Sidebar */
    .sidebar {
      width: 160px;
      background: #8BE8CD;
      padding: 10px;
      box-sizing: border-box;
      font-size: 13px;
      flex-shrink: 0;
    }

    .sidebar h2 {
      font-family: 'Russo One';
      font-size: 15px;
      margin: 10px 0;
    }

    .filter-group {
      margin: 15px 0;
    }

    .filter-option {
      margin: 5px 0;
      cursor: pointer;
      user-select: none;
    }

    .filter-option.active {
      text-decoration: underline;
    }

    .color-box {
      width: 105px;
      height: 20px;
      margin: 5px 0;
      cursor: pointer;
      border: 1px solid #000;
    }

    .color-box.active {
      outline: 3px solid #E55252;
    }

    .black { background: #000; }
    .white { background: #fff; }
    .green { background: #37D237; }
    .yellow { background: #E7EF77; }
    .blue { background: #0900FF; }
    .grey { background: #A0A0A0; }

    /* Main */
    .main {
      flex: 1;
      background: #8EF3D6;
      min-height: 794px;
      display: flex;
      flex-direction: column;
    }

    .header {
      background: #FFFF00;
      height: 60px;
      display: flex;
      align-items: center;
      padding-left: 20px;
      font-family: 'Irish Grover';
      font-size: 48px;
    }

    .line-red {
      height: 4px;
      background: #E55252;
    }

    .menu {
      background: #FFFF00;
      display: flex;
      gap: 20px;
      padding: 5px 20px;
      font-family: 'Lobster';
      font-size: 14px;
      flex-wrap: wrap;
    }

    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 20px;
      padding: 20px;
    }

    .product {
      background: #fff;
      border: 1px solid #000;
      padding: 10px;
      font-family: 'Press Start 2P';
      font-size: 10px;
      text-align: center;
    }

    .product img {
      width: 100%;
      height: 120px;
      object-fit: cover;
      margin-bottom: 5px;
    }

    .price {
      margin-top: 5px;
      font-weight: bold;
    }

    /* Адаптив */
    @media (max-width: 768px) {
      .wrapper {
        flex-direction: column;
      }
      .sidebar {
        width: 100%;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        font-size: 12px;
      }
      .color-box {
        width: 40px;
        height: 20px;
      }
    }
  </style>
</head>
<body>
  <div class="wrapper">
    <!-- Sidebar -->
    <div class="sidebar">
      <h2>Фільтри</h2>

      <div class="filter-group" data-filter="gender">
        <div class="filter-option" data-value="all">Усі</div>
        <div class="filter-option" data-value="male">Чоловічі</div>
        <div class="filter-option" data-value="female">Жіночі</div>
        <div class="filter-option" data-value="unisex">Унісекс</div>
        <div class="filter-option" data-value="kids">Дитячі</div>
      </div>

      <div class="filter-group" data-filter="color">
        <div class="filter-option">Колір</div>
        <div class="color-box black" data-value="black"></div>
        <div class="color-box white" data-value="white"></div>
        <div class="color-box green" data-value="green"></div>
        <div class="color-box yellow" data-value="yellow"></div>
        <div class="color-box blue" data-value="blue"></div>
        <div class="color-box grey" data-value="grey"></div>
      </div>

      <div class="filter-group" data-filter="print">
        <div class="filter-option" data-value="all">Всі</div>
        <div class="filter-option" data-value="no-print">Без принта</div>
        <div class="filter-option" data-value="print">З принтом</div>
      </div>
    </div>

    <!-- Main -->
    <div class="main">
      <div class="header">FastCap</div>
      <div class="line-red"></div>
      <div class="menu">
        <div>Головне</div>
        <div>Дитячі</div>
        <div>Чоловічі</div>
        <div>Жіночі</div>
      </div>

      <div class="products" id="product-list">
        <!-- Товари -->
        <div class="product" data-gender="male" data-color="black" data-print="no-print">
          <img src="image.png" alt="cap">
          <div>Кепка чорна</div>
          <div class="price">50$</div>
        </div>

        <div class="product" data-gender="female" data-color="white" data-print="no-print">
          <img src="image.png" alt="cap">
          <div>Кепка біла</div>
          <div class="price">50$</div>
        </div>

        <div class="product" data-gender="male" data-color="black" data-print="print">
          <img src="image.png" alt="cap">
          <div>Кепка чорна Нью-Йорк</div>
          <div class="price">100$</div>
        </div>

        <div class="product" data-gender="male" data-color="black" data-print="print">
          <img src="image.png" alt="cap">
          <div>Кепка чорна Лос-Анджелес</div>
          <div class="price">100$</div>
        </div>

        <div class="product" data-gender="unisex" data-color="green" data-print="no-print">
          <img src="image.png" alt="cap">
          <div>Кепка темно-зелена Polo</div>
          <div class="price">120$</div>
        </div>

        <div class="product" data-gender="female" data-color="yellow" data-print="print">
          <img src="image.png" alt="cap">
          <div>Кепка бежева Нью-Йорк</div>
          <div class="price">100$</div>
        </div>

        <div class="product" data-gender="male" data-color="grey" data-print="print">
          <img src="image.png" alt="cap">
          <div>Кепка камуфляж (ЗСУ знижка 75%)</div>
          <div class="price">100$</div>
        </div>

        <div class="product" data-gender="unisex" data-color="blue" data-print="no-print">
          <img src="image.png" alt="cap">
          <div>Кепка синя Polo</div>
          <div class="price">120$</div>
        </div>
      </div>
    </div>
  </div>

  <script>
    const filters = {
      gender: 'all',
      color: 'all',
      print: 'all'
    };

    const products = document.querySelectorAll('.product');

    // Обработка кликов по фильтрам
    document.querySelectorAll('.filter-option, .color-box').forEach(el => {
      el.addEventListener('click', () => {
        const parent = el.closest('[data-filter]');
        const type = parent.getAttribute('data-filter');
        const value = el.getAttribute('data-value');

        // Снять активность
        parent.querySelectorAll('.filter-option, .color-box').forEach(e => e.classList.remove('active'));
        // Активировать выбранный
        el.classList.add('active');

        // Сохранить выбранный фильтр
        filters[type] = value;

        applyFilters();
      });
    });

    function applyFilters() {
      products.forEach(p => {
        const matchGender = filters.gender === 'all' || p.dataset.gender === filters.gender;
        const matchColor = filters.color === 'all' || p.dataset.color === filters.color;
        const matchPrint = filters.print === 'all' || p.dataset.print === filters.print;

        if (matchGender && matchColor && matchPrint) {
          p.style.display = 'block';
        } else {
          p.style.display = 'none';
        }
      });
    }
  </script>
</body>
</html>

