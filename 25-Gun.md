# 25. Gün

Seriye kaldığımız yerden devam ediyoruz ve bugünde farklı farklı özellikleri öğrenmeye devam edeceğiz.

## `preventDefault`

Bazı etiketlerin varsayılan davranışları vardır. Örneğin bir `a` etiketine basınca ilgili linke yönlendirilirsiniz, ya da form içinde tipi submit olan bir `button` a basınca formu gönderir vs. Bu gibi varsayılan davranışları engellemek için `preventDefault` kullanabilirsiniz. Örneğin;

```html
<a href="about.html">Hakkimda</a>
<a href="https://prototurk.com">prototurk.com</a>
<script>
	const aTags = document.querySelectorAll('a')
	aTags.forEach(a => {
		a.addEventListener('click', e => {
			// eger link dis bir baglanti iceriyorsa
			// varsayilan davranisi engelle
			if (e.target.getAttribute('href').includes('http')) {
				if (!confirm('Guvenli olmayan bir siteye gitmeye calisiyorsunuz?')) {
					e.preventDefault()
				}
			}
		})
	})
</script>
```

## `stopPropagation`

Varsayılan yayılmayı engellemek içinse bu özellik kullanılır. Bunu bir örnekle anlatmak gerekirse, iç içe 3 tane etiketimiz olduğunu düşünelim. Ve bu 3 etiketin de bir `click` olayı olsun. Eğer 3. etikete tıklarsam, ne olmasını beklerim? Gelin bir bakalım.

```html
<div class="test1">
    test1
    <div class="test2">
        test2
        <div class="test3">test3</div>
    </div>
</div>
<script>
	const test1 = document.querySelector('.test1')
	const test2 = document.querySelector('.test2')
	const test3 = document.querySelector('.test3')

    test2.addEventListener('click', e => console.log('test2 tiklandi'))
    test1.addEventListener('click', e => console.log('test1 tiklandi'))
    test3.addEventListener('click', e => console.log('test3 tiklandi'))
</script>
```

Evet eğer `test3` e tıklarsam sırasıyla 3, 2 ve 1. etiketlerin console değerlerini görüyorum. Ama bazı durumlarda ben sadece test3'e tıkladığım olayın çalışmasını ve yayılmayı durdurmak isteyebilirim. İşte o zaman şöyle bir kod yazmam yeterliydi.

```js
test3.addEventListener('click', e => {
    e.stopPropagation()
    console.log('test3 tiklandi')
})
```

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

### `removeProperty()`

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

### `getPropertyValue()`

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

### `getPropertyPriority()`

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

## `designMode`

Bir belgenin tasarım modunda olup olmadığını belirlememizi sağlar.

```js
document.designMode = 'on'
```

## `selectionStart` ve `selectionEnd`

Kullanıcıdan bilgi aldığımız `input` ve `textarea` elemanlarında seçilen yazının başlangıç ve bitiş indis değerlerini döndürür. Örneğin textarea içinde seçilen yazıyı şöyle konsola basabilirdik.

```html
<textarea id="test-textarea">textarea mesela</textarea>
<script>
  const textarea = document.getElementById('test-textarea')

  textarea.addEventListener('select', () => {
      console.log(
          textarea.value.substring(
              textarea.selectionStart,
              textarea.selectionEnd
          )
      )
  })
</script>
```

##  `setRangeText()`

Başlangıç ve bitiş indislerine göre seçilen değeri belirlene değer ile değiştirir. Yukarıdaki örneğimizi biraz daha genişletelim.

```html
<textarea id="test-textarea">textarea mesela</textarea>
<button class="button" data-type="bold">Kalın Yap</button>
<button class="button" data-type="italic">Eğik Yap</button>
<script>
	const textarea = document.getElementById('test-textarea')
	const buttons = document.querySelectorAll('.button')
	const selection = {}

	buttons.forEach(button => button.addEventListener('click', e => {
		let selected = textarea.value.substring(
			selection.start,
			selection.end
		)
		switch (e.target.dataset.type) {
			case 'bold':
				selected = `<b>${selected}</b>`
				break
			case 'italic':
				selected = `<i>${selected}</i>`
				break
		}
		textarea.focus()
		textarea.setRangeText(
			selected,
			selection.start,
			selection.end,
			'end'
		)
	}))

	textarea.addEventListener('select', () => {
		selection.start = textarea.selectionStart
		selection.end = textarea.selectionEnd
	})
</script>
```

Metodun 4. parametresinde seçimden sonraki konumu ayarlanıyor.
- `select` - eklme yaptıktan sonra ekleneni seçer
- `start` - ekleme yaptıktan sonra eklenenin başını seçer
- `end` - ekleme yaptıktan sonra eklenenin sonunu seçer

## `setSelectionRange()`

Belirlenen başlangıç ve bitiş değerlerini `input` ya da `textarea` içinde seçilmesini sağlar.

```html
<textarea id="test-textarea">textarea mesela</textarea>
<button id="button">Belli Bir Yazıyı Seç</button>
<script>
	const textarea = document.getElementById('test-textarea')
	const button = document.getElementById('button')

	button.addEventListener('click', () => {
		textarea.focus()
		textarea.setSelectionRange(9, 11)
	})
</script>
```

## `stepUp()` ve `stepDown()` metodları

`input` etiketinde tipi `number`, `time`, `date`, `range`, `month`, `week` olan bütün etiketlerin değerlerini azaltmak ve artırmak için kullanılır.

```html
<input type="time" max="17:00" step="900"/> <br>
<input type="date" max="2019-12-25" step="7"/> <br>
<input type="month" max="2019-12" step="12"/> <br>
<input type="number" max="50" step="5"> <br>
<input type="range" value="1" max="10" min="-4">

<hr>

<button id="increment-button">Artır</button>
<button id="decrement-button">Azalt</button>
<script>
	const inputs = document.querySelectorAll('input')
	const incrementButton = document.getElementById('increment-button')
	const decrementButton = document.getElementById('decrement-button')

	incrementButton.addEventListener('click', () => {
		inputs.forEach(input => {
			input.stepUp()
		})
	})

	decrementButton.addEventListener('click', () => {
		inputs.forEach(input => {
			input.stepDown()
		})
	})
</script>
```

## `showPicker()`

Farklı tiplerdeki inputların dialoglarını açmak için kullanılır.

```html
<input type="color"/>
<input type="file"/>
<input type="date"/>
<button>Show All</button>
<script>
	const input = document.querySelector('input')
	const button = document.querySelector('button')

	button.addEventListener('click', async () => {
		await input.showPicker()
	})
</script>
```
