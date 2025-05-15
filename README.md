
<html lang="uz">
<head>
  <meta charset="UTF-8">
  <title>Kongruent Generatorlar</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background-color: #f7f7f7;
    }
    h1 {
      color: #333;
    }
    label {
      display: block;
      margin: 8px 0 4px;
    }
    input, select, button {
      margin-bottom: 10px;
      padding: 5px;
      font-size: 14px;
    }
    #output {
      margin-top: 15px;
      padding: 10px;
      background-color: #fff;
      border: 1px solid #ccc;
    }
  </style>
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
    </label>

    <label>a: <input type="number" id="a" required></label>
    <label>b: <input type="number" id="b" required></label>
    <label>c: <input type="number" id="c"></label>
    <label>d: <input type="number" id="d"></label>
    <label>m (modul): <input type="number" id="m" required></label>
    <label>xn (boshlang‘ich qiymat): <input type="number" id="xn" required></label>
    <label>Nechta son generatsiya qilinsin? <input type="number" id="count" required></label>

    <button type="submit">Generatsiya qilish</button>
  </form>

  <h2>Natijalar</h2>
  <div id="output"></div>

  <script>
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
  </script>
</body>
</html>
