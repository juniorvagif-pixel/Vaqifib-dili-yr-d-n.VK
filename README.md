<!DOCTYPE html>
<html lang="az">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vaqifib Sözlük</title>
<style>
  body {
    font-family: Arial, sans-serif;
    text-align: center;
    background: linear-gradient(120deg, #7cb8ff, #9ee0ff);
    margin: 0;
    padding: 0;
  }
  h1 {
    margin-top: 20px;
    font-size: 28px;
    color: #004d80;
  }
  button {
    width: 80%;
    max-width: 300px;
    padding: 12px;
    margin: 8px;
    font-size: 16px;
    border: none;
    border-radius: 10px;
    background-color: #0077cc;
    color: white;
    cursor: pointer;
    transition: 0.2s;
  }
  button:hover {
    background-color: #005fa3;
  }
  textarea {
    width: 90%;
    height: 300px;
    margin-top: 10px;
    font-size: 15px;
    padding: 10px;
    resize: none;
  }
</style>
</head>
<body>
  <h1>=== Vaqifib Sözlük ===</h1>

  <button onclick="translateWord()">1. Söz tərcümə et</button><br>
  <button onclick="testWord()">2. Test et</button><br>
  <button onclick="showAllWords()">3. Bütün sözləri göstər</button><br>
  <button onclick="exitProgram()">4. Çıxış</button>

  <div id="output"></div>

<script>
const dictionary = {
  "it": "xafu", "pişik": "nelo", "at": "zume", "inək": "mugu",
  "qoyun": "dare", "keçi": "seka", "toyuq": "gafu", "xoruz": "rafu",
  "ördək": "duna", "balıq": "kifi", "quş": "lavu", "aslan": "ragon",
  "pələng": "tavun", "fil": "gomu", "ayı": "murga", "canavar": "xavul",
  "tülkü": "fesko", "dovşan": "nibu", "siçan": "tikur", "ilan": "hisi",
  "maral": "velin",
  "salam": "sişa", "xudafiz": "tişa", "necəsən?": "yezi?", "yaxşıyam": "pife",
  "mən": "qami", "sən": "jiqa", "o": "pina",
  "öyrən": "eyji", "öyrənmək": "eyjiti", "oxumaq": "namiti", "iş": "vuc",
  "işlə": "vucve", "işləmək": "vucveti", "yat": "əraf", "yatmaq": "ərafti",
  "lüğət": "bado", "şəxs": "geba", "konsol": "aba",
  "maq²": "ti", "la²": "ve", "am²": "fe", "san²": "zi", "dır⁴": "la", "iq⁴": "ci",
  "1": "taf", "2": "ucsi", "3": "viy", "4": "zol", "5": "ələf",
  "6": "ziy", "7": "uciyla", "8": "yeş", "9": "fena", "0": "şşexi"
};

function translateWord() {
  const word = prompt("Azərbaycan dilində söz yaz:")?.trim().toLowerCase();
  if (!word) return;
  if (dictionary[word]) {
    alert(`${word} → ${dictionary[word]}`);
  } else {
    alert("Bu söz hələ əlavə olunmayıb!");
  }
}

function testWord() {
  const keys = Object.keys(dictionary);
  const randomKey = keys[Math.floor(Math.random() * keys.length)];
  const answer = prompt(`${randomKey} Vaqifibcə nədir?`)?.trim().toLowerCase();
  if (answer === null) return;
  const correct = dictionary[randomKey].toLowerCase();
  if (answer === correct) {
    alert("✅ Düzdür!");
  } else {
    alert(`❌ Yanlış! Düzgün cavab: ${correct}`);
  }
}

function showAllWords() {
  const allWords = Object.entries(dictionary)
    .map(([az, vq]) => `${az} → ${vq}`)
    .join("\n");
  const newWindow = window.open("", "_blank", "width=400,height=500,scrollbars=yes");
  newWindow.document.write(`<pre style="font-size:16px">${allWords}</pre>`);
}

function exitProgram() {
  if (confirm("Proqramdan çıxmaq istəyirsən?")) {
    window.close();
  }
}
</script>
</body>
</html>
