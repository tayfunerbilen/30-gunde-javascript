# 4. Gün Egzersizleri

## Egzersiz: Seviye 1

1. `prompt("Yaşınızı girin:")` fonksiyonunu kullanarak kullanıcıdan giriş alın. Kullanıcı 18 yaşında veya daha büyükse, 'Ehliyet alabilirsiniz' geri bildirimini verin, ancak 18 yaşından küçükse, 18 yaşına gelmesi için beklemesi gereken yılların sayısını belirten başka bir geri bildirim verin.

```js
let yas = prompt("Yaşınızı girin:");
if (yas >= 18) {
    console.log("Ehliyet alabilirsiniz.");
} else {
    console.log("Ehliyet alabilmeniz için " + (18 - yas) + " yıl beklemeniz gerekiyor.");
}
```

2. `myAge` ve `yourAge` değerlerini `if ... else` kullanarak karşılaştırın. Karşılaştırmaya dayanarak sonucu kimin daha yaşlı olduğunu belirten bir ifade ile konsola yazdırın. Yaşı giriş olarak almak için `prompt("Yaşınızı girin:")` kullanın.

```js
let myAge = 25;
let yourAge = prompt("Yaşınızı girin:");
if (yourAge > myAge) {
    console.log("Benim yaşım " + myAge + ". Siz benden " + (yourAge - myAge) + " yaş büyüksünüz.");
} else {
    console.log("Benim yaşım " + myAge + ". Ben sizden " + (myAge - yourAge) + " yaş büyüğüm.");
}
```

3. Eğer a, b'den büyükse 'a, b'den büyük' değilse 'a, b'den küçük' döndürün. Bunu iki farklı şekilde deneyin:
  - if else kullanarak
  - üçlü operatör kullanarak.

```js
let a = 4;
let b = 3;

// if else kullanarak
if (a > b) {
    console.log(a + ", " + b + " 'den büyük");
} else {
    console.log(a + ", " + b + " 'den küçük");
}

// üçlü operatör kullanarak
console.log(a > b ? a + ", " + b + " 'den büyük" : a + ", " + b + " 'den küçük");
```

4. Çift sayılar 2'ye bölünebilir ve kalan sıfırdır. JavaScript kullanarak bir sayının çift olup olmadığını nasıl kontrol edersiniz?

```js
 let sayi = prompt("Bir sayı girin:");
if (sayi % 2 == 0) {
    console.log(sayi + " çift bir sayıdır.");
} else {
    console.log(sayi + " tek bir sayıdır.");
}
```

## Egzersiz: Seviye 2

1. Öğrencilere puanlarına göre not verebilen bir kod yazın:
  - 80-100, A
  - 70-89, B
  - 60-69, C
  - 50-59, D
  - 0-49, F

```js
let puan = prompt("Puanınızı girin:");

if (puan >= 80 && puan <= 100) {
    console.log("Notunuz: A");
} else if (puan >= 70 && puan < 80) {
    console.log("Notunuz: B");
} else if (puan >= 60 && puan < 70) {
    console.log("Notunuz: C");
} else if (puan >= 50 && puan < 60) {
    console.log("Notunuz: D");
} else if (puan >= 0 && puan < 50) {
    console.log("Notunuz: F");
} else {
    console.log("Geçerli bir puan girin.");
}
```

2. Mevsimin Sonbahar, Kış, İlkbahar veya Yaz olup olmadığını kontrol edin. Kullanıcının girişi ise:
  - Eylül, Ekim veya Kasım ise, mevsim Sonbahar.
  - Aralık, Ocak veya Şubat ise, mevsim Kış.
  - Mart, Nisan veya Mayıs ise, mevsim İlkbahar
  - Haziran, Temmuz veya Ağustos ise, mevsim Yaz

```js
let ay = prompt("Ayı girin:").toLowerCase();

switch (ay) {
    case 'eylül':
    case 'ekim':
    case 'kasım':
        console.log("Mevsim: Sonbahar");
        break;
    case 'aralık':
    case 'ocak':
    case 'şubat':
        console.log("Mevsim: Kış");
        break;
    case 'mart':
    case 'nisan':
    case 'mayıs':
        console.log("Mevsim: İlkbahar");
        break;
    case 'haziran':
    case 'temmuz':
    case 'ağustos':
        console.log("Mevsim: Yaz");
        break;
    default:
        console.log("Geçerli bir ay girin.");
}
```

3. Bir günün hafta sonu veya iş günü olup olmadığını kontrol edin. Senaryonuz giriş olarak gün alacaktır.

```js
let gun = prompt("Bugün hangi gün?").toLowerCase();

switch (gun) {
    case 'pazartesi':
    case 'salı':
    case 'çarşamba':
    case 'perşembe':
    case 'cuma':
        console.log(gun.charAt(0).toUpperCase() + gun.slice(1) + " bir iş günüdür.");
        break;
    case 'cumartesi':
    case 'pazar':
        console.log(gun.charAt(0).toUpperCase() + gun.slice(1) + " bir hafta sonudur.");
        break;
    default:
        console.log("Geçerli bir gün girin.");
}
```

## Egzersiz: Seviye 3

1. Bir aydaki gün sayısını belirten bir program yazın.

```js
let ay = prompt("Bir ay girin:").toLowerCase();

switch (ay) {
    case 'ocak':
    case 'mart':
    case 'mayıs':
    case 'temmuz':
    case 'ağustos':
    case 'ekim':
    case 'aralık':
        console.log(ay.charAt(0).toUpperCase() + ay.slice(1) + " ayı 31 gündür.");
        break;
    case 'nisan':
    case 'haziran':
    case 'eylül':
    case 'kasım':
        console.log(ay.charAt(0).toUpperCase() + ay.slice(1) + " ayı 30 gündür.");
        break;
    case 'şubat':
        console.log(ay.charAt(0).toUpperCase() + ay.slice(1) + " ayı 28 gündür.");
        break;
    default:
        console.log("Geçerli bir ay girin.");
}
```

2. Bir aydaki gün sayısını belirten ve artık yılı dikkate alan bir program yazabiliriz. JavaScript'in Date nesnesini kullanabiliriz. Bu örnekte, her ayın son gününü bulmak için Date nesnesini kullanacağız.

```js
let ay = prompt("Bir ay girin:").toLowerCase();
let yil = prompt("Bir yıl girin:");

let ayNumarasi;
switch (ay) {
    case 'ocak': ayNumarasi = 0; break;
    case 'şubat': ayNumarasi = 1; break;
    case 'mart': ayNumarasi = 2; break;
    case 'nisan': ayNumarasi = 3; break;
    case 'mayıs': ayNumarasi = 4; break;
    case 'haziran': ayNumarasi = 5; break;
    case 'temmuz': ayNumarasi = 6; break;
    case 'ağustos': ayNumarasi = 7; break;
    case 'eylül': ayNumarasi = 8; break;
    case 'ekim': ayNumarasi = 9; break;
    case 'kasım': ayNumarasi = 10; break;
    case 'aralık': ayNumarasi = 11; break;
    default: console.log("Geçerli bir ay girin."); return;
}

let tarih = new Date(yil, ayNumarasi + 1, 0);
console.log(ay.charAt(0).toUpperCase() + ay.slice(1) + " ayı " + tarih.getDate() + " gündür.");
```

🎉 Tebrikler :) 5. günün egzersizlerine geçebilirsiniz. 🎉
