# 📔 3. Gün

## Bool Değerler

Bir boolean veri türü 2 değerden birine sahip olabilir: _true_ veya _false_. Bu veri türü, karşılaştırma operatörleri konusunu gördüğünüzde daha da netleşecektir. Herhangi bir karşılaştırmadan sonra true veya false değerleri döner.

**Örnek: Boolean Veri Türü**

```js
let isLightOn = true;
let isRaining = false;
let isHungry = false;
let isMarried = true;
let truValue = 4 > 3; // true döner
let falseValue = 4 < 3; // false döner
```

Bu konuda anlaştıysak devam edelim.

### True dönen değerler

- Sıfır hariç tüm rakamlar (negatif ve pozitif farketmez) true değer döndürür. Yani doğru kabul edilir.
- Boş dize ('') dışında tüm metinler true değer döndürür.
- The boolean true

### False dönen değerler

- 0
- 0n (0'dan sonra herhangi bir şey)
- null (boş değer)
- undefined (tanımsız)
- NaN
- the boolean false
- '', "", ``, boş yazı değerleri

Bu değerlerin akılda kalması, karşılaştırma operatörlerinde çok önemli olacak. Sıradaki derste bunları karşılaştırmalar da kullanacağız.

## Undefined (Tanımsız)

Eğer bir değişken belirleyip içine değer atamazsak bize undefined (tanımsız) değer döner. Ek olarak, tanımladığımız fonksitonun dönen değeri yoksa yine undefined (tanımsız) değer döndüğünü görürüz.

```js
let firstName;
console.log(firstName); //undifined, çünkü henüz bir değer atanmadı
```

## Null (Boş)

```js
let empty = null;
console.log(empty); // -> null değer yok demek.
```

## Operators (Operatörler)

### Assignment operators (Atama Operatörleri)

Javascript'te eşittir ("=") işareti atama operatörü olarak kullanılır.

```js
let firstName = "Prototurk";
let country = "Türkiye";
```

Assignment Operators (Atama Operatörleri)

![Assignment operators](../images/assignment_operators.png)

### Arithmetic Operators (Aritmatik Operatörler)

Aritmatik operatörler aslında bildiğimiz matematiksel operatörlerdir.

- Toplama(+): a + b
- Çıkarma(-): a - b
- Çarpma(_): a _ b
- Bölme(/): a / b
- Mod Alma(%): a % b
- Üst Alma(**): a ** b

```js
let numOne = 4;
let numTwo = 3;
let sum = numOne + numTwo;
let diff = numOne - numTwo;
let mult = numOne * numTwo;
let div = numOne / numTwo;
let remainder = numOne % numTwo;
let powerOf = numOne ** numTwo;

console.log(sum, diff, mult, div, remainder, powerOf); // 7,1,12,1.33,1, 64
```

```js
const PI = 3.14;
let radius = 100; // metre cinsinden uzunluk

// Dairenin alanını hesaplayalım.
const areaOfCircle = PI * radius * radius;
console.log(areaOfCircle); //  314 m

const gravity = 9.81; // in m/s2
let mass = 72; // in Kilogram

// Bir cismin ağırlığını hesaplayalım.
const weight = mass * gravity;
console.log(weight);

const boilingPoint = 100;
const bodyTemp = 37;

// EcmaScript ile gelen (``) eğik çizgiyi kullanarak metinlerimizle hesapladığımız değişkenleri birleştiriyoruz.
console.log(
  `The boiling point of water is ${boilingPoint} oC.\nHuman body temperature is ${bodyTemp} oC.\nThe gravity of earth is ${gravity} m / s2.`
);
```

### Comparison Operators (Karşılaştırma Operatörleri)

Programlamada değerleri karşılaştırırz ve iki değeri karşılaştırmak için karşılaştırma operatörlerini kullanırız. Bir değerin diğer değere eşit veya büyük olup olmadığını kontrol ederiz.

![Comparison Operators](../images/comparison_operators.png)
**Example: Comparison Operators**

```js
console.log(3 > 2); // true döner, çünkü 3 büyüktür 2 den.
console.log(3 >= 2); // true döner, çünkü 3 büyüktür 2 den.
console.log(3 < 2); // false döner, çünkü 3, 2 den küçük değildir.
console.log(2 <= 3); //true, çünkü 2 küçüktür 3 den.
console.log(3 == 2); //false, çünkü 3 ve 2 eşit değildir.
console.log(3 != 2); //true, çünkü 3 ve 2 eşit değildir.
console.log(3 == "3"); // true, sadece değerler karşılaştırılır.
console.log(3 === "3"); // false, üç tane eşittir kullanırsan bu sefer veri tiplerinide karşılaştırır.
console.log(3 !== "3"); // true, hem veriler hem de veri türleri karşılaştırılır
console.log(3 != 3); // false, compare only value
console.log(3 !== 3); // false, compare both value and data type
console.log(0 == false); // true, equivalent
console.log(0 === false); // false, veri türleri aynı değildir.
console.log(0 == ""); // true, eşittir.
console.log(0 == " "); // true, eşittir.
console.log(0 === ""); // false, veri türleri aynı değildir.
console.log(1 == true); // true
console.log(1 === true); // false
console.log(undefined == null); // true
console.log(undefined === null); // false
console.log(NaN == NaN); // false
console.log(NaN === NaN); // false
console.log(typeof NaN); // number

console.log("mango".length == "avocado".length); // false
console.log("mango".length != "avocado".length); // true
console.log("mango".length < "avocado".length); // true
console.log("milk".length == "meat".length); // true
console.log("milk".length != "meat".length); // false
console.log("tomato".length == "potato".length); // true
console.log("python".length > "dragon".length); // false
```

Yukarıdaki karşılaştırmaları mantığınızla anlamaya çalışın.

As rule of thumb, if a value is not true with == it will not be equal with ===. Using === is safer than using ==. The following [link](https://dorey.github.io/JavaScript-Equality-Table/) has an exhaustive list of comparison of data types.

Temel kural şudur: eğer bir değer "==" ile doğru değilse "===" ile de eşit olmayacaktır. "===" kullanmak "==" kullanmaktan daha iyi ve güvenlidir. Çünkü 3 eşittir kullandığınızda veri türü karşılaştırmasıda yapmış olursunuz. Bu bir nevi type kontrolüdür.

### Logical Operators (Mantık Operatörleri)

Şimdi genel mantık operatörlerine bakalım: && (ve işareti), || (veya işareti) ve ! (olumsuz işareti).

Eğer iki değer true ise && her daim true döner. İki değerden en az biri false ise her daim false döner.

Eğer iki değerden herhangi biri true ise || true döner.

! operatörü "değilse" anlamında kullanılır. Örneğin "a" değişkeni true değerinde, biz !a dersek bu false olarak dönecektir.

```js
// && ampersand operator example

const check = 4 > 3 && 10 > 5; // true && true -> true
const check = 4 > 3 && 10 < 5; // true && false -> false
const check = 4 < 3 && 10 < 5; // false && false -> false

// || pipe or operator, example

const check = 4 > 3 || 10 > 5; // true  || true -> true
const check = 4 > 3 || 10 < 5; // true  || false -> true
const check = 4 < 3 || 10 < 5; // false || false -> false

//! Negation examples

let check = 4 > 3; // true
let check = !(4 > 3); //  false
let isLightOn = true;
let isLightOff = !isLightOn; // false
let isMarried = !false; // true
```

### Increment Operator (Artış Opearatörü)

Javascript'te bir değişkenin değerini arttırmak için Increment Operator'ü kullanırız. Artık operatörü pre veya post olabilir. İksinide görelim:

1. Pre-increment

```js
let count = 0;
console.log(++count); // 1
console.log(count); // 1
```

1. Post-increment

```js
let count = 0;
console.log(count++); // 0
console.log(count); // 1
```

Çoğu zaman post-increment kullanırız. En azından nasıl kullanıldığını bilmelisiniz.

### Decrement Operator (Azaltma Operatörü)

Bir değişkenin değerini azaltmak için Decrement Operator'ünü kullanırız. Burada da pre veya post olarak kullanabiliriz. Her ikisi şu şekilde:

1. Pre-decrement

```js
let count = 0;
console.log(--count); // -1
console.log(count); // -1
```

2. Post-decrement

```js
let count = 0;
console.log(count--); // 0
console.log(count); // -1
```

### Ternary Operators

Ternary operatör'leri bir koşul yazmaya izin verir. Javascript'te if ve else'in yaptıklarının kısa halidir. Örneğe bakalım:

```js
let isRaining = true;
isRaining
  ? console.log("Yağmurluğa ihtiyacın var.")
  : console.log("Yağmurluğa ihtiyacın yok.");

isRaining = false;
isRaining
  ? console.log("Yağmurluğa ihtiyacın var.")
  : console.log("Yağmurluğa ihtiyacın yok.");
```

Sonuç şu şekilde olur:

```sh
Yağmurluğa ihtiyacın var.
Yağmurluğa ihtiyacın yok.
```

```js
let number = 5;
number > 0
  ? console.log(`${number} pozitif bir sayıdır.`)
  : console.log(`${number} negatif bir sayıdır`);
number = -5;

number > 0
  ? console.log(`${number} pozitif bir sayıdır.`)
  : console.log(`${number} negatif bir sayıdır.`);
```

Sonuç şu şekilde olur:
```sh
5 pozitif bir sayıdır.
-5 negatif bir sayıdır.
```

### Operator Precendence (Operatör Öncelikleri)

Operatör önceliklerini bu bağlantıdan okumanızı tavsiye ederim. [link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)

## Window Methods

### Window alert() method

En başta gördüğünüz gibi alert() metodu, bir mesaj alanı ve bir "Tamam" butonu ile bir uyarı kutusu görüntüler. alert() metodu yerleşik bir metoddur ve değer alır.

```js
alert(message);
```

```js
alert("PROTOTURK'e Hoşgeldin!");
```

Normal şartlar da alert metodu kullanmamalısınız çünkü kullanışsızdır. Sadece testlerini yaparken kullanmalısınız.

### Window prompt() method

prompt() metodu input kutusu görüntüler ve kullanıcının bu input'a girdiği değeri alır. Bu değeri bir değişkende saklayabilirsiniz. prompt() metodu iki değer alır. İkinci değeri opsiyoneldir.

```js
prompt("Bir yazı gir", "opsiyonel alan");
```

```js
let number = prompt("Rakam gir", "Rakamını buraya gir.");
console.log(number);
```

### Window confirm() method

confirm() metodu, mesaj alanı, tamam ve vazgeç butonlarına sahip bir diyalog kutusu görüntüler. confirm kutusu genellikle kullanıcıdan herhangi bir izin almak için kullanılır. confirm() metodu bir string değeri alır. "Tamam" butonuna tıklanırsa true, Vazgeç butonuna tıklanırsa false değer döner. Bu dönen değeri bir değişkende saklayıp kullanabiliriz. 

```js
const agree = confirm("Silmek istediğinizden emin misiniz? ");
console.log(agree); // "Tamam" tıklanırsa true, Vazgeç tıklanırsa false gelir.
```

Tüm metodlar bunlarla sınırlı değil. Ayrı bir bölümde bu metodları derinlemesine işleyeceğiz.

## Date Object (Tarih Nesnesi)

Belirli bir faaliyetin veya olayın zamanını bilmek isteriz. Javascript'te geçerli zaman ve tarih, Date Object kullanılarak oluşturulur.

Oluşturduğumuz Date objesi bize bir çok zaman ve tarih metodu sağlar. Kullandığımız metodlarla tarih ve zaman bilgilerini alabiliriz. Genel de bu metodlar "almak" anlamına gelen _get_ ile başlar.
_getFullYear(), getMonth(), getDate(), getDay(), getHours(), getMinutes, getSeconds(), getMilliseconds(), getTime(), getDay()_

![Date time Object](../images/date_time_object.png)

### Creating a time object (Zaman objesi oluşturmak)

Bir zaman objesi oluşturalım. Zaman objesi zaman hakkında bilgi sağlayacaktır. 

```js
const now = new Date();
console.log(now); // Sat Jan 04 2020 00:56:41 GMT+0200 (Eastern European Standard Time)
```

Zaman objesini oluşturduk ve tablo üzerinde bahsettiğimiz get yöntemlerini kullanarak nesneden herhangi bir tarih saat bilgisine ulaşabiliyoruz.

### Getting full year (Yıl bilgisi alma)

Date nesnesinden tam yıl bilgisini alalım:

```js
const now = new Date();
console.log(now.getFullYear()); // 2020
```

### Getting month (Ay bilgisini alma)

Date nesnesinden ay bilgisini alalım:

```js
const now = new Date();
console.log(now.getMonth()); // 0, Çünkü aylardan Ocaktır,  month(0-11)
```

### Getting date (Gün bilgisini alma - Ay)

Date nesnesinden ayın kaçıncı günü olduğunun bilgisini alalım:

```js
const now = new Date();
console.log(now.getDate()); // 4, çünkü ayın 4. günü,  day(1-31)
```

### Getting day (Gün bilgisini alma - Hafta)

Date nesnesinden haftanın hangi gününde olduğumuzun bilgisini alalım:

```js
const now = new Date();
console.log(now.getDay());
```

### Getting hours (Saat bilgisini alma)

Date nesnesinden saat bilgisini alalım:

```js
const now = new Date();
console.log(now.getHours()); // 0, çünkü saat 00:56:41
```

### Getting minutes (Dakika bilgisini alma)

Date nesnesinden dakika bilgisini alalım:

```js
const now = new Date();
console.log(now.getMinutes()); // 56, çünkü saat 00:56:41
```

### Getting seconds (Saniye bilgisini alma)

Date nesnesinden saniye bilgisini alalım:

```js
const now = new Date();
console.log(now.getSeconds()); // 41, çünkü saat 00:56:41
```

### Getting time (Unix zamanı alma)

Bu metod 1 Ocak 1970'den itibaren milisaniye cinsinden süre verir. Bu bir Unix zamanıdır. Unix zamanını iki şekilde alabiliriz:

1. _getTime()_ Kullanabiliriz

```js
const now = new Date();
console.log(now.getTime());
```

1. _Date.now()_ Kullanabiliriz

```js
const allSeconds = Date.now();
console.log(allSeconds);

const timeInSeconds = new Date().getTime();
console.log(allSeconds == timeInSeconds); // true
```

Aldığımız Unix zamanını okunabilir bir zaman biçimine çevirelim.

**Örnek:**

```js
const now = new Date();
const year = now.getFullYear(); // yılı döner
const month = now.getMonth() + 1; // ayları döner(0 - 11)
const date = now.getDate(); // gün bilgisini döner (1 - 31)
const hours = now.getHours(); // saat döner (0 - 23)
const minutes = now.getMinutes(); // dakika döner (0 -59)

console.log(`${date}/${month}/${year} ${hours}:${minutes}`); // 4/1/2020 0:56
```

🌕 You have boundless energy. You have just completed day 3 challenges and you are three steps a head in to your way to greatness. Now do some exercises for your brain and for your muscle.

Sınırsız bir enerjin var. 3. günü bitirdin ve başarıya giden yolda üç adım öndesin.