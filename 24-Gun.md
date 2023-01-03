# 24. Gün (Element)

30 günde javascript serisinin 23. gününde temel javascript konuları bitiyor ve son 7 gün örnek uygulamalar üzerine. Ancak örnek uygulamalar çok matah olmadığı için ben seriyi biraz daha genişletmeye karar verdim.

Bu yüzden 24. günde Element objesinden ve bunun değerlerinden bahsedeceğim.

## Özellikler

### `attributes`

`Element.attributes` özelliği elemana ait nitelikleri döndürür. Dönen değer bir dizi değil `NamedNodeMap` objesidir. Bu yüzden dizi metodları kullanılamaz, dönen değerlerin isimleri tarayıcıdan tarayıcıya farklılık gösterebilir.

```html
<h1 style="color: red; background-color: yellow" class="test" id="deneme">prototurk</h1>

<script>
const h1 = document.getelementById('deneme')
const attributes = h1.attributes

for (const attr of attributes) {
  console.log(attr.name, attr.value)
}
</script>
```

### `childElementCount`

Elemanın kaç çocuk öğesi olduğunu döndürür.

```html
<ul class="list">
  <li>Liste 1</li>
  <li>Liste 2</li>
  <li>Liste 3</li>
  <li>Liste 4</li>
</ul>

<script>
console.log(
    document.querySelector('.list').childElementCount
)
</script>
```

### `children`

Elemanın çocuk öğelerini `HTMLCollection` objesi olarak döndürür.

```html
<article>
  <h1>başlık</h1>
  <p>paragraf</p>
  <footer>alt bilgi</footer>
</article>

<script>
const article = document.getElementsByTagName('article')[0]
for (const child of article.children) {
  console.log(child, child.tagName);
}
</script>
```

### `clientHeight` ve `clientWidth`

- `clientHeight` - Elemanın iç yüksekliğini döndürüyor. yükseklik + padding - (varsa) scrollbar yüksekliği değerini döndürüyor. Border ve margin değerlerini hariç tutularak döndürür.
- `clientWidth` - Elemanın iç genişliğini döndürüyor. genişlik + padding - (varsa) scrollbar genişliği değerini döndürüyor. Border ve margin değerlerini hariç tutularak döndürür.

```html
<div class="test" style="padding: 20px; border: 20px solid red">
  <div>eleman 1</div>
  <div style="padding: 10px">eleman 2</div>
  <div>eleman 3</div>
</div>

<script>
console.log(
    document.querySelector('.test').clientHeight
)

console.log(
    document.querySelector('.test').clientWidth
)
</script>
```

### `firstElementChild` ve `lastElementChild`

Adındanda anlaşılacağı üzere ilk ve son elemanları döndürür.

```html
<ul>
  <li>eleman 1</li>
  <li>eleman 2</li>
  <li>eleman 3</li>
  <li>eleman 4</li>
</ul>

<script>
const ul = document.querySelector('ul')

console.log(
    ul.firstElementChild
)

console.log(
    ul.lastElementChild
)
</script>
```

### `nextElementSibling` ve `previousElementSibling`

- `nextElementSibling` - Seçilen elemanın hemen sonrasında gelen elemanı döndürür.
- `previousElementSibling` - Seçilen elemanın hemen öncesinde gelen elemanı döndürür.

```html
<div>div etiketi</div>
<h1 class="title">Başlık</h1>
<p>paragraf</p>

<script>
console.log(
    document.querySelector('.title').nextElementSibling
)
  
console.log(
    document.querySelector('.title').previousElementSibling
)
</script>
```

### `scrollHeight` ve `scrollWidth`

- `scrollHeight` - Elemanın taşan alanlarıda dahil olmak üzere yüksekliğini döndürür.
- `scrollWidth` - Elemanın taşan alanlarıda dahil olmak üzere genişliğini döndürür.

```html
<div class="scroll-content" style="height: 70px; overflow: auto">
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
</div>

<script>
console.log(
    document.querySelector('.scroll-content').scrollHeight
)
</script>
```

```html
<div class="scroll-content" style="width: 200px; display: flex; white-space: nowrap; overflow: auto">
  <div style="width:100px; flex-shrink: 0">test</div>
  <div style="width:100px; flex-shrink: 0">test</div>
  <div style="width:100px; flex-shrink: 0">test</div>
  <div style="width:100px; flex-shrink: 0">test</div>
  <div style="width:100px; flex-shrink: 0">test</div>
  <div style="width:100px; flex-shrink: 0">test</div>
</div>

<script>
console.log(
    document.querySelector('.scroll-content').scrollWidth
)
</script>
```

### `scrollLeft` ve `scrollTop`

- `scrollLeft` - Scroll olan elemanın soldan mesafesini döndürür. Ayrıca soldan mesafesini ayarlamak içinde aynı özellik kullanılır.
- `scrollWidth` - Scroll olan elemanın yukarıdan mesafesini döndürür. Ayrıca yukarıdan mesafesini ayarlamak içinde aynı özellik kullanılır.

```html
<div class="scroll-content" style="height: 70px; overflow: auto">
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
  test <br>
</div>

<script>
document.querySelector('.scroll-content').scrollTop += 100

console.log(
    document.querySelector('.scroll-content').scrollTop
)
</script>
```

```html
<div class="scroll-content" style="width: 200px; display: flex; white-space: nowrap; overflow: auto">
  <div style="width:100px; flex-shrink: 0">test</div>
  <div style="width:100px; flex-shrink: 0">test</div>
  <div style="width:100px; flex-shrink: 0">test</div>
  <div style="width:100px; flex-shrink: 0">test</div>
  <div style="width:100px; flex-shrink: 0">test</div>
  <div style="width:100px; flex-shrink: 0">test</div>
</div>

<script>
document.querySelector('.scroll-content').scrollLeft += 100

console.log(
    document.querySelector('.scroll-content').scrollLeft
)
</script>
```

### `tagName`

Seçilen öğenin etiket ismini döndürür.

```html
<h1 class="test">Başlık</h1>
<p class="test">paragraf</p>
<div class="test">div</div>

<script>
const elements = document.querySelectorAll('.test')
for (const element of elements) {
    console.log(element.tagName)
}
</script>
```

## Metodlar

### `after()` ve `before()`

Seçilen elemanın öncesine ve sonrasına öğe eklemek için kullanılır.

```html
<div id="test">test div</div>

<script>
let div = document.getElementById('test')

let h1 = document.createElement('h1')
h1.textContent = 'baslik'

let p = document.createElement('p')
p.textContent = 'paragraf'

div.before(h1)
div.after(p)
</script>
```

### `append()` ve `prepend()`

Seçilen elemanın başına ve sonuna öğe eklemek için kullanılır. `after()` ve `before()` metodlarından farklı olarak bu iki metod ile seçilen öğenin içinde öncesine ve sonrasına öğeler eklenir.

```html
<div id="test" style="border: 10x solid red">test div</div>

<script>
let div = document.getElementById('test')

let h1 = document.createElement('h1')
h1.textContent = 'baslik'

let p = document.createElement('p')
p.textContent = 'paragraf'

div.prepend(h1)
div.append(p)
</script>
```

### `closest()`

Seçilen elemana en yakın belirtilen öğeyi döndürür.

```html
<ul>
  <li>liste</li>
  <li>liste</li>
  <li>
    liste
    <ul>
      <li>liste</li>
      <li>liste</li>
      <li>liste</li>
      <li>
        liste
        <ul>
          <li>liste</li>
          <li>liste</li>
          <li>liste</li>
        </ul>
      </li>
    </ul>
  </li>
  <li>liste</li>
  <li>liste</li>
</ul>

<script>
const liElements = document.querySelectorAll('li')

for (const li of liElements) {
    li.addEventListener('click', e => {
        //e.stopPropagation()
        console.log(
            li.closest('ul')
        )
    })
}
</script>
```

### `getBoundingClientRect()`

Seçilen öğenin boyutlarını ve pozisyon bilgilerini DOMRect objesi olarak döndürür.

```html
<div id="test">
  test div
</div>

<script>
console.log(
    document.getElementById('test').getBoundingClientRect()
)
</script>
```

### `matched()`

Seçilen elemanın belirtilen css seçicisiyle eşleşip eşleşmediğini kontrol eder.


```html
<button type="button">buton</button>
<button type="submit">submit button</button>
<button type="reset">reset button</button>
<button disabled type="submit">disabled submit button</button>

<script>
const buttons = document.querySelectorAll('button')

for (const button of buttons) {
    // tipi submit olan ve disabled olan oge olup olmadini kontrol et
    console.log(
        button.matches('[type=submit][disabled]'),
        button
    )
}
</script>
```

### `setAttribute()`

Seçilen elemana belirtilen niteligi ekler.

```html
<a href="https://prototurk.com">prototurk</a>

<script>
const a = document.querySelector('a')
a.setAttibute('target', '_blank')
</script>
```

### `getAttribute()`

Seçilen elemana ait belirtilen niteligi dondurur.

```html
<a href="https://prototurk.com">prototurk</a>

<script>
const a = document.querySelector('a')
console.log(
    a.getAttribute('href')
)
</script>
```

### `hasAttribute()`

Seçilen elemana ait belirlenen niteliğin olup olmadığını kontrol eder.

```html
<a href="https://prototurk.com">prototurk</a>
<a href="https://youtube.com/prototurkcom" title="Prototurk youtube kanalı">prototurk youtube</a>

<script>
const aElements = document.querySelectorAll('a')

for (const a of aElements) {
    if (a.hasAttribute('title')) {
        a.style.backgroundColor = 'yellow'
    }
}
</script>
```

### `hasAttributes()`

Seçilen elemana ait herhangi bir nitelik olup olmadığını kontrol eder.

```html
<h1>başlık</h1>
<h1 title="örnek başlık">başlık 2</h1>

<script>
const h1Elements = document.querySelectorAll('h1')

for (const h1 of h1Elements) {
    if (!h1.hasAttributes()) {
        h1.style.backgroundColor = 'yellow'
    }
}
</script>
```

### `toggleAttribute()`

Seçilen elemana belirtilen nitelik varsa kaldırılmasını yoksa eklenmesini sağlar.


```html
<input type="text" />
<button>toggle</button>

<script>
const button = document.querySelector('button')
const input = document.querySelector('input')
  
button.addEventListener('click', () => {
  input.toggleAttribute('disabled')
})
</script>
```
