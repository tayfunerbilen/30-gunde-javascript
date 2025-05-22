// Egzersiz: Seviye 1

const countries = [
  'Albania', 'Bolivia', 'Canada', 'Denmark', 'Ethiopia',
  'Finland', 'Germany', 'Hungary', 'Ireland', 'Japan', 'Kenya'
];

const webTechs = [
  'HTML', 'CSS', 'JavaScript', 'React', 'Redux', 'Node', 'MongoDB'
];

// 1. Boş bir dizi
let bosDizi = [];

// 2. 5'ten fazla elemanı olan dizi
let sayilar = [1, 2, 3, 4, 5, 6];

// 3. Dizinin uzunluğu
console.log(sayilar.length);

// 4. İlk, orta ve son eleman
console.log(sayilar[0]);
console.log(sayilar[Math.floor(sayilar.length / 2)]);
console.log(sayilar[sayilar.length - 1]);

// 5. mixedDataTypes
let mixedDataTypes = ['Berna', 26, true, null, { job: 'developer' }, [1, 2, 3]];
console.log(mixedDataTypes.length);

// 6. itCompanies dizisi
let itCompanies = ['Facebook', 'Google', 'Microsoft', 'Apple', 'IBM', 'Oracle', 'Amazon'];

// 7. Diziyi yazdır
console.log(itCompanies);

// 8. Şirket sayısı
console.log(itCompanies.length);

// 9. İlk, orta ve son şirket
console.log(itCompanies[0]);
console.log(itCompanies[Math.floor(itCompanies.length / 2)]);
console.log(itCompanies[itCompanies.length - 1]);

// 10. Her şirketi yazdır
itCompanies.forEach(company => console.log(company));

// 11. Büyük harfli yazdır
itCompanies.forEach(company => console.log(company.toUpperCase()));

// 12. Cümle gibi yazdır
console.log(`${itCompanies.slice(0, -1).join(', ')} and ${itCompanies.slice(-1)} are big IT companies.`);

// 13. Şirket kontrolü
let companyToCheck = 'Google';
console.log(itCompanies.includes(companyToCheck) ? companyToCheck : 'Company not found');

// 14. Birden fazla 'o' içeren şirketler
let cokOlu = [];
for (let company of itCompanies) {
  let oSayisi = company.toLowerCase().split('o').length - 1;
  if (oSayisi > 1) cokOlu.push(company);
}
console.log(cokOlu);

// 15. Alfabetik sırala
console.log([...itCompanies].sort());

// 16. Ters çevir
console.log([...itCompanies].reverse());

// 17. İlk 3 şirketi dilimle
console.log(itCompanies.slice(0, 3));

// 18. Son 3 şirketi dilimle
console.log(itCompanies.slice(-3));

// 19. Ortadaki şirket(ler)
let ortanca = Math.floor(itCompanies.length / 2);
console.log(itCompanies.length % 2 === 0 ? itCompanies.slice(ortanca - 1, ortanca + 1) : itCompanies[ortanca]);

// 20. İlk şirketi sil
itCompanies.shift();

// 21. Ortadaki şirketi sil
let ortancaIndex = Math.floor(itCompanies.length / 2);
itCompanies.splice(ortancaIndex, 1);

// 22. Son şirketi sil
itCompanies.pop();

// 23. Tüm şirketleri sil
itCompanies = [];

// Egzersiz: Seviye 2

// 1. Ayrı dosyalara aktarma (örnek)
// countries.js -> module.exports = [...];
// web_techs.js -> module.exports = [...];
// main.js -> const countries = require('./countries');
//            const webTechs = require('./web_techs');

// 2. Noktalama işaretlerini kaldır ve kelimeleri say
let text = 'I love teaching and empowering people. I teach HTML, CSS, JS, React, Python.';
let words = text.replace(/[.,]/g, '').split(' ');
console.log(words);
console.log(words.length);

// 3. Alışveriş sepeti işlemleri
let shoppingCart = ['Milk', 'Coffee', 'Tea', 'Honey'];

if (!shoppingCart.includes('Meat')) shoppingCart.unshift('Meat');
if (!shoppingCart.includes('Sugar')) shoppingCart.push('Sugar');

let alerjiVar = true;
if (alerjiVar && shoppingCart.includes('Honey')) {
  shoppingCart.splice(shoppingCart.indexOf('Honey'), 1);
}

shoppingCart[shoppingCart.indexOf('Tea')] = 'Green Tea';
console.log(shoppingCart);

// 4. Ethiopia kontrolü
if (countries.includes('Ethiopia')) {
  console.log('ETHIOPIA');
} else {
  countries.push('Ethiopia');
}

// 5. Sass kontrolü
if (webTechs.includes('Sass')) {
  console.log('Sass is a CSS preprocess');
} else {
  webTechs.push('Sass');
  console.log(webTechs);
}

// 6. fullStack dizisi
const frontEnd = ['HTML', 'CSS', 'JS', 'React', 'Redux'];
const backEnd = ['Node', 'Express', 'MongoDB'];
const fullStack = frontEnd.concat(backEnd);
console.log(fullStack);

// Egzersiz: Seviye 3

const ages = [19, 22, 19, 24, 20, 25, 26, 24, 25, 24];

ages.sort((a, b) => a - b);
const minAge = ages[0];
const maxAge = ages[ages.length - 1];
console.log('En küçük:', minAge, 'En büyük:', maxAge);

// Medyan hesaplama
let medyan;
if (ages.length % 2 === 0) {
  medyan = (ages[ages.length / 2 - 1] + ages[ages.length / 2]) / 2;
} else {
  medyan = ages[Math.floor(ages.length / 2)];
}
console.log('Medyan:', medyan);

// Ortalama yaş
let toplam = ages.reduce((acc, val) => acc + val, 0);
let ortalama = toplam / ages.length;
console.log('Ortalama:', ortalama);

// Aralık
let yasAraligi = maxAge - minAge;
console.log('Aralık:', yasAraligi);

// abs karşılaştırma
console.log('Min - Ortalama:', Math.abs(minAge - ortalama));
console.log('Max - Ortalama:', Math.abs(maxAge - ortalama));

// İlk 10 ülke
console.log('İlk 10 ülke:', countries.slice(0, 10));

// Ortadaki ülke(ler)
let ortancaUlke;
if (countries.length % 2 === 0) {
  ortancaUlke = countries.slice(countries.length / 2 - 1, countries.length / 2 + 1);
} else {
  ortancaUlke = countries[Math.floor(countries.length / 2)];
}
console.log('Ortadaki ülke(ler):', ortancaUlke);

// Ülkeleri ikiye böl
let ilkYari, ikinciYari;
let bolumNoktasi = Math.ceil(countries.length / 2);
ilkYari = countries.slice(0, bolumNoktasi);
ikinciYari = countries.slice(bolumNoktasi);
console.log('İlk Yarı:', ilkYari);
console.log('İkinci Yarı:', ikinciYari);
