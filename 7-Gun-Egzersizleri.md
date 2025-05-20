// Fonksiyon Alıştırmaları – Seviye 1

function fullName() {
  console.log('Murat Alpaslan');
}

function fullNameWithParams(firstName, lastName) {
  return `${firstName} ${lastName}`;
}

function addNumbers(a, b) {
  return a + b;
}

function areaOfRectangle(length, width) {
  return length * width;
}

function perimeterOfRectangle(length, width) {
  return 2 * (length + width);
}

function volumeOfRectPrism(length, width, height) {
  return length * width * height;
}

function areaOfCircle(r) {
  return Math.PI * r * r;
}

function circumOfCircle(r) {
  return 2 * Math.PI * r;
}

function density(mass, volume) {
  return mass / volume;
}

function speed(distance, time) {
  return distance / time;
}

function weight(mass, gravity = 9.81) {
  return mass * gravity;
}

function convertCelsiusToFahrenheit(celsius) {
  return (celsius * 9/5) + 32;
}

function bmi(weight, height) {
  const value = weight / (height * height);
  if (value < 18.5) return 'Zayıf';
  else if (value < 25) return 'Normal';
  else if (value < 30) return 'Kilolu';
  else return 'Obez';
}

function checkSeason(month) {
  const lower = month.toLowerCase();
  if (['aralık', 'ocak', 'şubat'].includes(lower)) return 'Kış';
  else if (['mart', 'nisan', 'mayıs'].includes(lower)) return 'İlkbahar';
  else if (['haziran', 'temmuz', 'ağustos'].includes(lower)) return 'Yaz';
  else if (['eylül', 'ekim', 'kasım'].includes(lower)) return 'Sonbahar';
  else return 'Geçersiz ay';
}

function findMax(a, b, c) {
  let max = a;
  if (b > max) max = b;
  if (c > max) max = c;
  return max;
}

// Fonksiyon Alıştırmaları – Seviye 2

function solveLinEquation(a, b, c, x, y) {
  return a * x + b * y + c === 0;
}

function solveQuadratic(a = 1, b = 0, c = 0) {
  const discriminant = b * b - 4 * a * c;
  if (discriminant < 0) return [];
  else if (discriminant === 0) return [-b / (2 * a)];
  else {
    const root1 = (-b + Math.sqrt(discriminant)) / (2 * a);
    const root2 = (-b - Math.sqrt(discriminant)) / (2 * a);
    return [root1, root2];
  }
}

function printArray(arr) {
  arr.forEach(val => console.log(val));
}

function showDateTime() {
  const now = new Date();
  const day = String(now.getDate()).padStart(2, '0');
  const month = String(now.getMonth() + 1).padStart(2, '0');
  const year = now.getFullYear();
  const hour = String(now.getHours()).padStart(2, '0');
  const min = String(now.getMinutes()).padStart(2, '0');
  console.log(`${day}/${month}/${year} ${hour}:${min}`);
}

function swapValues(x, y) {
  return [y, x];
}

function reverseArray(arr) {
  let reversed = [];
  for (let i = arr.length - 1; i >= 0; i--) {
    reversed.push(arr[i]);
  }
  return reversed;
}

function capitalizeArray(arr) {
  return arr.map(item => item.toUpperCase());
}

let globalArray = [];
function addItem(item) {
  globalArray.push(item);
  return globalArray;
}

function removeItem(index) {
  globalArray.splice(index, 1);
  return globalArray;
}

function sumOfNumbers(n) {
  let sum = 0;
  for (let i = 0; i <= n; i++) sum += i;
  return sum;
}

function sumOfOdds(n) {
  let sum = 0;
  for (let i = 0; i <= n; i++) if (i % 2 !== 0) sum += i;
  return sum;
}

function sumOfEven(n) {
  let sum = 0;
  for (let i = 0; i <= n; i++) if (i % 2 === 0) sum += i;
  return sum;
}

function evensAndOdds(n) {
  let evens = 0, odds = 0;
  for (let i = 0; i <= n; i++) {
    if (i % 2 === 0) evens++;
    else odds++;
  }
  console.log(`Çift sayı adedi: ${evens}`);
  console.log(`Tek sayı adedi: ${odds}`);
}

function sum(...args) {
  return args.reduce((acc, cur) => acc + cur, 0);
}

function randomUserIp() {
  return Array(4).fill(0).map(() => Math.floor(Math.random() * 256)).join('.');
}

function randomMacAddress() {
  const hex = '0123456789ABCDEF';
  let mac = '';
  for (let i = 0; i < 6; i++) {
    mac += hex[Math.floor(Math.random() * 16)];
    mac += hex[Math.floor(Math.random() * 16)];
    if (i < 5) mac += ':';
  }
  return mac;
}

function randomHexaNumberGenerator() {
  return '#' + Math.floor(Math.random() * 0xffffff).toString(16).padStart(6, '0');
}

function userIdGenerator() {
  const chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
  let id = '';
  for (let i = 0; i < 7; i++) {
    id += chars[Math.floor(Math.random() * chars.length)];
  }
  return id;
}
// --- Seviye 3 Fonksiyon Alıştırmaları ---

function userIdGeneratedByUser() {
  const charCount = Number(prompt('Kaç karakterli olsun?'));
  const idCount = Number(prompt('Kaç ID üretilecek?'));
  const chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
  for (let i = 0; i < idCount; i++) {
    let id = '';
    for (let j = 0; j < charCount; j++) {
      id += chars[Math.floor(Math.random() * chars.length)];
    }
    console.log(id);
  }
}

function rgbColorGenerator() {
  const r = Math.floor(Math.random() * 256);
  const g = Math.floor(Math.random() * 256);
  const b = Math.floor(Math.random() * 256);
  return `rgb(${r},${g},${b})`;
}

function arrayOfHexaColors(n = 1) {
  const arr = [];
  for (let i = 0; i < n; i++) {
    arr.push(randomHexaNumberGenerator());
  }
  return arr;
}

function arrayOfRgbColors(n = 1) {
  const arr = [];
  for (let i = 0; i < n; i++) {
    arr.push(rgbColorGenerator());
  }
  return arr;
}

function convertHexaToRgb(hex) {
  let r = parseInt(hex.slice(1, 3), 16);
  let g = parseInt(hex.slice(3, 5), 16);
  let b = parseInt(hex.slice(5, 7), 16);
  return `rgb(${r},${g},${b})`;
}

function convertRgbToHexa(r, g, b) {
  return '#' + r.toString(16).padStart(2, '0') +
               g.toString(16).padStart(2, '0') +
               b.toString(16).padStart(2, '0');
}

function generateColors(type, count) {
  if (type === 'hexa') {
    return count === 1 ? randomHexaNumberGenerator() : arrayOfHexaColors(count);
  } else if (type === 'rgb') {
    return count === 1 ? rgbColorGenerator() : arrayOfRgbColors(count);
  } else {
    return 'Desteklenmeyen tür';
  }
}

function shuffleArray(arr) {
  for (let i = arr.length - 1; i > 0; i--) {
    let j = Math.floor(Math.random() * (i + 1));
    [arr[i], arr[j]] = [arr[j], arr[i]];
  }
  return arr;
}

function factorial(n) {
  let result = 1;
  for (let i = 1; i <= n; i++) result *= i;
  return result;
}

function isEmpty(value) {
  return value === undefined || value === null || value === '';
}

function sum(...args) {
  return args.reduce((a, b) => a + b, 0);
}

function sumOfArrayItems(arr) {
  if (!arr.every(item => typeof item === 'number')) return 'Tüm elemanlar sayı olmalı';
  return arr.reduce((a, b) => a + b, 0);
}

function average(arr) {
  if (!arr.every(item => typeof item === 'number')) return 'Tüm elemanlar sayı olmalı';
  return sumOfArrayItems(arr) / arr.length;
}

function modifyArray(arr) {
  if (arr.length < 5) return 'Not Found';
  arr[4] = arr[4].toUpperCase();
  return arr;
}

function isPrime(num) {
  if (num <= 1) return false;
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
}

function areItemsUnique(arr) {
  return new Set(arr).size === arr.length;
}

function areSameDataType(arr) {
  const type = typeof arr[0];
  return arr.every(item => typeof item === type);
}

function isValidVariable(name) {
  return /^[a-zA-Z_$][a-zA-Z0-9_$]*$/.test(name);
}

function sevenRandomNumbers() {
  const nums = new Set();
  while (nums.size < 7) {
    nums.add(Math.floor(Math.random() * 10));
  }
  return Array.from(nums);
}

function reverseCountries(countriesArr) {
  return [...countriesArr].reverse();
}
