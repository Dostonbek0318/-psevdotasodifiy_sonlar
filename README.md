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
