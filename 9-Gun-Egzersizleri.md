// forEach: Dizi üzerinde döner ama yeni bir dizi döndürmez
// map: Her elemanı değiştirip yeni bir dizi döndürür
// filter: Belirli şartları sağlayanları alır, yeni dizi döndürür
// reduce: Tüm diziyi tek bir değere indirger (ör: toplam, cümle oluşturma)

const countries = ['Finland', 'Sweden', 'Denmark', 'Norway', 'IceLand'];
const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook'];
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const products = [
  { product: 'banana', price: 3 },
  { product: 'mango', price: 6 },
  { product: 'potato', price: ' ' },
  { product: 'avocado', price: 8 },
  { product: 'coffee', price: 10 },
  { product: 'tea', price: '' },
];

// forEach, map, filter, reduce farkı açıklama üstte verilmişti

// forEach kullanımı
countries.forEach(country => console.log(country));
names.forEach(name => console.log(name));
numbers.forEach(num => console.log(num));

// map kullanımı
const upperCountries = countries.map(c => c.toUpperCase());
console.log(upperCountries);

const countryLengths = countries.map(c => c.length);
console.log(countryLengths);

const squaredNumbers = numbers.map(n => n * n);
console.log(squaredNumbers);

const upperNames = names.map(n => n.toUpperCase());
console.log(upperNames);

const productPrices = products.map(p => p.price);
console.log(productPrices);

// filter kullanımı
const landCountries = countries.filter(c => c.toLowerCase().includes('land'));
console.log(landCountries);

const sixCharCountries = countries.filter(c => c.length === 6);
console.log(sixCharCountries);

const sixOrMoreCharCountries = countries.filter(c => c.length >= 6);
console.log(sixOrMoreCharCountries);

const eCountries = countries.filter(c => c.startsWith('E'));
console.log(eCountries);

const validPrices = products.filter(p => parseFloat(p.price) > 0);
console.log(validPrices);

// getStringLists fonksiyonu
const getStringLists = arr => arr.filter(i => typeof i === 'string');
console.log(getStringLists([1, "Hello", true, "World"]));

// reduce kullanımı
const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum);

const sentence = countries.reduce((acc, cur, index) => {
  if (index === countries.length - 1) return `${acc} and ${cur} are north European countries.`;
  return `${acc}, ${cur}`;
});
console.log(sentence);

// some ve every farkı
console.log(names.some(n => n.length > 7)); // en az biri 7'den uzun mu
console.log(countries.every(c => c.toLowerCase().includes('land'))); // hepsi 'land' içeriyor mu

// find ve findIndex farkı
console.log(countries.find(c => c.length === 6)); // ilk 6 harfli ülke
console.log(countries.findIndex(c => c.length === 6));
console.log(countries.findIndex(c => c === 'Norway'));
console.log(countries.findIndex(c => c === 'Russia'));

// Toplam fiyat (map + filter + reduce)
const totalPrice = products
  .map(p => parseFloat(p.price))
  .filter(price => price > 0)
  .reduce((acc, price) => acc + price, 0);
console.log(totalPrice);

// Sadece reduce ile
const totalPrice2 = products.reduce((acc, p) => {
  const price = parseFloat(p.price);
  return price > 0 ? acc + price : acc;
}, 0);
console.log(totalPrice2);

// categorizeCountries
const categorizeCountries = pattern => countries.filter(c => c.toLowerCase().includes(pattern.toLowerCase()));
console.log(categorizeCountries('land'));
console.log(categorizeCountries('ia'));

// Baş harf istatistiği
const letterStats = countries.reduce((acc, c) => {
  const firstLetter = c[0].toUpperCase();
  acc[firstLetter] = (acc[firstLetter] || 0) + 1;
  return acc;
}, {});
console.log(letterStats);

// İlk 10 ülke
const getFirstTenCountries = arr => arr.slice(0, 10);
console.log(getFirstTenCountries(countries));

// Son 10 ülke
const getLastTenCountries = arr => arr.slice(-10);
console.log(getLastTenCountries(countries));

// En çok kullanılan baş harf
const mostUsedLetter = Object.entries(letterStats).sort((a, b) => b[1] - a[1])[0];
console.log(`En çok kullanılan harf: ${mostUsedLetter[0]} - ${mostUsedLetter[1]} kez`);

const countriesData = [
  { name: 'China', capital: 'Beijing', population: 1377422166, languages: ['Chinese'] },
  { name: 'India', capital: 'New Delhi', population: 1295210000, languages: ['Hindi', 'English'] },
  { name: 'USA', capital: 'Washington D.C.', population: 323947000, languages: ['English'] },
  { name: 'Brazil', capital: 'Brasilia', population: 206135893, languages: ['Portuguese'] },
  { name: 'Nigeria', capital: 'Abuja', population: 186988000, languages: ['English'] },
];

// Ülke, başkent ve nüfus sıralama
console.log(countriesData.sort((a, b) => a.name.localeCompare(b.name)));
console.log(countriesData.sort((a, b) => a.capital.localeCompare(b.capital)));
console.log(countriesData.sort((a, b) => b.population - a.population));

// En çok konuşulan diller
const mostSpokenLanguages = (countries, topN) => {
  const langCount = countries.reduce((acc, c) => {
    c.languages.forEach(lang => acc[lang] = (acc[lang] || 0) + 1);
    return acc;
  }, {});
  return Object.entries(langCount)
    .map(([lang, count]) => ({ country: lang, count }))
    .sort((a, b) => b.count - a.count)
    .slice(0, topN);
};

console.log(mostSpokenLanguages(countriesData, 3));

// En kalabalık ülkeler
const mostPopulatedCountries = (countries, topN) =>
  countries
    .sort((a, b) => b.population - a.population)
    .slice(0, topN)
    .map(c => ({ country: c.name, population: c.population }));

console.log(mostPopulatedCountries(countriesData, 3));

const ages = [31, 26, 34, 37, 27, 26, 32, 32, 26, 27, 27, 24, 32, 33, 27, 25, 26, 38, 37, 31, 34, 24, 33, 29, 26];

const statistics = {
  count: () => ages.length,
  sum: () => ages.reduce((acc, val) => acc + val, 0),
  min: () => Math.min(...ages),
  max: () => Math.max(...ages),
  range: () => statistics.max() - statistics.min(),
  mean: () => Math.round(statistics.sum() / statistics.count()),
  median: () => {
    const sorted = [...ages].sort((a, b) => a - b);
    const mid = Math.floor(sorted.length / 2);
    return sorted.length % 2 === 0
      ? (sorted[mid - 1] + sorted[mid]) / 2
      : sorted[mid];
  },
  mode: () => {
    const freq = {};
    ages.forEach(age => freq[age] = (freq[age] || 0) + 1);
    const maxCount = Math.max(...Object.values(freq));
    const mode = Number(Object.keys(freq).find(key => freq[key] === maxCount));
    return { mode, count: maxCount };
  },
  var: () => {
    const mean = statistics.mean();
    return Math.round(ages.reduce((acc, val) => acc + (val - mean) ** 2, 0) / ages.length);
  },
  std: () => Math.sqrt(statistics.var()).toFixed(1),
  freqDist: () => {
    const freq = {};
    ages.forEach(age => freq[age] = (freq[age] || 0) + 1);
    return Object.entries(freq)
      .map(([age, count]) => [(count / ages.length * 100).toFixed(1), Number(age)])
      .sort((a, b) => b[0] - a[0]);
  },
  describe: () => {
    console.log("Count:", statistics.count());
    console.log("Sum:", statistics.sum());
    console.log("Min:", statistics.min());
    console.log("Max:", statistics.max());
    console.log("Range:", statistics.range());
    console.log("Mean:", statistics.mean());
    console.log("Median:", statistics.median());
    console.log("Mode:", statistics.mode());
    console.log("Variance:", statistics.var());
    console.log("Standard Deviation:", statistics.std());
    console.log("Frequency Distribution:", statistics.freqDist());
  }
};

statistics.describe();
