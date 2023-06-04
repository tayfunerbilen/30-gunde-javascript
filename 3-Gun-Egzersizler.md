# 3. Gün Egzersizleri

## Egzersiz: Seviye 1

1. `firstName`, `lastName`, `country`, `city`, `age`, `isMarried`, `year` isimli değişkenleri tanımlayın ve bunlara değer atayın. Daha sonra `typeof` operatörünü kullanarak farklı veri tiplerini kontrol edin.

```js
let firstName = "Ahmet";
let lastName = "Yılmaz";
let country = "TR";
let city = "İstanbul";
let age = 30;
let isMarried = true;
let year = 2023;

console.log(typeof firstName);  // string
console.log(typeof lastName);   // string
console.log(typeof country);    // string
console.log(typeof city);       // string
console.log(typeof age);        // number
console.log(typeof isMarried);  // boolean
console.log(typeof year);       // number
```

2. '10' tipinin 10'a eşit olup olmadığını kontrol edin.

```js
console.log(typeof '10' === typeof 10); // false
```

3. `parseInt('9.8')`'in 10'a eşit olup olmadığını kontrol edin.

```js
console.log(parseInt('9.8') === 10); // false
```

4. Boolean değer ya `true` ya da `false` olabilir.

  1. Truthy değer döndüren üç JavaScript ifadesi yazın.
  ```js
  console.log(!!"Merhaba"); // true
  console.log(!!1);       // true
  console.log(!![]);      // true
  ```
  
  2. Falsy değer döndüren üç JavaScript ifadesi yazın.
  ```js
  console.log(!!"");  // false
  console.log(!!0);   // false
  console.log(!!null); // false
  ```
  
5. Aşağıdaki karşılaştırma ifadelerinin sonuçlarını tahmin edin ve daha sonra `console.log()` kullanarak kontrol edin.

```js
console.log(4 > 3);     // true
console.log(4 >= 3);    // true
console.log(4 < 3);     // false
console.log(4 <= 3);    // false
console.log(4 == 4);    // true
console.log(4 === 4);   // true
console.log(4 != 4);    // false
console.log(4 !== 4);   // false
console.log(4 != '4');  // false
console.log(4 == '4');  // true
console.log(4 === '4'); // false
console.log('python'.length != 'jargon'.length); // true
```

6. Aşağıdaki ifadelerin sonuçlarını tahmin edin ve daha sonra `console.log()` kullanarak kontrol edin.

```js
console.log(4 > 3 && 10 < 12);        // true
console.log(4 > 3 && 10 > 12);        // false
console.log(4 > 3 || 10 < 12);        // true
console.log(4 > 3 || 10 > 12);        // true
console.log(!(4 > 3));                // false
console.log(!(4 < 3));                // true
console.log(!false);                  // true
console.log(!(4 > 3 && 10 < 12));     // false
console.log(!(4 > 3 && 10 > 12));     // true
console.log(!(4 === '4'));            // true
console.log(!('dragon'.includes('on') && 'python'.includes('on'))); // false
```

7. Date nesnesini kullanarak aşağıdaki işlemleri yapın.

```js
let now = new Date();

console.log(now.getFullYear());               // Bugünün yılı
console.log(now.getMonth() + 1);              // Bugünün ay numarası (getMonth() 0 tabanlıdır)
console.log(now.getDate());                   // Bugünün tarihi
console.log(now.getDay());                    // Bugünün hafta numarası
console.log(now.getHours());                  // Şu anki saat
console.log(now.getMinutes());                // Şu anki dakika
console.log(Math.floor(now.getTime() / 1000)); // 1 Ocak 1970'ten şu ana kadar geçen saniye sayısı
```

## Egzersiz: Seviye 2

1. Kullanıcıya bir üçgenin tabanını ve yüksekliğini girmesi için bir script yazın ve üçgenin alanını hesaplayın (alan = 0.5 x b x h).

```js
let base = parseFloat(prompt("Tabanı girin: "));
let height = parseFloat(prompt("Yüksekliği girin: "));
let area = 0.5 * base * height;
console.log(`Üçgenin alanı ${area}`);
```

2. Kullanıcıya bir üçgenin a, b ve c kenarlarını girmesi için bir script yazın ve üçgenin çevresini hesaplayın (çevre = a + b + c)

```js
let sideA = parseFloat(prompt("A kenarını girin: "));
let sideB = parseFloat(prompt("B kenarını girin: "));
let sideC = parseFloat(prompt("C kenarını girin: "));
let perimeter = sideA + sideB + sideC;
console.log(`Üçgenin çevresi ${perimeter}`);
```

3. Uzunluğu ve genişliği kullanıcıdan alın ve dikdörtgenin alanını (alan = uzunluk x genişlik) ve çevresini (çevre = 2 x (uzunluk + genişlik)) hesaplayın.

```js
let length = parseFloat(prompt("Uzunluğu girin: "));
let width = parseFloat(prompt("Genişliği girin: "));
let area = length * width;
let perimeter = 2 * (length + width);
console.log(`Dikdörtgenin alanı ${area}, çevresi ${perimeter}`);
```

4. Yarıçapı kullanıcıdan alın ve bir çemberin alanını (alan = pi x r x r) ve çevresini (c = 2 x pi x r) hesaplayın. Burada pi = 3.14.

```js
let radius = parseFloat(prompt("Yarıçapı girin: "));
let area = Math.PI * radius * radius;
let circumference = 2 * Math.PI * radius;
console.log(`Çemberin alanı ${area}, çevresi ${circumference}`);
```

5. y = 2x - 2 denkleminin eğimini, x-kesim noktasını ve y-kesim noktasını hesaplayın.

```js
let slope = 2; // m
let x_intercept = 1; // c / m
let y_intercept = -2; // c
console.log(`Eğim: ${slope}, x-kesim noktası: ${x_intercept}, y-kesim noktası: ${y_intercept}`);
```

6. Eğim m = (y<sub>2</sub>-y<sub>1</sub>)/(x<sub>2</sub>-x<sub>1</sub>). (2, 2) noktası ile (6,10) noktası arasındaki eğimi bulun.

```js
let x1 = 2, y1 = 2;
let x2 = 6, y2 = 10;
let slope = (y2 - y1) / (x2 - x1);
console.log(`Eğim: ${slope}`);
```

7. Yukarıdaki iki sorunun eğimlerini karşılaştırın.

```js
// İki eğim değeri de daha önce hesaplandı ve ikisi de 2 değerine sahip. Yani, eşitler.
```

8. y = x<sup>2</sup> + 6x + 9 denkleminin değerini hesaplayın. Farklı x değerleri kullanmayı deneyin ve y'nin hangi x değerinde 0 olduğunu belirleyin.

```js
let x_values = [-3, 0, 1, 2, 3];
for(let x of x_values) {
    let y = x*x + 6*x + 9;
    console.log(`x=${x}, y=${y}`);
}
// y'nin 0 olduğu x değeri -3'tür.
```

9. Kullanıcının saat başına ücreti ve saat sayısını girmesi için bir script yazın. Kişinin kazancını hesaplayın.

```js
let hours = parseFloat(prompt("Saat sayısını girin: "));
let rate = parseFloat(prompt("Saat başına ücreti girin: "));
let pay = hours * rate;
console.log(`Haftalık kazancınız ${pay}`);
```

10. İsminizin uzunluğu 7'den büyükse, isminiz uzun demektir, aksi takdirde isminiz kısa demektir.

```js
let name = prompt("İsminizi girin: ");
let message = (name.length > 7) ? "İsminiz uzun." : "İsminiz kısa.";
console.log(message);
```

11. Adınızın uzunluğunu ve soyadınız uzunluğunu karşılaştırın ve hangisi uzunsa ona göre bir mesaj gösterin.

```js
let firstName = prompt("Adınızı girin: ");
let lastName = prompt("Soyadınızı girin: ");
let message = (firstName.length > lastName.length) ? `Adınız, ${firstName}, soyadınızdan, ${lastName}, daha uzun.` : `Soyadınız, ${lastName}, adınızdan, ${firstName}, daha uzun.`;
console.log(message);
```

12. `myAge` ve `yourAge` adında iki değişken tanımlayın ve değerler atayın. Daha sonra sizin yaşınızla onun yaşa arasındaki farkı hesaplayıp gösterin:

```js
let myAge = 250;
let yourAge = 25;
let message = `Ben sizden ${myAge - yourAge} yıl daha yaşlıyım.`;
console.log(message);
```

13. Kullanıcının doğduğu yılı alın ve kullanıcı 18 yaşında veya daha büyükse kullanıcıya araba kullanma izni verin, değilse kullanıcının belirli bir süre beklemesi gerektiğini söyleyin.

```js
let birthYear = parseInt(prompt("Doğum yılınızı girin: "));
let age = new Date().getFullYear() - birthYear;
let message = (age >= 18) ? `Siz ${age} yaşındasınız. Araba kullanabilirsiniz.` : `Siz ${age} yaşındasınız. Araba kullanabilmek için ${18 - age} yıl beklemeniz gerekiyor.`;
console.log(message);
```

14. Kullanıcının yaşadığı yıl sayısını girmesi için bir script yazın. Bir kişinin yaşayabileceği saniye sayısını hesaplayın. Birinin sadece yüz yıl yaşadığını varsayın.

```js
let years = parseFloat(prompt("Kaç yıl yaşadınız: "));
let seconds = years * 365 * 24 * 60 * 60;
console.log(`Sen ${seconds} saniye yaşadın.`);
```

15. `Date` objesini kullanarak aşağıdaki gibi okunabilir bir zaman formatları oluşturun:

  1. YYYY-MM-DD HH:mm
  2. DD-MM-YYYY HH:mm
  3. DD/MM/YYYY HH:mm

```js
let now = new Date();

let year = now.getFullYear();
let month = now.getMonth() + 1;
let day = now.getDate();
let hour = now.getHours();
let minute = now.getMinutes();

console.log(`YYYY-MM-DD HH:mm: ${year}-${month}-${day} ${hour}:${minute}`);
console.log(`DD-MM-YYYY HH:mm: ${day}-${month}-${year} ${hour}:${minute}`);
console.log(`DD/MM/YYYY HH:mm: ${day}/${month}/${year} ${hour}:${minute}`);
```

## Egzersiz: Seviye 3

1. Date time objesini kullanarak okunabilir bir zaman formatı oluşturun. Saat ve dakika her zaman iki basamaklı olmalıdır (7 saat 07 ve 5 dakika 05 olmalıdır)
  - YYY-MM-DD HH:mm Örnek: 20220-01-02 07:05

```js
let now = new Date();

let year = now.getFullYear();
let month = String(now.getMonth() + 1).padStart(2, '0'); // ayı 2 basamaklı hale getirir
let day = String(now.getDate()).padStart(2, '0'); // günü 2 basamaklı hale getirir
let hour = String(now.getHours()).padStart(2, '0'); // saati 2 basamaklı hale getirir
let minute = String(now.getMinutes()).padStart(2, '0'); // dakikayı 2 basamaklı hale getirir

console.log(`YYYY-MM-DD HH:mm: ${year}-${month}-${day} ${hour}:${minute}`);
```

🎉 Tebrikler :) 4. günün egzersizlerine geçebilirsiniz. 🎉
