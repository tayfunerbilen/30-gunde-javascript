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



......... devam edecek .........
