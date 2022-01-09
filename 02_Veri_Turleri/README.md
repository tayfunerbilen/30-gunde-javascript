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

.... devam edecek ....
