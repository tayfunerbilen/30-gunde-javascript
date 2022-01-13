# 📔 2. Gün

## Veri Türleri

Bir önceki bölümde, veri türlerinden biraz bahsetmiştik. Her değer bir veri türüne sahip. Veri türleri verinin özelliklerini tanımlar. İki çeşit veri türü bulunur:

1. Primitive (İlkel) veri türleri: Numbers, Strings, Booleans, Null, Undefined
2. Non-Primitive (İlkel Olmayan) veri türleri: Nesneler (Objects), Fonksiyonlar (Functions), Diziler (Arrays)

### Primitive (İlkel) Veri Türleri

Gelin ilkel ve ilkel olmayan veri türleri tam olarak nedir ona bir bakalım. İlkel (Primitive) veri türleri değişmez (düzenlenemez) veri türleridir. Yani bir kere bu türle oluştursak düzenleyemeyiz.

**Örneğin:**

```js
let word = 'Javascript'
```

`word` değişkeni içindeki yazının değerini değiştirmeye çalışırsak, değiştiremediğimizi göreceksiniz. Ama burada bahsettiğim şey yeni bir değer atamak değil. Örneğin şu kodu ele alalım.

```js
word[0] = 'Y'
```

Bu işlem `word` içinde depolanan değeri etkilemeyecektir yani değiştirmeyecektir. O zaman stringlerin düzenlenemez yani immutable (değişmez) olduğunu söyleyebiliriz. İlker veri türleri değerlerine göre karşılaştırılır. Farklı değerleri karşılaştırarak örneklendirelim.

```js
let numOne = 3
let numTwo = 3

console.log(numOne == numTwo)      // true

let js = 'JavaScript'
let py = 'Python'

console.log(js == py)             //false 

let lightOn = true
let lightOff = false

console.log(lightOn == lightOff) // false
```

### Non-Primitive (İlkel Olmayan) Veri Türler

İlkel veri türünün aksine, bu veri türleri düzenlenebilir yani değişebilir (mutable). Oluşturulduktan sonra değeri düzenleyebiliriz. Bir dizi oluşturarak bunu örneklendirelim ana öncesinde dizi ne diye soracak olursanız, dizi köşeli parantezler içinde virgüllerle ayrılmış değerler listesi diyebiliriz. Normalde değişken şu ana kadar hep tek bir değeri depoladı, ancak diziler bunu değiştiriyor, birden fazla değer depolamamızı sağlıyor. Ayrıca dizi içindeki değerler farklı veri türlerinde olabilir. Dizi elemanlarına erişmek için index değerleri kullanılır. Javascript'de dizi indexleri 0'dan başlar. Bu da eğer ilk elemana ulaşmak istiyorsanız aslında 0. elemanı seçmeniz gerekiyor demek oluyor. Aynı şekilde 2. eleman için 1'i, 3. eleman için 2.yi seçmelisiniz, bu böyle devam eder -1 olarak düşünebiliriz seçme işlemini.

```js
let nums = [1, 2, 3]
nums[0] = 10

console.log(nums)  // [10, 2, 3]
```

Gördüğünüz gibi, dizi non-primitive tipinde olduğu için düzenlenebilir (mutable). Non-primitive türler değerlerine göre karşılaştırılamazlar. Birebir aynı değerlere sahip iki non-primitive türünde değer bile birbirine eşit değildir.

```js
let nums = [1, 2, 3]
let numbers = [1, 2, 3]

console.log(nums == numbers)  // false

let userOne = {
  name: 'Tayfun Erbilen',
  age: 28
}

let userTwo = {
  name: 'Tayfun Erbilen',
  age: 28
}

console.log(userOne == userTwo) // false
```

Temel kural, non-primitive veri türlerini karşılaştırmıyoruz. Dizileri, fonksiyonları, objeleri karşılaştırmayın. Non-primitive türler değerlerine göre değil referanslarına göre karşılaştırılır. Dolayısı ile iki değer aynı referansa sahipse o zaman eşit olacaklardır. Örneğin;

```js
let nums = [1, 2, 3]
let numbers = nums

console.log(nums == numbers)  // true

let userOne = {
  name: 'Tayfun Erbilen',
  age: 28
}

let userTwo = userOne

console.log(userOne == userTwo)  // true
```

Eğer primitive ve non-primitive veri türlerini anlamakta zorluk çekiyorsanız, yalnız değilsiniz. Şimdilik burayı anlamaya uğraşmayın ve sonraki bölüme geçin, daha sonra tekrar buraya gelip kendinizi yeniden değerlendirin. Şimdi gelin number veri türlerine bir bakalım.

## Sayılar (Numbers)

Sayılar, aritmatik işlemleri yaptığımız tam sayılar ve ondalık değerlerdir. Gelin bir örnekle inceleyelim.

```js
let age = 35
const gravity = 9.81  // değişmeyen değerler için const kullanıyorduk, yerçekimi sabiti m/s2 cinsinden
let mass = 72         // kilogram cinsinden kütle
const PI = 3.14       // pi - geometrik sabit

// More Examples
const boilingPoint = 100 //  suyun kaynama noktası aynı zamanda sabit bir değerdir
const bodyTemp = 37      // ortalama insan vücudu sıcaklığı aynı zamanda sabit bir değerdir

console.log(age, gravity, mass, PI, boilingPoint, bodyTemp)
```
### Math Nesnesi

Javascript'de `Math` objesi sayılarla çalışmamız için gereken metodları sağlar.

```js
const PI = Math.PI

console.log(PI)                            // 3.141592653589793

// En yakın sayıya yuvarlama
// .5 üstü ise yukarıya 0.5 altı ise aşağıya yuvarlar

console.log(Math.round(PI))                // 3 - en yakın sayıya yuvarlar

console.log(Math.round(9.81))              // 10

console.log(Math.floor(PI))                // 3 aşağı yuvarlar

console.log(Math.ceil(PI))                 // 4 yukarı yuvarlar

console.log(Math.min(-5, 3, 20, 4, 5, 10)) // -5, en düşük değeri döndürür

console.log(Math.max(-5, 3, 20, 4, 5, 10)) // 20, en yüksek değeri döndürür

const randNum = Math.random() // 0 ile 0.999999 arasında rastgele sayı üretir
console.log(randNum)

const num = Math.floor(Math.random () * 11) // 0 ile 10 arasında rastgele sayı üretir
console.log(num)

// Mutlak değer
console.log(Math.abs(-10))      // 10

// karekök
console.log(Math.sqrt(100))     // 10

console.log(Math.sqrt(2))       // 1.4142135623730951

// Üs
console.log(Math.pow(3, 2))     // 9

console.log(Math.E)             // 2.718

// Logaritma
console.log(Math.log(2))        // 0.6931471805599453
console.log(Math.log(10))       // 2.302585092994046

// Trigonometri
Math.sin(0)
Math.sin(60)

Math.cos(0)
Math.cos(60)
```

#### Rastgele Numara Üretici

Javascript Math objesinde `random()` metodu 0 ile 0.9999.. arasında rastgele sayı üretmemizi sağlar. 

```js
let randomNum = Math.random() // 0 ile 0.999... arasında sayı üretir
```

Gelin bu metodu kullanarak nasıl 0 ile 10 arasında sayı üretebiliriz ona bakalım.

```js
let randomNum = Math.random()         // 0 ile 0.999 arasında sayı üretir
let numBtnZeroAndTen = randomNum * 11

console.log(numBtnZeroAndTen)         // bu bize min. 0 max 10.99 değeri verir

let randomNumRoundToFloor = Math.floor(numBtnZeroAndTen)
console.log(randomNumRoundToFloor)    // bu bize min. 0 max. 10 değeri verir
```

## Strings

String'ler tırnak içinde yazılmış metinlerdir. Bir string tanımlamak için, bir değişken adına, atama operatörüne ve tırnaklar içinde bir değere ihtiyacımız vardır. Örneklerine bakalım;

```js
let space = ' '        // boşlukla da oluşturulabilir
let firstName = 'Asabeneh'
let lastName = 'Yetayeh'
let country = 'Finland'
let city = 'Helsinki'
let language = 'JavaScript'
let job = 'teacher'
let quote = "The saying,'Seeing is Believing' is not correct in 2020."
let quotWithBackTick = `The saying,'Seeing is Believing' is not correct in 2020.`
```

### String Birleştirme

İki ya da daha fazla string'i birleştirme işlemine `concatenation` deniyor. Yukarıdaki değerleri birleştirerek tek bir string haline getirelim.

```js
let fullName = firstName + space + lastName; // birden fazla stringi birleştirmek için + kullandık
console.log(fullName);
```

String'leri birleştirmenin birden fazla yolu vardır.

#### Toplama Operatörüyle String Birleştirmek

Bu operatörle string birleştirme işlemi eskide kaldı. Bu şekilde kullanırsanız hatalarla karşılaşma olasılığınız yüksek. Yine de bilmeniz yararınıza olacaktır, ancak string birleştirme için ES6 yöntemi olan `template string` i tercih edeceğiz (daha sora açıklayacağız).

```js
// Farklı veri türlerinde farklı değişkenler tanımlayalım
let space = ' '
let firstName = 'Asabeneh'
let lastName = 'Yetayeh'
let country = 'Finland'
let city = 'Helsinki'
let language = 'JavaScript'
let job = 'teacher'
let age = 250


let fullName = firstName + space + lastName
let personInfoOne = fullName + '. I am ' + age + '. I live in ' + country; // ES5 string addition

console.log(personInfoOne)
// Çıktı: Asabeneh Yetayeh. I am 250. I live in Finland
```

### Long Literal Strings

Bir string tek karakter olabileceği gibi bir paragraf ya da sayfa dolusu kelime olabilir. Eğer string fazla uzunsa tek satıra sığdırmak yerine çok satırda yazmamız gerekebilir. Eğer yeni bir satıra geçilecekse \ işareti ile sonlandırılıp sonraki satıra geçilmelidir.

```js
const poetry = "Sen kocaman çöllerde bir kalabalık gibisin,\
Kocaman denizlerde ender bir balık gibisin.\
Bir ısıtır, bir üşütür, bir ağlatır bir güldürür;\
Sen hem bir hastalık hem de sağlık gibisin.\
\
- Özdemir Asaf"

console.log(poetry)
```

#### Kaçış Karakterleri

Javascript ve diğer programlama dillerinde \ işaretinden sonra bazı karakterler geliyorsa buna kaçış karakteri denmektedir. Bazı yaygın kaçış karakterlerine bir bakalım.

- \n : yeni satır
- \t : tab - 8 boşluk
- \\\ : ters slash
- \\' : tek tırnak
- \\" : çift tırnak

```js
console.log('I hope everyone is enjoying the 30 Days Of JavaScript challenge.\nDo you ?') // line break
console.log('Days\tTopics\tExercises')
console.log('Day 1\t3\t5')
console.log('Day 2\t3\t5')
console.log('Day 3\t3\t5')
console.log('Day 4\t3\t5')
console.log('This is a backslash  symbol (\\)') // ters slash yazmak için iki ters slash koymamız gerekiyor diğer türlü ondan sonra geleni kaçış karakteri gibi yorumlamaya çalışıyor.
console.log('In every programming language it starts with \"Hello, World!\"')
console.log("In every programming language it starts with \'Hello, World!\'")
console.log('The saying \'Seeing is Believing\' isn\'t correct in 2020')
```

Konsol çıktısı:

```
I hope everyone is enjoying the 30 Days Of JavaScript challenge.
Do you ?
Days  Topics  Exercises
Day 1 3 5
Day 2 3 5
Day 3 3 5
Day 4 3 5
This is a backslash  symbol (\)
In every programming language it starts with "Hello, World!"
In every programming language it starts with 'Hello, World!'
The saying 'Seeing is Believing' isn't correct in 2020
```

### Şablon Değişmezleri (Template Strings)

Yukarıda anlatılan tamamını unutun. Template stringleri kullanarak artık birleştirme işlemleri için, alt satıra geçmek için ya da kaçış karakterleri vs. kullanımı gibi şeylere ihtiyaç duymuyoruz. Backtick (`) karakterleri içerisinde bunların tamamını özgürce yapablirsiniz. Ayrıca stringlerin içine javascript ifadeleri yanımlamak için başında $ olacak şekilde süslü parantezler içinde yazmamız gerekiyor.

```js
// Sözdizimi
`String literal text`
`String literal text ${expression}`
```

__Örnek 1__

```js
console.log(`The sum of 2 and 3 is 5`)              // statik olarak veriyi yazmak
let a = 2
let b = 3
console.log(`The sum of ${a} and ${b} is ${a + b}`) // veriyi dinamik olarak yazmak
```

__Örnek 2__

```js
let firstName = 'Asabeneh'
let lastName = 'Yetayeh'
let country = 'Finland'
let city = 'Helsinki'
let language = 'JavaScript'
let job = 'teacher'
let age = 250
let fullName = firstName + ' ' + lastName

let personInfoTwo = `I am ${fullName}. I am ${age}. I live in ${country}.` //ES6 - String interpolation method
let personInfoThree = `I am ${fullName}. I live in ${city}, ${country}. I am a ${job}. I teach ${language}.`
console.log(personInfoTwo)
console.log(personInfoThree)
```

```
I am Asabeneh Yetayeh. I am 250. I live in Finland.
I am Asabeneh Yetayeh. I live in Helsinki, Finland. I am a teacher. I teach JavaScript.
```

Template stringleri kullanarak javascript ifadeleri tanımlayabiliyoruz. Bu ifadeler bir değişken olabildiği gibi herhangi bir javascript işlemi de olabilir. Örneğin;

```js
let a = 2
let b = 3
console.log(`${a} is greater than ${b}: ${a > b}`)
```

```
2 is greater than 3: false
```

### String Metodları

Javascript'de herşey bir nesnedir. Stringler primitive (ilkel) veri türleridir yani bir kere oluşturulunca düzenlenemezler. String nesneleri bir çok string metodlarına sahiptir. String'lerle çalışırken bu metodlar bir çok işimizi kolaylaştırır.

1. `length` : Bu metod karakterin uzunluğunu döndürür. Boşluklar ve tüm özel karakterler dahil olmak üzere.

__Örnek__

```js
let js = 'JavaScript'
console.log(js.length)         // 10
let firstName = 'Asabeneh'
console.log(firstName.length)  // 8
```

2. String'de karakterlere erişmek : Karakterlere index değerlerini kullanarak erişebiliriz. Programlamada sayma 0'dan başlar, yani ilk karaktere erişmek için 0. indexini almamız gerekir. Son karakter içinse uzunluk - 1 şeklinde.

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/string_indexes.png)

Örnek:

```js
let string = 'JavaScript'
let firstLetter = string[0]

console.log(firstLetter)           // J

let secondLetter = string[1]       // a
let thirdLetter = string[2]
let lastLetter = string[9]

console.log(lastLetter)            // t

let lastIndex = string.length - 1

console.log(lastIndex)  // 9
console.log(string[lastIndex])    // t
```

3. `toUpperCase()` : Harfleri büyük harfe çevirir.

```js
let string = 'JavaScript'

console.log(string.toUpperCase())     // JAVASCRIPT

let firstName = 'Asabeneh'

console.log(firstName.toUpperCase())  // ASABENEH

let country = 'Finland'

console.log(country.toUpperCase())    // FINLAND
```

4. `toLowerCase()` : Harfleri küçük harfe çevirir.

```js
let string = 'JavasCript'

console.log(string.toLowerCase())     // javascript

let firstName = 'Asabeneh'

console.log(firstName.toLowerCase())  // asabeneh

let country = 'Finland'

console.log(country.toLowerCase())   // finland
```

5. `substr()` : İki parametre alır, başlangıç değeri ve uzunluk.

```js
let string = 'JavaScript'
console.log(string.substr(4,6))    // Script

let country = 'Finland'
console.log(country.substr(3, 4))   // land
```

6. `substring()` : İki parametre alır, başlangıç indexi ve bitiş indexi. Ancak bitiş indexindeki karakter dahil olmaz.

```js
let string = 'JavaScript'

console.log(string.substring(0,4))     // Java
console.log(string.substring(4,10))    // Script
console.log(string.substring(4))       // Script

let country = 'Finland'

console.log(country.substring(0, 3))   // Fin
console.log(country.substring(3, 7))   // land
console.log(country.substring(3))      // land
```

7. `split()` : Belirtilen bir ayraç yardımı ile string'i parçalar.

```js
let string = '30 Days Of JavaScript'

console.log(string.split())     // Diziye dönüştürür -> ["30 Days Of JavaScript"]
console.log(string.split(' '))  // boşluktan parçalayıp diziye dönüştürür -> ["30", "Days", "Of", "JavaScript"]

let firstName = 'Asabeneh'

console.log(firstName.split())    // Diziye dönüştürür - > ["Asabeneh"]
console.log(firstName.split(''))  // Boş string verilirse harfleri diziye dönüştürür ->  ["A", "s", "a", "b", "e", "n", "e", "h"]

let countries = 'Finland, Sweden, Norway, Denmark, and Iceland'

console.log(countries.split(','))  // Virgül ile parçalarayak diziye dönüştürür -> ["Finland", " Sweden", " Norway", " Denmark", " and Iceland"]
console.log(countries.split(', ')) // Diğerinden farklı olarak boşluk olmasını engeller ["Finland", "Sweden", "Norway", "Denmark", "and Iceland"]
```

8. `trim()` : Başlangıçtaki ve sondaki gereksiz boşlukları kaldırır.

```js
let string = '   30 Days Of JavaScript   '

console.log(string)
console.log(string.trim(' '))

let firstName = ' Asabeneh '

console.log(firstName)
console.log(firstName.trim())  // bir değer girmedende aynı işlemi yapmaya devam eder
```

```
   30 Days Of JavasCript   
30 Days Of JavasCript
  Asabeneh 
Asabeneh
```

9. `includes()` : String içinde belirtilen string'in olup olmadığını kontrol eder. Aratılan değer varsa `true` yoksa `false` değeri döner. 

```js
let string = '30 Days Of JavaScript'

console.log(string.includes('Days'))     // true
console.log(string.includes('days'))     // false - büyük-küçük harf duyarlı!
console.log(string.includes('Script'))   // true
console.log(string.includes('script'))   // false
console.log(string.includes('java'))     // false
console.log(string.includes('Java'))     // true

let country = 'Finland'

console.log(country.includes('fin'))     // false
console.log(country.includes('Fin'))     // true
console.log(country.includes('land'))    // true
console.log(country.includes('Land'))    // false
```

10. `replace()` : İki parametre alır, ilk parametre değiştirilecek string, ikinci parametre değiştirilmesini istediği string. 

```js
let string = '30 Days Of JavaScript'
console.log(string.replace('JavaScript', 'Python')) // 30 Days Of Python

let country = 'Finland'
console.log(country.replace('Fin', 'Noman'))       // Nomanland
```

11. `charAt()` : Parametre olarak index alır ve o indexe ait karakteri döndürür.

```js
let string = '30 Days Of JavaScript'
console.log(string.charAt(0))        // 3

let lastIndex = string.length - 1
console.log(string.charAt(lastIndex)) // t
```

12. `charCodeAt()` : Parametre olarak index alır ve o indexe ait ASCII karşılığını döndürür.

```js
let string = '30 Days Of JavaScript'
console.log(string.charCodeAt(3))        // D ASCII numarası 68

let lastIndex = string.length - 1
console.log(string.charCodeAt(lastIndex)) // t ASCII numarası 116
```
Bunu anlamadım ben deyip kafanıza takmayın, şimdilik bir önemi yok bilin yeter.

