/*
# Seviye 1 - Nesne Alıştırmaları
*/

// 1. Boş bir dog (köpek) nesnesi oluşturun
const dog = {};

// 2. dog nesnesini konsola yazdırın
console.log(dog);

// 3. dog nesnesine name, legs, color, age ve bark özellikleri ekleyin. 
// bark özelliği 'woof woof' dönen bir metot olmalı
dog.name = "Karabas";
dog.legs = 4;
dog.color = "kahverengi";
dog.age = 3;
dog.bark = function() {
  return "hav hav";
};

// 4. dog nesnesinden name, legs, color, age ve bark değerlerini alın
console.log(dog.name);      // Karabas
console.log(dog.legs);      // 4
console.log(dog.color);     // kahverengi
console.log(dog.age);       // 3
console.log(dog.bark());    // hav hav

// 5. dog nesnesine yeni özellikler ekleyin: breed ve getDogInfo
// getDogInfo, köpekle ilgili açıklayıcı bir bilgi döndürsün
dog.breed = "Golden Retriever";
dog.getDogInfo = function() {
  return `${this.name}, ${this.age} yaşında bir ${this.breed}. ${this.legs} bacağı var ve '${this.bark()}' diye havlıyor.`;
};

console.log(dog.getDogInfo());


/*
# Seviye 2 - Kullanıcı Nesnesi Üzerinde İşlemler
*/

const users = {
  Alex: {
    email: 'alex@alex.com',
    skills: ['HTML', 'CSS', 'JavaScript'],
    age: 20,
    isLoggedIn: false,
    points: 30
  },
  Asab: {
    email: 'asab@asab.com',
    skills: ['HTML', 'CSS', 'JavaScript', 'Redux', 'MongoDB', 'Express', 'React', 'Node'],
    age: 25,
    isLoggedIn: false,
    points: 50
  },
  Brook: {
    email: 'daniel@daniel.com',
    skills: ['HTML', 'CSS', 'JavaScript', 'React', 'Redux'],
    age: 30,
    isLoggedIn: true,
    points: 50
  },
  Daniel: {
    email: 'daniel@alex.com',
    skills: ['HTML', 'CSS', 'JavaScript', 'Python'],
    age: 20,
    isLoggedIn: false,
    points: 40
  },
  John: {
    email: 'john@john.com',
    skills: ['HTML', 'CSS', 'JavaScript', 'React', 'Redux', 'Node.js'],
    age: 20,
    isLoggedIn: true,
    points: 50
  },
  Thomas: {
    email: 'thomas@thomas.com',
    skills: ['HTML', 'CSS', 'JavaScript', 'React'],
    age: 20,
    isLoggedIn: false,
    points: 40
  },
  Paul: {
    email: 'paul@paul.com',
    skills: ['HTML', 'CSS', 'JavaScript', 'MongoDB', 'Express', 'React', 'Node'],
    age: 20,
    isLoggedIn: false,
    points: 40
  }
};

// 1. En çok beceriye (skills) sahip kullanıcıyı bulun
let mostSkilledUser = '';
let maxSkills = 0;

for (const user in users) {
  if (users[user].skills.length > maxSkills) {
    maxSkills = users[user].skills.length;
    mostSkilledUser = user;
  }
}

console.log("En çok beceriye sahip kullanıcı:", mostSkilledUser);

// 2. Giriş yapmış kullanıcıları ve 50'den fazla puanı olanları sayın
let loggedInCount = 0;
let highPointsCount = 0;

for (const user in users) {
  if (users[user].isLoggedIn) loggedInCount++;
  if (users[user].points >= 50) highPointsCount++;
}

console.log("Giriş yapmış kullanıcı sayısı:", loggedInCount);
console.log("50 veya daha fazla puanı olan kullanıcı sayısı:", highPointsCount);

// 3. MERN stack geliştiricilerini bulun (MongoDB, Express, React, Node içerenler)
let mernUsers = [];

for (const user in users) {
  const skills = users[user].skills;
  if (['MongoDB', 'Express', 'React', 'Node'].every(skill => skills.includes(skill))) {
    mernUsers.push(user);
  }
}

console.log("MERN stack geliştiricileri:", mernUsers);

// 4. Orijinal nesneyi bozmadan kendi kullanıcı adınızı ekleyin
const newUsers = { ...users };
newUsers.Golge = {
  email: 'golge@darkmail.com',
  skills: ['JavaScript', 'Node.js'],
  age: 31,
  isLoggedIn: true,
  points: 45
};

console.log("Yeni kullanıcı eklendi:", newUsers.Golge);

// 5. users nesnesinin tüm anahtarlarını alın
console.log("Kullanıcı isimleri:", Object.keys(users));

// 6. users nesnesinin tüm değerlerini alın
console.log("Tüm kullanıcı verileri:", Object.values(users));

/*
# Seviye 3 - Fonksiyonel Nesne ve Kullanıcı İşlemleri
*/

// 1. Kişisel bir hesap nesnesi oluşturun
totalIncome = 0;
totalExpense = 0;

const personAccount = {
  firstName: "Gölge",
  lastName: "Kodcu",
  incomes: [
    { amount: 3000, description: "Maaş" },
    { amount: 500, description: "Freelance" }
  ],
  expenses: [
    { amount: 1000, description: "Kira" },
    { amount: 300, description: "Faturalar" }
  ],
  totalIncome() {
    return this.incomes.reduce((sum, item) => sum + item.amount, 0);
  },
  totalExpense() {
    return this.expenses.reduce((sum, item) => sum + item.amount, 0);
  },
  accountInfo() {
    return `${this.firstName} ${this.lastName}`;
  },
  addIncome(amount, description) {
    this.incomes.push({ amount, description });
  },
  addExpense(amount, description) {
    this.expenses.push({ amount, description });
  },
  accountBalance() {
    return this.totalIncome() - this.totalExpense();
  }
};

console.log("Hesap Bilgisi:", personAccount.accountInfo());
console.log("Toplam Gelir:", personAccount.totalIncome());
console.log("Toplam Gider:", personAccount.totalExpense());
console.log("Bakiye:", personAccount.accountBalance());