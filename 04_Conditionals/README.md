# 📔 4. Gün

## Conditionals (Koşullar)

Yazılımda koşullu ifadeleri, farklı koşullara dayalı kararlar vermek için kullanırız. Javascript'te bu ifadeler yukarıdan aşağıya sırayla yürütülür. Bu yukarıdan aşağıya akışın yolu iki şekilde değiştirilebilir:

- Eğer belirli bir koşul doğruysa, bir veya birden fazla ifadeden oluşan bir blok yürütülür. (Bu cümle karışık gelebilir örnekleri görünce anlayacaksınız.)

- belirli bir ifade doğru olduğu sürece, bir veya daha fazla ifadeden oluşan bir blok tekrar tekrar yürütülecektir. Bu bölümde _if_, _else_ , _else if_  deyimlerini ele alacağız.

Önceki bölümlerde öğrendiğimiz karşılaştırma ve mantıksal operatörler burada faydalı olacaktır.

Karşılaştırma oparatörlerini şu şekillerde tanımlayabiliriz:

- if
- if else
- if else if else
- switch
- ternary operator

### If (Eğer)

Javascript ve diğer çoğu dilde "if" sözcüğü bir koşulun doğru olup olmadığını kontrol etmek ve doğru yanlışa göre ilgili kodu çalıştırmak için kullanılır. Bir karşılaştırma operatörü oluşturmak için "if" kullanalım. Parantez içindeki kısma koşulumuzu ve süslü parantezler arasınada koşul sağlandıktan sonra çalışacak kod yazılır.

```js

// syntax (syntax: sözdizimi, bir dildeki yazım biçimi anlamında kullanılır. )

if (kosul) {
  //bu kısma kosul sağlandığında yürütülecek kod yazılır.
}
```

**Örnek:**

```js
let num = 3
if (num > 0) {
  console.log(`${num} bir pozitif sayıdır.`)
}
//  3 bir pozitif sayıdır.
```

Örnek üstünde gördüğünüz gibi, 3 0 dan büyük ve pozitif bir sayı. Yani koşul doğruydu ve ilgili block içindeki kod çalıştı. Ancak koşul yanlış olsaydı, herhangi bir yazı görmeyecektik.

```js
let isRaining = true
if (isRaining) {
  console.log('Yağmurluğunu almayı unutma!')
}
```

 İkinci koşulumuzda da aynı şey geçerli, eğer isRaining değişkeni false ise if bloğu çalışmayacak ve ekranda bir şey görmeyeceğiz. Peki yanlış bir koşulun sonucunu görmek istiyorsak? O zaman _else_ sözcüğünü kullanmamız gerekiyor.

### If - Else (Eğer - Değilse)

Koşul doğruysa if kısmında yazdıklarımız çalışır. Eğer değilse else kısmında yazdıklarımız çalışır.

```js
// syntax
if (kosul) {
  // koşul doğruysa burası çalışır
} else {
  // koşul yanlışsa burası çalışır.
}
```

```js
let num = 3
if (num > 0) {
  console.log(`${num} bir pozitif sayıdır.`)
} else {
  console.log(`${num} bir negatif sayıdır.`)
}
//  3 bir pozitif sayıdır

num = -3
if (num > 0) {
  console.log(`${num} bir pozitif sayıdır.`)
} else {
  console.log(`${num} bir negatif sayıdır.`)
}
//  -3 bir negatif sayıdır.
```

```js
let isRaining = true
if (isRaining) {
  console.log('Sana yağmurluk lazım.')
} else {
  console.log('Sana yağmurluk lazım değil.')
}
// Sana yağmurluk lazım.

isRaining = false
if (isRaining) {
  console.log('Sana yağmurluk lazım.')
} else {
  console.log('Sana yağmurluk lazım değil.')
}
// Sana yağmurluk lazım değil.
```

Son koşul yanlış, o yüzden else kısmında yazılanlar çalıştı. Peki ya iki koşuldan fazlası varsa? İşte o zaman *else if* sözcüğünü kullanabiliriz.

### If - Else if - Else (Eğer - Eğer Değilse - Değilse)

Günlük hayatımızda sürekli kararlar alıyoruz ve bu kararları genelde bir veya iki koşulu değil, birden fazla koşulu kontrol ederek veriyoruz. Günlük hayatımızda olduğu gibi programlamada kararlarla dolu. Birden fazla koşulumuz olduğunda *else if* kullanacağız.

```js
// syntax
if (kosul) {
     // kosul sağlanırsa burası çalışır
} else if (kosul2) {
   // eğer kosul sağlanmazsa ve kosul2 sağlanırsa burası çalışır
} else {
    // hiçbiri sağlanmazsa burası çalışır.

}
```

**Örnek:**

```js
let a = 0
if (a > 0) {
  console.log(`${a} bir pozitif sayıdır.`)
} else if (a < 0) {
  console.log(`${a} bir negatif sayıdır.`)
} else if (a == 0) {
  console.log(`${a} sıfırdır`)
} else {
  console.log(`${a} bir rakam değildir.`)
}
```

```js
// if - else if - else (üçünü de kullanıyoruz.)
let weather = 'gunesli'
if (weather === 'yagmurlu') {
  console.log('Sana yağmurluk lazım.')
} else if (weather === 'bulutlu') {
  console.log('Soğuyabilir, sana ceket lazım.')
} else if (weather === 'gunesli') {
  console.log('Hava güneşli, hiçbir şey almana gerek yok!')
} else {
  console.log('Yağmurluğa ihtiyacın yok.')
}

//sence hangisi çalışacak? kodu yazarak test et ve gör!
```

### Switch (Tam olarak Türkçe karşılğı: Değiştirmek)

Switch **if - else if - else** alternatifidir. Switch yazmak için yine aynı şeylere ihtiyaç duyarsınız. *Switch* sözcüğü, parantez ve süslü parantezler. Switch süslü parantezler içerisine birden fazla farklı koşullar yazabiliriz. Switch içinde koşullarımızı belirtmek için ise *case* sözcüğünü kullanırız. Eğer case'de yazdığımız koşul ile switch parantezleri içerisindeki değerimiz eşleşirse, ilgili case çalıştırılır. *break* sözcüğünü ise, eğer ilgili koşul sağlanırsa kodun daha fazla devam etmemesi için kullanırız. *default* sözcüğünü ise *else* gibi düşünebilirsin; Eğer switch içerisindeki case'lerin hiçbir koşulu uyuşmazsa *default* çalıştırılır.

```js
switch(caseValue){
  case 1:
    // koşul sağlandığında yürütülecek kod.
    break
  case 2:
   // koşul sağlandığında yürütülecek kod.
   break
  case 3:
  // koşul sağlandığında yürütülecek kod.
  default:
   // koşul sağlandığında yürütülecek kod.
}
```

```js
let weather = 'bulutlu' // switch içerisindeki değerimizi "bulutlu" olarak belirledik.

switch (weather) {
  case 'yagmurlu':
    console.log('Yağmurluğa ihtiyacın var.')
    break
  case 'bulutlu':
    console.log('Soğuk olabilir, cekete ihtiyacın var.')
    break
  case 'gunesli':
    console.log('Hava güzel, özgürce dolaş!')
    break
  default:
    console.log('Yağmurluğa ihtiyacın yok.')
}
// Soğuk olabilir, cekete ihtiyacın var.

// Daha fazla switch örneği - bu sefer ingilizce ilerleyelim :)
let dayUserInput = prompt('What day is today ?')
let day = dayUserInput.toLowerCase()

switch (day) {
  case 'monday':
    console.log('Today is Monday')
    break
  case 'tuesday':
    console.log('Today is Tuesday')
    break
  case 'wednesday':
    console.log('Today is Wednesday')
    break
  case 'thursday':
    console.log('Today is Thursday')
    break
  case 'friday':
    console.log('Today is Friday')
    break
  case 'saturday':
    console.log('Today is Saturday')
    break
  case 'sunday':
    console.log('Today is Sunday')
    break
  default:
    console.log('It is not a week day.')
}

```

// koşullarda case örnekleri

```js
let num = prompt('Enter number');
switch (true) {
  case num > 0: //num sıfırdan büyükse
    console.log('Number is positive');
    break;
  case num == 0:
    console.log('Numbers is zero');
    break;
  case num < 0:
    console.log('Number is negative');
    break;
  default:
    console.log('Entered value was not a number');
}
```

### Ternary Operators (Türkçe karşılığı: Üçlü Operatörler)

Ben buna kısa if kullanımı diyorum. Genel de google'a short if yazınca da çıkıyor.

Bir başka koşul yazma yolu ise ternary operators. Bunu diğer bölümlerde ele aldık fakat burada da belirtmeliyiz.

```js
let isRaining = true
isRaining
  ? console.log('Yağmurluğa ihtiyacın var.')
  : console.log('Yağmurluğa ihtiyacın yok.')
```

🌕 Harikasın. 4. günü bitirdin ve başarıya giden yolda şimdi 4 adım öndesin. İşte sana biraz egzersiz:

## 💻 Egzersizler

### Egzersizler: Level 1

1. Get user input using prompt(“Enter your age:”). If user is 18 or older , give feedback:'You are old enough to drive' but if not 18 give another feedback stating to  wait for the number of years he neds to turn 18.

   ```sh
   Enter your age: 30
   You are old enough to drive.

   Enter your age:15
   You are left with 3 years to drive.
   ```

1. Compare the values of myAge and yourAge using if … else. Based on the comparison and log the result to console stating who is older (me or you). Use prompt(“Enter your age:”) to get the age as input.

   ```sh
   Enter your age: 30
   You are 5 years older than me.
   ```

1. If a is greater than b return 'a is greater than b' else 'a is less than b'. Try to implement it in to ways

    - using if else
    - ternary operator.

    ```js
      let a = 4
      let b = 3
    ```

    ```sh
      4 is greater than 3
    ```

1. Even numbers are divisible by 2 and the remainder is zero. How do you check, if a number is even or not using JavaScript?

    ```sh
    Enter a number: 2
    2 is an even number

    Enter a number: 9
    9 is is an odd number.
    ```

### Egzersizler: Level 2

1. Write a code which  can give grades to students according to theirs scores:
   - 80-100, A
   - 70-89, B
   - 60-69, C
   - 50-59, D
   - 0-49, F
1. Check if the season is Autumn, Winter, Spring or Summer.
   If the user input is :
   - September, October or November, the season is Autumn.
   - December, January or February, the season is Winter.
   - March, April or May, the season is Spring
   - June, July or August, the season is Summer
1. Check if a day is weekend day or a working day. Your script will take day as an input.

```sh
    What is the day  today? Saturday
    Saturday is a weekend.

    What is the day today? saturDaY
    Saturday is a weekend.

    What is the day today? Friday
    Friday is a working day.

    What is the day today? FrIDAy
    Friday is a working day.
  ```

### Egzersizler: Level 3

1. Write a program which tells the number of days in a month.

  ```sh
    Enter a month: January
    January has 31 days.

    Enter a month: JANUARY
    January has 31 day

    Enter a month: February
    February has 28 days.

    Enter a month: FEbruary
    February has 28 days.
  ```

1. Write a program which tells the number of days in a month, now consider leap year.


🎉 TEBRİKLER ! 🎉