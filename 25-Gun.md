# 25. Gün

Seriye kaldığımız yerden devam ediyoruz ve bugünde farklı farklı özellikleri öğrenmeye devam edeceğiz.

## `CSSStyleDeclaration`

Javascript'de css özellikleri eklemek için `style` objesi içinde tanımlamayı öğrenmiştik. Gelin bir de bunları metodlar yardımıyla nasıl yapabileceğimize bir bakalım.

### `setProperty()`

Belirtilen css özelliği tanımlamamızı sağlar. 3. parametre olarak `important` olup olmadığını belirtebiliriz.

```html
<h1>prototurk.com</h1>
<style>
    h1 {
        color: red !important;
    }
</style>
<script>
    const h1 = document.querySelector('h1')
    h1.style.setProperty('color', 'blue')
    //h1.style.setProperty('color', 'blue', 'important')
</script>
```

## `removeProperty()`

Seçilen css özelliğini kaldırır. 

```html
<h1>prototurk.com</h1>
<style>
    h1 {
        color: red !important;
    }
</style>
<script>
    const h1 = document.querySelector('h1')
    h1.style.removeProperty('color')
</script>
```

## `getPropertyValue()`

Seçilen css özelliğinin değerini döndürür.

```html
<h1>prototurk.com</h1>
<style>
    h1 {
        color: red !important;
    }
</style>
<script>
    const h1 = document.querySelector('h1')
    console.log(
      h1.style.getPropertyValue('color')
    )
</script>
```

## `getPropertyPriority()`

Seçilen css özelliğinin `important` olup olmadığını döndürür. Çok önemli bir metod değil ancak bir gün mutlaka işe yarayacağı bir yer çıkar, bilmekte fayda var.

```html
<h1>prototurk.com</h1>
<style>
    h1 {
        color: red !important;
    }
</style>
<script>
    const h1 = document.querySelector('h1')
    console.log(
      h1.style.getPropertyPriority('color') === 'important' ? 'important kullanilmis' : 'cokta onemli degil!'
    )
</script>
```

## `MediaQueryList`

Medya sorguları css'de responsive tasarım yaparken kullandığımız sorgulardır. Bunu javascript tarafında da kullanmak istediğimizde bize birkaç yararlı metod vermekte. Gelin bunlara birlikte bir bakalım.

### `window.matchMedia()`

Bir medya sorgusu yazmamıza sağlar. Örneğin sayfa genişliğimiz 480px altında mı değil mi onu kontrol edelim.

```js
const mq = window.matchMedia('(max-width: 480px)')
console.log(mq.matches) // true ya da false
console.log(mq.media) // sorgumuzun değeri
```

Eğer bu değişikliği sürekli takip etmek istersek `change` olayını dinleyebiliriz. Yani;

```js
const mq = window.matchMedia('(max-width: 480px)')

mq.addEventListener('change', e => {
  console.log(e.matches) // eşleşip eşleşmediğini döndürür
})
```

..... DEVAM EDECEK .....
