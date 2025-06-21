<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Supetarya Kayıt</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background: #121212;
    color: #f0f0f0;
    margin: 0; padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
  .container {
    background: #222;
    padding: 20px 30px;
    border-radius: 8px;
    width: 90%;
    max-width: 400px;
    box-shadow: 0 0 15px #900;
  }
  h1, h2 {
    text-align: center;
    color: #ff2020;
  }
  label {
    display: block;
    margin-top: 15px;
    font-weight: bold;
  }
  input, select {
    width: 100%;
    padding: 8px;
    margin-top: 5px;
    border: none;
    border-radius: 4px;
    font-size: 1em;
  }
  button {
    margin-top: 25px;
    width: 100%;
    background: #ff2020;
    color: #fff;
    font-size: 1.1em;
    border: none;
    padding: 12px;
    border-radius: 6px;
    cursor: pointer;
  }
  button:hover {
    background: #e01a1a;
  }
  .hidden {
    display: none;
  }
  .rules {
    background: #330000;
    padding: 15px;
    border-radius: 6px;
    margin-top: 15px;
    color: #ff9999;
    font-weight: bold;
    white-space: pre-line;
  }
  .message {
    text-align: center;
    font-size: 1.3em;
    color: #90ee90;
  }
</style>
</head>
<body>

<div class="container" id="form-container">
  <h1>Supetarya Kayıt</h1>
  <form id="register-form">
    <label for="ad">Adın:</label>
    <input type="text" id="ad" name="ad" required />

    <label for="soyad">Soyadın:</label>
    <input type="text" id="soyad" name="soyad" required />

    <label for="yas">Yaşın:</label>
    <input type="number" id="yas" name="yas" min="1" max="120" required />

    <label for="dogum">Doğum Tarihin:</label>
    <input type="date" id="dogum" name="dogum" required />

    <label for="cinsiyet">Cinsiyetin:</label>
    <select id="cinsiyet" name="cinsiyet" required>
      <option value="" disabled selected>Seçiniz</option>
      <option value="Erkek">Erkek</option>
      <option value="Kadın">Kadın</option>
      <option value="Diğer">Diğer</option>
      <option value="Belirtmek İstemiyorum">Belirtmek İstemiyorum</option>
    </select>

    <label for="ulke">Ülken:</label>
    <input type="text" id="ulke" name="ulke" required />

    <button type="submit">İleri</button>
  </form>
</div>

<div class="container hidden" id="rules-container">
  <h2>Supetarya Kuralları</h2>
  <div class="rules">
    ÖNEMLİ KİŞİLERE KÜFÜR EDEN ATILIR  
    ÖRNEK: KURUCU sP-Yusuf Yönetici  
    SUPETARYA'YA KÜFÜR ETMEK YASAKTIR  
    RASTGELE BİR ÜLKEYE KÜFÜR ETMEK YASAKTIR  
  </div>
  <button id="accept-rules">İleri</button>
</div>

<div class="container hidden" id="welcome-container">
  <h2 class="message">Tebrikler! Supetarya'ya katıldınız!</h2>
</div>

<script>
  const formContainer = document.getElementById('form-container');
  const rulesContainer = document.getElementById('rules-container');
  const welcomeContainer = document.getElementById('welcome-container');

  const registerForm = document.getElementById('register-form');
  const acceptRulesBtn = document.getElementById('accept-rules');

  registerForm.addEventListener('submit', function(e) {
    e.preventDefault();

    // Basit validasyon (formda required zaten var)
    // İstersen burada daha gelişmiş kontrol yapabiliriz

    formContainer.classList.add('hidden');
    rulesContainer.classList.remove('hidden');
  });

  acceptRulesBtn.addEventListener('click', function() {
    rulesContainer.classList.add('hidden');
    welcomeContainer.classList.remove('hidden');
  });
</script>

</body>
</html>
