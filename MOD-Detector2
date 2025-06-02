<!DOCTYPE html><html lang="tr"><head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MOD-Detector</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #0e1e2e;
      color: white;
    }
    header {
      background-color: #1e3a5f;
      padding: 20px;
      text-align: center;
    }
    h1 {
      margin: 0;
      font-size: 1.8em;
    }
    .container {
      padding: 20px;
      max-width: 600px;
      margin: auto;
    }
    .input-section {
      background-color: #1c2f45;
      padding: 20px;
      border-radius: 10px;
      margin-bottom: 20px;
    }
    label {
      display: block;
      margin-bottom: 8px;
    }
    input, select {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border: none;
      border-radius: 5px;
      font-size: 1em;
    }
    button {
      width: 100%;
      padding: 12px;
      background-color: #406080;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 1em;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    button:hover {
      background-color: #2e4a6f;
    }
    .result {
      background-color: #1c2f45;
      padding: 20px;
      border-radius: 10px;
    }
    .footer {
      text-align: center;
      padding: 20px;
      font-size: 0.9em;
      color: #bbb;
    }
  </style>
</head><body>
  <header>
    <h1>MOD-Detector 2.0</h1>
  </header>
  <div class="container">
    <p style="text-align: justify;">
      Bu uygulama, daha önceden kuralları bilinen 2, 3, 4, 5, 6, 9 ve 10 sayılarının yanı sıra Matematik Öğretmeni Ahmet ÖZDURAN ve öğrencisi Enes ÖZGEN tarafından Tübitak 2204-B Ortaokul Öğrencileri Araştırma Projeleri Yarışması kapsamında geliştirilen 79, 83, 89 ve 97 sayıları için bölünebilme kurallarını içeren bir hesaplama aracıdır.
    </p>
    <div class="input-section">
      <label for="number">Sayıyı girin:</label>
      <input type="number" id="number" placeholder="Örneğin: 1264">
      <label for="divisor">Hangi sayıya bölünebildiğini kontrol etmek istiyorsunuz?</label>
      <select id="divisor">
        <option value="2">2</option>
        <option value="3">3</option>
        <option value="4">4</option>
        <option value="5">5</option>
        <option value="6">6</option>
        <option value="9">9</option>
        <option value="10">10</option>
        <option value="79">79</option>
        <option value="83">83</option>
        <option value="89">89</option>
        <option value="97">97</option>
      </select>
      <button onclick="checkDivisibility()">Kontrol Et</button>
    </div>
    <div class="result" id="result"></div>
  </div>
  <div class="footer">
    MOD-Detector © 2025 Fatsa Bahçeşehir Bilim Şenliği
  </div>  <script>
    function checkDivisibility() {
      const number = parseInt(document.getElementById("number").value);
      const divisor = parseInt(document.getElementById("divisor").value);
      const resultDiv = document.getElementById("result");
      resultDiv.innerHTML = "";

      if (isNaN(number)) {
        resultDiv.innerHTML = "Lütfen geçerli bir sayı girin.";
        return;
      }

      let isDivisible = number % divisor === 0;
      let steps = [];
      let explanation = "";
      let rule = "";

      if ([2, 3, 4, 5, 6, 9, 10].includes(divisor)) {
        rule = `Kural: ${divisor} sayısı için klasik bölünebilme kuralları uygulanır.`;
        switch (divisor) {
          case 2:
            explanation = "Bir sayının 2 ile bölünebilmesi için son basamağı çift olmalıdır.";
            break;
          case 3:
            explanation = "Rakamları toplamı 3'ün katı olan sayılar 3 ile tam bölünür.";
            break;
          case 4:
            explanation = "Son iki basamağı 4 ile bölünebilen sayılar 4'e tam bölünür.";
            break;
          case 5:
            explanation = "Son basamağı 0 veya 5 olan sayılar 5 ile tam bölünür.";
            break;
          case 6:
            explanation = "Hem 2 hem de 3 ile tam bölünen sayılar 6 ile de tam bölünür.";
            break;
          case 9:
            explanation = "Rakamları toplamı 9'un katı olan sayılar 9 ile tam bölünür.";
            break;
          case 10:
            explanation = "Son basamağı 0 olan sayılar 10 ile tam bölünür.";
            break;
        }
      } else {
        switch (divisor) {
          case 79:
            rule = "Kural: Son basamak 8 ile çarpılır ve kalan sayıya eklenir. 79 elde edilirse tam bölünür.";
            let temp79 = number;
            for (let i = 0; i < 20; i++) {
              let d = temp79 % 10;
              let rest = Math.floor(temp79 / 10);
              let add = d * 8;
              steps.push(`${d} × 8 = ${add}; ${add} + ${rest} = ${add + rest}`);
              temp79 = add + rest;
              if (temp79 === 79) {
                isDivisible = true;
                break;
              }
              if (temp79 < 100 && temp79 !== 79) {
                isDivisible = false;
                break;
              }
            }
            explanation = isDivisible ? "Sayı 79 elde edildiği için tam bölünür." : "79 elde edilemediği için tam bölünemez.";
            break;
          case 83:
            rule = "Kural: Son basamak 25 ile çarpılır ve kalan sayıya eklenir. 83 veya 166 elde edilirse tam bölünür.";
            let temp83 = number;
            for (let i = 0; i < 20; i++) {
              let d = temp83 % 10;
              let rest = Math.floor(temp83 / 10);
              let add = d * 25;
              steps.push(`${d} × 25 = ${add}; ${add} + ${rest} = ${add + rest}`);
              temp83 = add + rest;
              if (temp83 === 83 || temp83 === 166) {
                isDivisible = true;
                break;
              }
              if (temp83 < 100 && temp83 !== 83 && temp83 !== 166) {
                isDivisible = false;
                break;
              }
            }
            explanation = isDivisible ? "Sayı 83 veya 166 elde edildiği için tam bölünür." : "83 ya da 166 elde edilemediği için tam bölünemez.";
            break;
          case 89:
            rule = "Kural: Son basamak 9 ile çarpılır ve kalan sayıya eklenir. 89 elde edilirse tam bölünür.";
            let temp89 = number;
            for (let i = 0; i < 20; i++) {
              let d = temp89 % 10;
              let rest = Math.floor(temp89 / 10);
              let add = d * 9;
              steps.push(`${d} × 9 = ${add}; ${add} + ${rest} = ${add + rest}`);
              temp89 = add + rest;
              if (temp89 === 89) {
                isDivisible = true;
                break;
              }
              if (temp89 < 100 && temp89 !== 89) {
                isDivisible = false;
                break;
              }
            }
            explanation = isDivisible ? "Sayı 89 elde edildiği için tam bölünür." : "89 elde edilemediği için tam bölünemez.";
            break;
          case 97:
            rule = "Kural: Son iki basamak hariç kısım 3 ile çarpılır ve son iki basamağa eklenir. 97 elde edilirse tam bölünür.";
            let temp97 = number;
            for (let i = 0; i < 20; i++) {
              let rest = Math.floor(temp97 / 100);
              let last2 = temp97 % 100;
              let add = rest * 3;
              steps.push(`${rest} × 3 = ${add}; ${add} + ${last2} = ${add + last2}`);
              temp97 = add + last2;
              if (temp97 === 97) {
                isDivisible = true;
                break;
              }
              if (temp97 < 100 && temp97 !== 97) {
                isDivisible = false;
                break;
              }
            }
            explanation = isDivisible ? "Sayı 97 elde edildiği için tam bölünür." : "97 elde edilemediği için tam bölünemez.";
            break;
        }
      }

      resultDiv.innerHTML = `
        <h3>${isDivisible ? "✔ Evet, tam bölünür." : "❌ Hayır, tam bölünmez."}</h3>
        <p><strong>${rule}</strong></p>
        <p>${explanation}</p>
        ${steps.length > 0 ? `<details><summary>İşlem Adımları</summary><ul>${steps.map(s => `<li>${s}</li>`).join('')}</ul></details>` : ""}
      `;
    }
  </script></body></html>
