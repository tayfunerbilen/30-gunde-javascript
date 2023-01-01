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
