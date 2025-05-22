// Alıştırma - Pratik: 6. Gün

const countries = [
  'Albania', 'Bolivia', 'Canada', 'Denmark', 'Ethiopia',
  'Finland', 'Germany', 'Hungary', 'Ireland', 'Japan', 'Kenya'
];

const webTechs = [
  'HTML', 'CSS', 'JavaScript', 'React', 'Redux', 'Node', 'MongoDB'
];

const mernStack = ['MongoDB', 'Express', 'React', 'Node'];

// while ve do while ile 0'dan 10'a
let i = 0;
while (i <= 10) {
  console.log(i);
  i++;
}

i = 0;
do {
  console.log(i);
  i++;
} while (i <= 10);

// while ve do while ile 10'dan 0'a
let j = 10;
while (j >= 0) {
  console.log(j);
  j--;
}

j = 10;
do {
  console.log(j);
  j--;
} while (j >= 0);

// 0'dan n'e kadar for döngüsü (örnek olarak n = 10)
let n = 10;
for (let i = 0; i <= n; i++) {
  console.log(i);
}

// # desenli çıktı
let desen = '';
for (let i = 1; i <= 7; i++) {
  desen += '#';
  console.log(desen);
}

// x x = x çıktı
for (let i = 0; i <= 10; i++) {
  console.log(`${i} x ${i} = ${i * i}`);
}

// i, i^2, i^3 tablosu
console.log('i    i^2    i^3');
for (let i = 0; i <= 10; i++) {
  console.log(`${i}    ${i ** 2}    ${i ** 3}`);
}

// Çift sayılar
for (let i = 0; i <= 100; i++) {
  if (i % 2 === 0) console.log(i);
}

// Tek sayılar
for (let i = 0; i <= 100; i++) {
  if (i % 2 !== 0) console.log(i);
}

// Asal sayılar
for (let num = 2; num <= 100; num++) {
  let asal = true;
  for (let d = 2; d <= Math.sqrt(num); d++) {
    if (num % d === 0) {
      asal = false;
      break;
    }
  }
  if (asal) console.log(num);
}

// Toplam
let toplam = 0;
for (let i = 0; i <= 100; i++) {
  toplam += i;
}
console.log('Toplam:', toplam);

// Tek ve çift sayıların toplamı
let tekToplam = 0;
let ciftToplam = 0;
for (let i = 0; i <= 100; i++) {
  i % 2 === 0 ? ciftToplam += i : tekToplam += i;
}
console.log('Çift sayıların toplamı:', ciftToplam);
console.log('Tek sayıların toplamı:', tekToplam);

// Pratik: 2. Seviye

// Rastgele ID
function randomId(length = 12) {
  const chars = 'abcdefghijklmnopqrstuvwxyz0123456789';
  let result = '';
  for (let i = 0; i < length; i++) {
    result += chars[Math.floor(Math.random() * chars.length)];
  }
  return result;
}
console.log(randomId());

// Rastgele hexadecimal
function randomHex() {
  const chars = '0123456789abcdef';
  let hex = '#';
  for (let i = 0; i < 6; i++) {
    hex += chars[Math.floor(Math.random() * chars.length)];
  }
  return hex;
}
console.log(randomHex());

// Rastgele RGB
function randomRgb() {
  let r = Math.floor(Math.random() * 256);
  let g = Math.floor(Math.random() * 256);
  let b = Math.floor(Math.random() * 256);
  return `rgb(${r},${g},${b})`;
}
console.log(randomRgb());

// Rastgele yeni ülkeler dizisi
const randomCountries = [...countries].sort(() => 0.5 - Math.random());
console.log(randomCountries);

// Ülke uzunlukları
const countryLengths = countries.map(country => country.length);
console.log(countryLengths);

// ['Ülke', 'KIS', uzunluk]
const detailedCountries = countries.map(c => [c, c.slice(0, 3).toUpperCase(), c.length]);
console.log(detailedCountries);

// 'land' içeren ülkeler
const landCountries = countries.filter(c => c.toLowerCase().includes('land'));
console.log(landCountries);

// 'ia' içeren ülkeler
const iaCountries = countries.filter(c => c.toLowerCase().includes('ia'));
console.log(iaCountries);

// En uzun ülke
const longestCountry = countries.reduce((a, b) => a.length > b.length ? a : b);
console.log(longestCountry);

// 5 harfli ülkeler
const fiveCharCountries = countries.filter(c => c.length === 5);
console.log(fiveCharCountries);

// Pratik: 3. Seviye

// Diziyi kopyala ve sırala
const sortedCountries = [...countries].sort();
console.log(sortedCountries);

// WebTechs ve MernStack sıralama
console.log([...webTechs].sort());
console.log([...mernStack].sort());

// 'land' ile biten ülkeler
const landEndCountries = countries.filter(c => c.endsWith('land'));
console.log(landEndCountries);

// En uzun ülke tekrar
const enUzun = countries.reduce((a, b) => a.length > b.length ? a : b);
console.log(enUzun);

// 4 harfli ülkeler
const dortHarfli = countries.filter(c => c.length === 4);
console.log(dortHarfli);

// 2+ kelimeli ülkeler (örnek için boş, varsa eklenebilir)
const cokKelime = countries.filter(c => c.split(' ').length > 1);
console.log(cokKelime);

// Ters çevir, büyük yap
const tersBuyuk = [...countries].reverse().map(c => c.toUpperCase());
console.log(tersBuyuk);
