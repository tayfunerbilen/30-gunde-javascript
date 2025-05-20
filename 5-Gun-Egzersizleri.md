// Exercise: Level 1

const countries = [
  'Albania',
  'Bolivia',
  'Canada',
  'Denmark',
  'Ethiopia',
  'Finland',
  'Germany',
  'Hungary',
  'Ireland',
  'Japan',
  'Kenya'
];

const webTechs = [
  'HTML',
  'CSS',
  'JavaScript',
  'React',
  'Redux',
  'Node',
  'MongoDB'
];

// 1. Declare an empty array:
let emptyArray = [];

// 2. Declare an array with more than 5 elements:
let numbers = [1, 2, 3, 4, 5, 6];

// 3. Find the length of your array:
console.log(numbers.length);

// 4. Get the first, middle, and last item:
console.log(numbers[0]);
console.log(numbers[Math.floor(numbers.length / 2)]);
console.log(numbers[numbers.length - 1]);

// 5. Declare mixedDataTypes:
let mixedDataTypes = ['Berna', 26, true, null, { job: 'developer' }, [1, 2, 3]];
console.log(mixedDataTypes.length);

// 6. Declare itCompanies array:
let itCompanies = ['Facebook', 'Google', 'Microsoft', 'Apple', 'IBM', 'Oracle', 'Amazon'];

// 7. Print array:
console.log(itCompanies);

// 8. Print number of companies:
console.log(itCompanies.length);

// 9. Print first, middle and last company:
console.log(itCompanies[0]);
console.log(itCompanies[Math.floor(itCompanies.length / 2)]);
console.log(itCompanies[itCompanies.length - 1]);

// 10. Print each company:
itCompanies.forEach(company => console.log(company));

// 11. Uppercase each:
itCompanies.forEach(company => console.log(company.toUpperCase()));

// 12. Sentence format:
console.log(`${itCompanies.slice(0, -1).join(', ')} and ${itCompanies.slice(-1)} are big IT companies.`);

// 13. Check if a company exists:
let companyToCheck = 'Google';
console.log(itCompanies.includes(companyToCheck) ? companyToCheck : 'Company not found');

// 14. Filter companies with more than one 'o':
let manyOs = [];
for (let company of itCompanies) {
  let count = company.toLowerCase().split('o').length - 1;
  if (count > 1) manyOs.push(company);
}
console.log(manyOs);

// 15. Sort the array:
console.log([...itCompanies].sort());

// 16. Reverse the array:
console.log([...itCompanies].reverse());

// 17. Slice out first 3:
console.log(itCompanies.slice(0, 3));

// 18. Slice out last 3:
console.log(itCompanies.slice(-3));

// 19. Slice out the middle company:
let mid = Math.floor(itCompanies.length / 2);
console.log(itCompanies.length % 2 === 0 ? itCompanies.slice(mid - 1, mid + 1) : itCompanies[mid]);

// 20. Remove the first company:
itCompanies.shift();

// 21. Remove middle company:
let midIndex = Math.floor(itCompanies.length / 2);
itCompanies.splice(midIndex, 1);

// 22. Remove the last company:
itCompanies.pop();

// 23. Remove all companies:
itCompanies = [];

// Exercise: Level 2

// 1. Separate countries and webTechs into modules (varsayım: tarayıcı ortamında değil Node ortamında çalışılıyor):
// Dosya: countries.js
module.exports = [ 'Albania', 'Bolivia', ... ];

// Dosya: web_techs.js
module.exports = [ 'HTML', 'CSS', ... ];

// Dosya: main.js
const countries = require('./countries');
const webTechs = require('./web_techs');

// 2. Remove punctuation and count words:
let text = 'I love teaching and empowering people. I teach HTML, CSS, JS, React, Python.';
let words = text.replace(/[.,]/g, '').split(' ');
console.log(words);
console.log(words.length); // 13

// 3. Shopping cart operations:
let shoppingCart = ['Milk', 'Coffee', 'Tea', 'Honey'];

if (!shoppingCart.includes('Meat')) shoppingCart.unshift('Meat');
if (!shoppingCart.includes('Sugar')) shoppingCart.push('Sugar');

// allergic to honey:
let allergicToHoney = true;
if (allergicToHoney && shoppingCart.includes('Honey')) {
  shoppingCart.splice(shoppingCart.indexOf('Honey'), 1);
}

shoppingCart[shoppingCart.indexOf('Tea')] = 'Green Tea';
console.log(shoppingCart);

// 4. Check for Ethiopia
if (countries.includes('Ethiopia')) {
  console.log('ETHIOPIA');
} else {
  countries.push('Ethiopia');
}

// 5. Check for Sass
if (webTechs.includes('Sass')) {
  console.log('Sass is a CSS preprocess');
} else {
  webTechs.push('Sass');
  console.log(webTechs);
}

// 6. Concatenate frontend and backend
const frontEnd = ['HTML', 'CSS', 'JS', 'React', 'Redux'];
const backEnd = ['Node', 'Express', 'MongoDB'];
const fullStack = frontEnd.concat(backEnd);
console.log(fullStack);

// Exercise: Level 3
const ages = [19, 22, 19, 24, 20, 25, 26, 24, 25, 24];

// 1. Sort, min, max
ages.sort((a, b) => a - b);
const minAge = ages[0];
const maxAge = ages[ages.length - 1];
console.log('Min:', minAge, 'Max:', maxAge);

// 2. Median
let medianAge;
if (ages.length % 2 === 0) {
  medianAge = (ages[ages.length / 2 - 1] + ages[ages.length / 2]) / 2;
} else {
  medianAge = ages[Math.floor(ages.length / 2)];
}
console.log('Median:', medianAge);

// 3. Average
let sum = ages.reduce((acc, val) => acc + val, 0);
let average = sum / ages.length;
console.log('Average:', average);

// 4. Range
let range = maxAge - minAge;
console.log('Range:', range);

// 5. Compare (min - avg) and (max - avg)
console.log('Min-Average Diff:', Math.abs(minAge - average));
console.log('Max-Average Diff:', Math.abs(maxAge - average));

// 6. First ten countries
console.log('First ten countries:', countries.slice(0, 10));

// 7. Middle country
let middleCountry;
if (countries.length % 2 === 0) {
  middleCountry = countries.slice(countries.length / 2 - 1, countries.length / 2 + 1);
} else {
  middleCountry = countries[Math.floor(countries.length / 2)];
}
console.log('Middle Country:', middleCountry);

// 8. Divide countries array in two
let firstHalf, secondHalf;
let half = Math.ceil(countries.length / 2);
firstHalf = countries.slice(0, half);
secondHalf = countries.slice(half);
console.log('First Half:', firstHalf);
console.log('Second Half:', secondHalf);

