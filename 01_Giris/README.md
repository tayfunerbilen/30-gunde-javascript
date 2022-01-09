# 📔 1. Gün
## Giriş

30 günde javascript öğrenme challenge'ına başlamaya karar verdiğiniz için tebrik ederim. Bu challenge'da javascript geliştiricisi olmak için gereken her şeyi öğreneceksiniz. Genel olarak, tüm programlama konseptini diyebiliriz. Challenge sonunda orijinal repodaki gibi benden bir bitirme sertifikası alamayacaksınız :D Eğer yardıma ihtiyacınız olursa ya da birilerine yardımcı olmak isterseniz prototurk'un [telegram grubuna](https://t.me/prototurk) katılmayı unutmayın.

30 günde javascript, yeni başlayan ve hali hazırda bilgisi olan javascript geliştiricileri için bir rehber niteliğindedir. Javascript dünyasına hoşgeldiniz! Javascript web'in dilidir. Ben kullanırken ve öğretirken zevk alıyorum, umarım bir gün sizde aynı şerefe nail olursunuz :)

Bu adım adım challenge'da, insanlık tarihinin en popüler dilini yani Javascript'i öğreneceksiniz. Javascript **web sayfalarına interaktiflik katmak**, **mobil ve masaüstü uygulamalar geliştirmek**, **oyunular geliştimek** ve hatta şu günlerde **makina öğrenmesi** ve **yapay zeka** alanlarında da kullanılmaktadır. Popülerliğini yıllar içinde artırmış ve yıllardır bu popülerliğini korumayı başarmıştır. Ayrıca github'da en çok kullanılan dil olduğunuda hatırlatmak isterim.

## Gereksinimler

Bu challenge için programlama bilgisine ihtiyacınız yok. Tek ihtiyacınız:

1. Motivasyon
2. Bir bilgisayar
3. İnternet
4. Bir tarayıcı
5. Bir kod editörü

## Kurulum

Eminim geliştirici olmak için bir bilgisayarınız, internetiniz ve gerekli motivasyon ve isteğiniz bulunuyordur. Eğer bunlara sahipseniz, başlamak için hazırsınız demektir.

### Node.js Kurulumu

Şu an için node.js'e ihtiyacınız olmayabilir ancak daha sonrası için ihtiyacınız olacaktır. Node.js'i [buradan](https://nodejs.org/en/) indirin ve kurun.

![](https://raw.githubusercontent.com/Asabeneh/30-Days-Of-JavaScript/master/images/download_node.png)

İndirdikten sonra çift tıklayıp kurulumu gerçekleştirin.

![](https://raw.githubusercontent.com/Asabeneh/30-Days-Of-JavaScript/master/images/install_node.png)

Bilgisayarınıza node'un yüklenip yüklenmediğini kontrol etmek için terminalinizi açıp şu komutu çalıştırabilirsiniz.

```
node -v
# v14.18.1
```

Bu dökümanı hazırlarken Node'un 14.18.1 sürümünü kullanıyordum, siz de daha yeni sürümü olabilir.

### Tarayıcı

Kullanabileceğiniz bir çok tarayıcı bulunuyor. Ancak, ben sizlere Google Chrome kullanmanızı tavsiye ediyorum.

#### Google Chrome'u Yükleme

Eğer [Google Chrome](https://www.google.com/chrome/) bilgisayarınızda yüklü değilde indirip kolayca yükleyebilirsiniz. Küçük basit javascript kodlarımızı tarayıcının konsolunda yazıyoruz, ancak uygulama geliştirmek için tabiki de tarayıcı konsollarını kullanmıyoruz.

![](https://raw.githubusercontent.com/Asabeneh/30-Days-Of-JavaScript/master/images/google_chrome.png)

#### Google Chrome Konsolunu Açmak

Google Chrome konsolunu açmak için sağ üstte bulunan üç noktaya basıp **Diğer Araçlar > Geliştirici Araçları** adımlarını takip edebilir ya da klavye kısayollarını kullanabilirsiniz.

![](https://raw.githubusercontent.com/Asabeneh/30-Days-Of-JavaScript/master/images/opening_developer_tool.png)

Klavye kısayolları:

```
Mac
Command + Option + J

Window
CTRL + Shift + J
```

Ayrıca J yerine C'yi kullanarak konsol açıldığında seçim işlemini de hızlıca gerçekleştirebilirsiniz ama bunun konumuzla bir ilgisi yok ek bilgi vermek istedim :)

![](https://raw.githubusercontent.com/Asabeneh/30-Days-Of-JavaScript/master/images/opening_chrome_console_shortcut.png)

Google Chrome konsolunu açtıktan sonra, yukarı görselde işaretlenmiş butonları keşfetmeye bakın. Zamanımızın çoğunu **Console** sekmesinde harcayacağız. Console, javascript'i yazacağımız alandır. Google Chrome V8 motoru, javascript kodumuzu alıp makina diline çevirir. Gelin ilk basit javascript kodumuzu konsolda yazalım.

![](https://raw.githubusercontent.com/Asabeneh/30-Days-Of-JavaScript/master/images/js_code_on_chrome_console.png)

#### Tarayıcı Konsolunda Kod Yazmak

Herhangi bir javascript kodunu Google ya da herhangi bir tarayıcı konsolunda yazabiliriz. Ama, bu challenge'da biz Google Chrome konsoluna odaklanacağız. Konsolu şu kısayolu kullanarak açın.

```
Mac
Command + Option + J

Window
CTRL + Shift + J
```

##### Console.log

İlk javascript kodumuzu yazmak için, yerleşik fonksiyon olan `console.log()` fonksiyonunu kullanıyoruz. Parametre olarak bir değer alıyor ve fonksiyon geriye bu değeri basıyor. **Hello World** değerini fonksiyona parametre olarak geçtik.

```js
console.log('Hello World')
```

##### Console.log'a birden fazla parametre göndermek

`console.log()` fonksiyonu virgüllerle ayrılacak şekilde birden fazla parametre alabilir. Yani aynı fonksiyon içinde birden fazla değeri konsola basabiliriz. Sözdizi ise şöyledir: `console.log(param1, param2, param3, paramN...)`

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/console_log_multipl_arguments.png)

```js
console.log('Hello', 'World', '!')
console.log('HAPPY', 'NEW', 'YEAR', 2020)
console.log('Welcome', 'to', 30, 'Days', 'Of', 'JavaScript')
```

Yukarıdaki yazdığımız koddan da göreceğiniz üzere, `console.log()` birden fazla parametre alabilir.

Tebrikler! İlk javascript kodunuzu `console.log()` kullanarak yazdınız.

##### Konsolun amacı

Bu noktada yeni başlayanlar neden konsolda gözükecek bir kod yazdığımızı merak etmiş olabilirler, ilerleyen süreçte javascript ile kod yazarken kodlarımızı **debug** etmek için yani hangi data geliyor, yaptığımız işlem bize ne dönüyor vs. gibi görmek için sıkça konsolu kullanacağız.

##### Yorumlar

Kodlarımıza yorum satırları ekliyoruz. Yorum satırları, kodları daha okunabilir kılmak ve ne işe yaradıklarını belirtmek için çok önemlidir. Özellikle yeni başladıysanız unutmamak için yazdığınız kodların altına ya da üstüne yorum satırı olarak ne işe yaradığını yazabilirsiniz. Javascript, yorum satırlarını kodlarımızla birlikte çalıştırmayacaktır. Yani yorum satırları içine bir javascript ifadesi bile yazsanız çalıştırılmazlar. Amaç sadece yazan ya da projeye sonradan dahil olacak kişilerin işini kolaylaştırmaktır. Javascript'de `//` ile başlayan ya da `/* */` içine yazılan herhangi bir tanım yorun satırı olarak yorumlanır.

**Tek satır yorum örnekleri**

```js
// This is the first comment
// This is the second comment
// I am a single line comment
```

**Çok satırlı yorum örneği**

```js
/* 
  This is a multiline comment
  Multiline comments can take multiple lines
  JavaScript is the language of the web
*/
```

##### Sözdizimi (Syntax)

Programlama dilleri, insan dillerine çok benzerdir. İngilizce ya da diğer bir çok dilde anlamlı bir cümle kurmak için kelimeler, deyimler vb. kalıplar kullanılır. İngilizcede sözdiziminin anlamı, bir dilde iyi cümleler kurmak için kelimelerin ve deyimlerin düzenlenmesidir. Sözdiziminin teknik tanımı ise, bilgisayar dilindeki ifadelerin yapısıdır. Her programlama dili sözdizimine sahiptir. Javascript'de diğer tüm programlama dillerinde olduğu gibi kendine has bir sözdizimine sahiptir. Eğer Javascript'in anlamayacağı bir şekilde kod yazarsak, bize hata fırlatacaktır. Farklı javascript hatalarına daha sonra bakacağız, şimdilik sözdizimi hatalarına bir gözatalım.

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/raising_syntax_error.png)

1. Tırnak kapatırken başlangıçta hangi tırnak kullanıldıysa onunla kapatılmalıdır.
2. Tırnak ile açılmış bir değer varsa mutlaka tırnak ile kapatılmalıdır.
3. `console.log()` fonksiyonunda sondaki parantez mutlaka kapatılmalıdır.

Yukarıda bilerek hata yapılmıştır. Sonuç olarak, konsol bana yazım hatalarıyla ilgili hatalar gösterdi. Aslına bakarsanız, sözdizimi hataları çok bilgilendirici. Ne tarz bir hata yaptığımızla ilgili bizi bilgilendiriyor. Sadece bu hata mesajlarını okuyup yorumlayarak bile hatalarımızı düzeltebiliriz. Bu yüzden buradaki hataları görmezden gelmeyin, bir hata aldığınızda en kötü ihtimalle o hatayı kopyalayıp internette çözümünü aratın, sizden önce bu hatayı almış ve çözüme kavuşmuş olduğunu göreceksiniz.

Şu ana kadar `console.log()` ile konsola metin yazdırmayı öğrendik. Eğer bir metin yazdırıyorsak, yazı tek tırnak, çift tırnak ya da backtick karakterleri içinde olmalıdır. Örneğin;

```js
console.log('Hello World')
console.log("Hello World")
console.log(`Hello World`)
```

#### Aritmatik İşlemler

Number veri türünü daha iyi anlamak için `console.log()` u kullanarak chrome console'da daha fazla pratik yapalım. Metinlere ek olarak, matematiksel işlemleri de javascript'de yapabiliriz. Gelin birkaç basit hesaplama işlemi yapalım. Chrome console'unda `console.log()` kullanmadan parametre gönderip işlem yapabilirsiniz. Ancak, bu örneklerin çoğunu editörde yazacağımız için biz yine de `console.log()` kullanarak işlemlerimize devam edelim. 

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/arithmetic.png)

```js
console.log(2 + 3) // Toplama
console.log(3 - 2) // Çıkarma
console.log(2 * 3) // Çarpma
console.log(3 / 2) // Bölme
console.log(3 % 2) // Modül - Kalanı bulma
console.log(3 ** 2) // Üs alma 3 ** 2 == 3 * 3
```

### Kod Editörü

Kodlarımızı tarayıcı konsolunda yazabiliyoruz gördüğünüz gibi, ancak büyük projeler yazmak için bir editöre ihtiyacımız olacak. Gerçek çalışma ortamlarında, geliştiriciler farklı türde editörler kullanarak geliştirme yapıyorlar. Ben şahsen webStorm IDE'sini tercih ediyorum. Ancak bu challenge'da **Visual Studio Code** editörünü kullanıyor olacağız.

#### VSCode'un Kurulumu

VSCode, çok popüler bir açık kaynaklı kod editörüdür. [Buradan](https://code.visualstudio.com/) indirip kullanmanızı tavsiye ederim, ancak alıştığınız başka bir editör varsa onu kullanmakta da özgürsünüz.

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/vscode.png)

Kurulumu yaptıysanız, kullanmaya başlayabiliriz.

#### VSCode Nasıl Kullanılır?

İkonuna çift tıklayarak vscode'u açın. Açtığnızda, aşağıdaki gibi bir arayüzle açılacaktır. İşaretlenmiş alanlara tıklayıp ne işe yaradıklarına bir bakın.

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/vscode_ui.png)

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/adding_project_to_vscode.png)

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/opening_project_on_vscode.png)

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/scripts_on_vscode.png)

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/vsc_live_server.png)

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/running_script.png)

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/launched_on_new_tab.png)

## Javascript'i Web Sayfasına Eklemek

Javascript web sayfalarına farklı şekillerde eklenebilir.

* Inline (Satır içi)
* Internal (Dahili)
* External (Harici ve Birden Fazla Harici)

Aşağıda her birisi tek tek açıklanmıştır.

### Inline (Satır içi)

Masaüstünüzde **30DaysOfJS** adıyla bir klasör oluşturup içinde `index.html` dosyası oluşturun. Ve aşağıdaki kodu kopyalayıp html dosyanıza yapıştırıp tarayıcınızda açıp bakın.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>30DaysOfScript:Inline Script</title>
  </head>
  <body>
    <button onclick="alert('Welcome to 30DaysOfJavaScript!')">Click Me</button>
  </body>
</html>
```

İlk örneğinizi başarıyla yaptınız. `alert()` bir yerleşik fonksiyon ve ekranda mesaj göstermenizi sağlıyor. `onclick` niteliği ise `button` etiketine tıklandığında içindeki javascript ifadesini çalıştırmanızı sağlıyor.

### Internal (Dahili)

Dahili script'ler `<head>` ya da `<body>` etiketleri içerisinde `<script>` etiketi olarak tanımlanır ve içine javascript kodları yazılır. Tercihen bu tarz işlemleri `<body>` içinde en sonda yazmanız çok daha iyi olacaktır.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>30DaysOfScript:Internal Script</title>
    <script>
      console.log('Welcome to 30DaysOfJavaScript')
    </script>
  </head>
  <body></body>
</html>
```
Yukarıda belirttiğim gibi body içinde yazmak daha çok tercih edilmekte. 

```html
<!DOCTYPE html>
<html>
  <head>
    <title>30DaysOfScript:Internal Script</title>
  </head>
  <body>
    <button onclick="alert('Welcome to 30DaysOfJavaScript!');">Click Me</button>
    <script>
      console.log('Welcome to 30DaysOfJavaScript')
    </script>
  </body>
</html>
```

`index.html` dosyanızı tarayıcıda açıp konsol'da yazdırdığınız mesaja bakabilirsiniz.

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/js_code_vscode.png)

### External (Harici)

Dahili script'lere benzer olarak harici script'lerde `<head>` ya da `<body>` içerisinde `<script>` etiketi ile kullanılır. Yine tercihen body içinde sonda yazılması daha doğrudur. İlk olarak uzantısı `.js` olan bir javascript dosyası oluşturmamız gerekiyor. Tüm javascript dosyaları `.js` uzantısıyla biterler. Proje klasörünüzde `introduction.js` adıyla bir javascript dosyası oluşturup aşağıdaki kodları yazın ve `index.html` de bu dosyanızı çağırın.

```js
// introduction.js
console.log('Welcome to 30DaysOfJavaScript')
```

`<head>` etiketinde çağırılması

```html
<!DOCTYPE html>
<html>
  <head>
    <title>30DaysOfJavaScript:External script</title>
    <script src="introduction.js"></script>
  </head>
  <body></body>
</html>
```

`<body>` etiketinde çağırılması

```html
<!DOCTYPE html>
<html>
  <head>
    <title>30DaysOfJavaScript:External script</title>
  </head>
  <body>
    <!-- head ya da body içinde yer alabilir --> 
    <!-- Burada önerilen yöntemle body içinde kullanıyoruz -->
    <script src="introduction.js"></script>
  </body>
</html>
```

Tarayıcıda açıp konsolda değer gelip gelmediğine bakabilirsiniz. Eğer bu noktada `<head>` ile `<body>` arasındaki farkı anlamadıysanız şöyle açıklayayım, `<head>` içinde bir javascript dosyası çağırırsanız sayfa bu dosyalar yüklenene kadar açılmayacaktır. Bu da sayfanın açılış hızını etkileyecektir, çünkü her javascript dosyası bir istek demek, her istekte bir cevap döndüğü için bu cevap dönene kadar sayfayı açmayacaktır. `<body>` sonunda yazdığımızda ise sayfayı beklemeden açıp daha sonra bu script dosyalarını yükleyecektir. 

Ayrıca `<head>` içinde javascript ile bir html etiketini seçmek istediğinizde ekstra kod yazmanız gerekir. Çünkü dom'un hazır olup olmadığını bilmeli ve hazır olduğunda o etiketi seçmeniz gerekir diğer türlü etiketi seçemezsiniz. Ancak `<body>` içinde en altta yazdığınızda burası çalıştığında dom çoktan hazır olacağı için bu ekstra işleme ihtiyacınız olmayacak.

### Çoklu External (Harici)

Birden fazla javascript dosyasını da aynı yöntemle çağırabilirsiniz. `helloworld.js` adında bir dosya oluşturup içine `console.log()` ile bir şeyler yazdırın ve `index.html` de bu dosyayı da çağırın.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Multiple External Scripts</title>
  </head>
  <body>
    <script src="./helloworld.js"></script>
    <script src="./introduction.js"></script>
  </body>
</html>
```

Birden fazla script'i neden çağırırız? Genelde bir eklenti kullanmak istediniz diyelim, onun javascript dosyasını çağırdınız. Bir de sizin kodlarınızı yazdığınız ana bir javascript dosyanız var, onu her zaman en son çağırdığınızdan emin olun. 

![](https://github.com/Asabeneh/30-Days-Of-JavaScript/raw/master/images/multiple_script.png)

## Veri Türlerine Giriş

Javascript ve diğer programlama dillerinde, birden fazla farklı veri türü bulunur. Şunlar javascript'de ilkel (primitive) veri türleri olarak geçmektedir: _String, Number, Boolean, undefined, Null,_ ve _Symbol._ 

### Numbers (Sayılar)

* Tam sayılar (Integer) : (negatif, sıfır, pozitif) sayılar. Örn: (-3, -2, -1, 0, 1, 5, 100 ...)
* Ondalık sayılar (Floats) : Örn: (-3.5, -1.2, 4.5, 3.14)

### Strings (Metinler)

Tek tırnak, çift tırnak ve backtick karakteri içinde bir ve daha fazla karakterin birleştiği metinler.

```js
'Asabeneh'
'Finland'
'JavaScript is a beautiful programming language'
'I love teaching'
'I hope you are enjoying the first day'
`We can also create a string using a backtick`
'A string could be just as small as one character as big as many pages'
```

### Booleans (Mantıksal)

Boolean değeri `true` ya da `false` olabilir. Herhangi bir karşılaştırma geriye boolean değer döndürür. Örneğin 3'ün 5'e eşit olup olmadığına bakarsak geriye `false` dönecektir. Bu da ileride true-false değerlerine göre başka işlemler yaptırmak için sıkça kullanacağız demek oluyor.

```js
true // ışık açıksa, değer true
false // ışık kapalıysa, değer false
```

### Undefined (Tanımsız)

Javascript'de değişkene bir değer atamazsak, değer `undefined` tani tanımsız olacaktır. Buna ek olarak, bir fonksiyon değer döndürmüyorsa yine undefined döndürüyor aslında, fonksiyon ne yeniyor mu diyorsanız, acele etmeyin ısınıyoruz :)

```js
let firstName
console.log(firstName) // undefined, çünkü henüz bir değer atanmamış
```

### Null

Javascript'de null boş değer anlamına gelir.

```js
let emptyValue = null
```

## Veri Türlerinin Kontrolü

Bir değişkenin taşıdığı veri türünü öğrenmek için `typeof` operatörünü kullanıyoruz. Örneğin;

```js
console.log(typeof 'Asabeneh') // string
console.log(typeof 5) // number
console.log(typeof true) // boolean
console.log(typeof null) // object türü
console.log(typeof undefined) // undefined
```

## Yorumlar (Tekrar)

Unutmayın, diğer programlama dillerine benzer olarak Javascript'te yorum satırlarına sahip. Yorum yazmak kodunuzu daha okunur kılacaktır. İki farklı şekilde yorum tanımlanabilir.

* Tek satırlı
* Çok satırlı

```js
// commenting the code itself with a single comment
// let firstName = 'Asabeneh'; single line comment
// let lastName = 'Yetayeh'; single line comment

/*
  let location = 'Helsinki';
  let age = 100;
  let isMarried = true;
  This is a Multiple line comment
*/
```

## Değişkenler

Bir değeri hafızada tutmak ve istediğiniz yerde kullanmak isterseniz bunu değişkenler aracılığıyla yapıyorsunuz. Değişkenler, hafızada değerleri depolarlar. Bir değişken tanımlandığında, hafızada yeri ayrılır. Bir değer atandığında ise, hafızadaki ayrılan yeri bu değerle doldurulur. Değişken tanımlamak için `var`, `let` ve `const` anahtar kelimeleri kullanılır.

Eğer değişkenin değeri zamanla değişebilir bir değerse `let`, eğer değişmez bir değeri varsa `const` ile değişken tanımlayabilirsiniz. Örneğin PI sayısı, ülke adı, yer çekimi gibi sabit değerler değişmeyeceği için `const` ile tanımlanabilir. `let` için ise örneğin maaş, yaş, boy gibi değişebilir değerleri örnek verebiliriz. Elbette bu örnekler gerçek hayattan, programlama yaparkende tek yaptığımız gerçek hayatı sanala aktarmak aslında, o yüzden bu örneklerde yeterince bilgilendirici olabiliyor. `var` anahtar kelimesini kullanarak değişken tanımlamayacağız, artık önerilmiyor, hataya açık ve çok fazla sorun çıkarabilir. Bunu bir başka bölümde konuşuyor olacağız.  Şimdilik bu kadar açıklama yeterli.

Geçerli bir javascript değişkeni tanımlarken şunlara dikkat edilmelidir:

* Değişken adı sayı ile başlayamaz.
* Değişkan adı $ ve _ karakterleri hariç özel karakter içeremez.
* Değişken adları camelCase olarak tanımlanmalıdır. (Zorunlu değil ancak genel görüş bu yönde olduğu için siz de bu mantıkta tanımlayabilirsiniz)
* Değişken tanımlarken kelimeler arası boşluk olmamalıdır. Yani "full name" için bir değişken tanımlarken `fullName` şeklinde isimlendirilmelidir.

**camelCase** - İlk kelime hariç her kelimenin baş harfi büyük olacak şekilde yazılması. Örn: _getUserName_ ya da _getElementById_ vb.

Aşağıda geçerli javascript değişken isimlerini inceleyebilirsiniz:

```
firstName
lastName
country
city
capitalCity
age
isMarried

first_name
last_name
is_married
capital_city

num1
num_1
_num_1
$num1
year2020
year_2020
```

Yukarıdaki listede ilk ve ikinci isimler camelCase tarzında yazılmıştır, biz de bu şekilde yazmaya devam edeceğiz isimlendirmelerimizi. 

Hatalı değişken isimlerine örnekler ise şöyle:

```
first-name
1_num
num_#_1
```

Artık değişkenleri farklı veri türleri ile tanımlamaya başlayabiliriz. Değişken tanımlamak için `let` ya da `const` anahtar değerini kullandıktan sonra değişkenın adını belirtiyoruz. Değişken adından sonrada = işareti (atama operatörü) kullanarak ona bir değer atıyoruz.

```js
// Sözdizimi
let buBirDegiskenAdi = deger
```

**Farklı veri türlerinde tanımlanmış değişkenlere örnekler**

```js
let firstName = 'Asabeneh' // kişinin adı
let lastName = 'Yetayeh' // kişinin soyadı
let country = 'Finland' // ülkesi
let city = 'Helsinki' // başkenti
let age = 100 // yaşı
let isMarried = true // medeni durumu

console.log(firstName, lastName, country, city, age, isMarried)
// çıktı: Asabeneh Yetayeh Finland Helsinki 100 true
```

**Sayısal değerlerle değişken tanımlama örnekleri**

```js
let age = 100 // yaş
const gravity = 9.81 // yerçekimi
const boilingPoint = 100 // suyun kaynama noktası
const PI = 3.14 // geometrik sabit

console.log(gravity, boilingPoint, PI)
// çıktı: 9.81 100 3.14
```

Her değişken tanımlamasında başına `let` ya da `const` koymanıza gerek yok. Virgül ile ayırarak tek tanım ilede değişkenleri tanımlayabilirdik.

```js
let name = 'Asabeneh',
    job = 'teacher',
    live = 'Finland'

console.log(name, job, live)
// çıktı: Asabeneh teacher Finland
```

🌕 Harikasın! 1. günü tamamladın ve mükemmeliğe giden yoldasın. Beyin kaslarının çalışması ve tembelleşmemek için bazı egzersizler yapmak isteyebilirsin 1. günde öğrendiklerinle ilgili.

# 💻  1. Gün Egzersizleri

1. "yorum satırları kodları daha okunur kılar" yazan bir tek satırlık yorum satırı tanımlayın.
2. "30 günde javascripte hoşgeldin" yazan bir tek satırlık yorum satırı tanımlayın.
3. "yorum satırları kodları daha okunur kılar ve ne işe yaradığı hakkında bizi bilgilendirir" yazan bir çok satırlık yorum satırı tanımlayın.
4. `variable.js` adında bir dosya oluşturup içine _string, boolean, undefined, null_ veri tiplerini içeren değişkenler tanımlayın.
5. `datatypes.js` adında bir dosya oluşturup değişkenlerin türlerini `typeof` ile kontrol edin. Her bir değişkeni tek tek kontrol edin.
6. Dört farklı değişkeni değer atamadan tanımlayın
7. Dört farklı değişkeni değer atayarak tanımlayın
8. Adınızı, soyadınızı, yaşınızı ve medeni durumunuzu belirten 4 değişkeni tek tek oluşturun.
9. Adınızı, soyadınızı, yaşınızı ve medeni durumunuzu belirten 4 değişkeni tek seferde oluşturun.
10. `myAge` ve `yourAge` adında iki değişken tanımlayın, başlangıç değerlerini belirtin ve tarayıcı konsoluna bu değerleri şu şekilde basın:
  ```
  I am 25 years old.
  You are 30 years old.
```

🎉  TEBRİKLER ! 🎉

[2. Gün >>](/02_Veri_Turleri/README.md)
