# -psevdotasodifiy_sonlar
<!DOCTYPE html>
<html lang="uz">
<head>
  <meta charset="UTF-8">
  <title>Kongruent Generatorlar</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Kongruent Generatorlar</h1>

  <form id="generatorForm">
    <label>Generator turi:
      <select id="type">
        <option value="linear">Chiziqli</option>
        <option value="quadratic">Kvadratik</option>
        <option value="cubic">Kubik</option>
      </select>
    </label><br>

    <label>a: <input type="number" id="a" required></label><br>
    <label>b: <input type="number" id="b" required></label><br>
    <label>c: <input type="number" id="c"></label><br>
    <label>d: <input type="number" id="d"></label><br>
    <label>m (modul): <input type="number" id="m" required></label><br>
    <label>xn (boshlang‘ich qiymat): <input type="number" id="xn" required></label><br>
    <label>Nechta son generatsiya qilinsin? <input type="number" id="count" required></label><br>

    <button type="submit">Generatsiya qilish</button>
  </form>

  <h2>Natijalar</h2>
  <div id="output"></div>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  padding: 20px;
}
label {
  display: block;
  margin: 5px 0;
}
document.getElementById('generatorForm').addEventListener('submit', function (e) {
  e.preventDefault();

  const type = document.getElementById('type').value;
  let a = parseInt(document.getElementById('a').value);
  let b = parseInt(document.getElementById('b').value);
  let c = parseInt(document.getElementById('c').value || 0);
  let d = parseInt(document.getElementById('d').value || 0);
  let m = parseInt(document.getElementById('m').value);
  let xn = parseInt(document.getElementById('xn').value);
  let count = parseInt(document.getElementById('count').value);

  const results = [];
  for (let i = 0; i < count; i++) {
    results.push(xn);
    if (type === 'linear') {
      xn = (a * xn + b) % m;
    } else if (type === 'quadratic') {
      xn = (a * xn * xn + b * xn + c) % m;
    } else if (type === 'cubic') {
      xn = (a * xn ** 3 + b * xn ** 2 + c * xn + d) % m;
    }
  }

  document.getElementById('output').textContent = results.join(', ');
});
# Kongruent Generatorlar

Bu veb-ilova chiziqli, kvadratik va kubik kongruent generatorlar asosida psevdotasodifiy ketma-ketliklar generatsiya qiladi.

## Foydalanish
1. Parametrlarni to‘ldiring
2. Generator turini tanlang
3. "Generatsiya qilish" tugmasini bosing
