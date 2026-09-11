# Birinchi-Express-serveringiz-Salomlashuv-API
Loyihani boshlash va paketlarni o'rnatish
Terminalni oching va yangi papka yaratib, uning ichida Node loyihasini ishga tushiring:

Bash
mkdir express-salom-api
cd express-salom-api
npm init -y
Kerakli kutubxonalarni o'rnating (asosiy Express va dev-dependency sifatida nodemon):

Bash
npm install express
npm install -D nodemon
2. package.json faylini sozlash
package.json faylini oching va scripts qismiga dev buyrug'ini qo'shing:

JSON
{
  "name": "express-salom-api",
  "version": "1.0.0",
  "description": "",
  "main": "server.js",
  "scripts": {
    "dev": "nodemon server.js"
  },
  "dependencies": {
    "express": "^4.21.2"
  },
  "devDependencies": {
    "nodemon": "^3.1.9"
  }
}
3. server.js faylini yaratish
Loyiha papkasida server.js nomli fayl yarating va quyidagi kodni yozing:

JavaScript
const express = require('express');
const app = express();
const PORT = 3000;

// Asosiy sahifa - Matnli salom
app.get('/', (req, res) => {
    res.send('Salom, Express serveriga xush kelibsiz!');
});

// About sahifasi - Qisqa tavsif
app.get('/about', (req, res) => {
    res.send('Bu minimal Express routing va API namunasi bo‘lib, matn va JSON formatida javob qaytaradi.');
});

// API user - JSON obyekt qaytarish
app.get('/api/user', (req, res) => {
    res.json({
        ism: 'Alisher',
        yosh: 22,
        kasb: 'Frontend Dasturchi'
    });
});

// Serverni ishga tushirish
app.listen(PORT, () => {
    console.log(`Server muvaffaqiyatli ishga tushdi: http://localhost:${PORT}`);
});
4. Serverni ishga tushirish
Terminalda quyidagi buyruqni kiriting:

Bash
npm run dev
