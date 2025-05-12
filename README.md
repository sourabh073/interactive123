index.html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Bundle & Save</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="container">
    <div class="heading">Bundle & Save</div>

    <div class="bundle-option" onclick="selectOption(this, 195)">
      <input type="radio" name="bundle">
      <div class="bundle-content">
        <div class="pair-info">
          <div>1 Pair</div>
          <div class="sub">50% OFF</div>
        </div>
        <div class="price">DKK 195.00</div>
      </div>
    </div>

    <div class="bundle-option selected" onclick="selectOption(this, 345)">
      <div class="most-popular">Most Popular</div>
      <input type="radio" name="bundle" checked>
      <div class="bundle-content">
        <div class="pair-info">
          <div>2 Pair</div>
          <div class="sub">40% OFF</div>
        </div>
        <div class="price">
          <s>DKK 195.00</s> <span class="bold">345.00</span>
        </div>
      </div>
      <div class="options">
        <div class="dropdown">
          <label>#1</label>
          <select>
            <option>Size</option><option>S</option><option>M</option><option>L</option>
          </select>
          <select>
            <option>Colour</option><option>Black</option><option>Blue</option>
          </select>
        </div>
        <div class="dropdown">
          <label>#2</label>
          <select>
            <option>Size</option><option>S</option><option>M</option><option>L</option>
          </select>
          <select>
            <option>Colour</option><option>Black</option><option>Blue</option>
          </select>
        </div>
      </div>
    </div>

    <div class="bundle-option" onclick="selectOption(this, 528)">
      <input type="radio" name="bundle">
      <div class="bundle-content">
        <div class="pair-info">
          <div>3 Pair</div>
          <div class="sub">60% OFF</div>
        </div>
        <div class="price">DKK 528.00</div>
      </div>
    </div>

    <div class="shipping">Free 2 Day Shipping</div>
    <div class="total">Total: <strong>DKK 360.00</strong></div>
    <button class="add-to-cart">+ Add to Cart</button>
  </div>

  <script src="script.js"></script>
</body>
</html>

styles.css
body {
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
  display: flex;
  justify-content: center;
  padding: 30px;
}

.container {
  background: #fff;
  border-radius: 10px;
  padding: 20px;
  max-width: 400px;
  width: 100%;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

.heading {
  font-weight: bold;
  font-size: 20px;
  text-align: center;
  margin-bottom: 20px;
}

.bundle-option {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 12px;
  margin-bottom: 15px;
  position: relative;
  cursor: pointer;
}

.bundle-option.selected {
  border-color: #007a5a;
  background-color: #eafff3;
}

.most-popular {
  position: absolute;
  top: -10px;
  right: 10px;
  background: #007a5a;
  color: white;
  padding: 2px 8px;
  font-size: 12px;
  border-radius: 4px;
  font-weight: bold;
}

.bundle-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.pair-info .sub {
  font-size: 12px;
  color: #555;
}

.price {
  font-weight: bold;
  color: #000;
  text-align: right;
}

.price s {
  color: gray;
  font-size: 13px;
}

.price .bold {
  font-weight: bold;
  font-size: 16px;
}

.options {
  margin-top: 10px;
}

.dropdown {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-top: 8px;
}

select {
  padding: 5px;
  width: 100px;
}

.shipping {
  color: #007a5a;
  font-size: 14px;
  margin-top: 10px;
}

.total {
  font-weight: bold;
  margin: 10px 0;
  font-size: 16px;
}

.add-to-cart {
  width: 100%;
  background-color: #007a5a;
  color: white;
  padding: 12px;
  border: none;
  border-radius: 8px;
  font-size: 16px;
  cursor: pointer;
}

script.js
function selectOption(element, price) {
  const allOptions = document.querySelectorAll('.bundle-option');
  allOptions.forEach(opt => opt.classList.remove('selected'));
  element.classList.add('selected');
  element.querySelector('input[type="radio"]').checked = true;

  document.querySelector('.total').innerHTML = `Total: <strong>DKK ${price.toFixed(2)}</strong>`;
}


