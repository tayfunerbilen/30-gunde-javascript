# 26. Gün

## elements

Form öğelerinin tamamını `elements` özelliği ile alabiliriz. Örneğin:

```html
<form action="" id="form1" novalidate>
    <input type="text" name="username"> <br>
    <input type="password" name="password"> <br>
    <button type="submit">Gonder</button>
</form>

<script>
const form1 = document.getElementById('form1')
form1.addEventListener('submit', e => {
	e.preventDefault()
	console.log(e.target.elements)
})
</script>
```

## document.forms

Dökümandaki tüm form elemanlarını döndürür. Ulaşmak için form elemanına verilen id değeri yeterlidir. Örneğin:

```html
<form id="form1"></form>
<form id="form2"></form>

<script>
  console.log(document.forms)
  console.log(document.forms.form2)
</script>
```

## Validation

Form elemanlarının geçerli olup olmadığını kontrol edebildiğimiz bir çok yol olmasına rağmen, size en basit ve javascript'de ekstra kod yazmadan kontrol yapabileceğiniz bazı metod ve objeleri göstermek istiyorum.

### validity

Form elemanına ait validasyon durumlarını döndürür. Örneğin:

```html
<form action="" id="form1" novalidate>
  <input type="text" name="username" required> <br>
  <input type="password" name="password" minlength="3" maxlength="10" required> <br>
  <div>bu div etiketinin hiçbir önemi yok</div>
  <input type="email" name="email" required> <br>
  <button type="submit">Gonder</button>
</form>

<script>
	const form1 = document.getElementById('form1')
	form1.addEventListener('submit', e => {
		e.preventDefault();
		[...e.target.elements].forEach(element => {
			console.log(element.validity)
		})
	})
</script>
```

Validasyon durumları ise şöyle olabilir:

- `badInput` - Değer belirlenen tipten farklı bir değer içeriyorsa true döner. Örneğin tipi number olan bir input'a sayı haricinde bir değer girildiğinde sonucu görebilirsiniz.
- `patternMismatch` - Değer pattern niteliğindeki desen ile eşleşmezse true döner
- `rangeUnderflow` - Değer belirtilen minimum değerinin altındaysa true döner
- `rangeOverflow` - Değer belirtilen maksimum değerinin üstündeyse true döner
- `stepMismatch` - Değer belirtilen step niteliğine uygun değilse true döner
- `tooLong` - Değer belirtilen maxlength değerinden daha uzunsa true döner
- `tooShort` - Değer belirtilen minlength değerinden daha kısaysa true döner
- `typeMismatch` - Değer belirtilen tipe uygun değilse (örn: email, url) true döner
- `valueMissing` - Değer required niteliği belirlenmişse ve boş ise true döner

### validationMessage

Validasyon mesajını döndürür. Örneğin:

```html
<form action="" id="form1" novalidate>
  <input type="text" name="username" required> <br>
  <input type="password" name="password" minlength="3" maxlength="10" required> <br>
  <div>bu div etiketinin hiçbir önemi yok</div>
  <input type="email" name="email" required> <br>
  <input type="number" min="20" max="40" step="2" /> <br>
  <button type="submit">Gonder</button>
</form>

<script>
	const form1 = document.getElementById('form1')
	form1.addEventListener('submit', e => {
		e.preventDefault();
		[...e.target.elements].forEach(element => {
			console.log(element.validationMessage)
		})
	})
</script>
```

### setCustomValidity() ve reportValidity()

Elemana özel validasyon mesajı tanımlamanızı sağlar. Ve elemanın geçerli olup olmadığını kontrol etmenizi sağlar.

```html
<form action="" id="form1" novalidate>
  <input type="text" name="username" required> <br>
  <input type="password" name="password" minlength="3" maxlength="10" required> <br>
  <div>bu div etiketinin hiçbir önemi yok</div>
  <input type="email" name="email" required> <br>
  <input type="number" min="20" max="40" step="2" /> <br>
  <button type="submit">Gonder</button>
</form>

<script>
  function checkValidity(element) {
		if (element.validity.badInput) {
			element.setCustomValidity('Geçersiz bir değer girdiniz')
		} else if (element.validity.patternMismatch) {
			element.setCustomValidity('Geçersiz bir format girdiniz')
		} else if (element.validity.rangeUnderflow) {
			element.setCustomValidity('Minimum değerden daha az')
		} else if (element.validity.rangeOverflow) {
			element.setCustomValidity('Minimum değerden daha fazla')
		} else if (element.validity.stepMismatch) {
			element.setCustomValidity('Adımda bir sıkıntı var')
		} else if (element.validity.tooLong) {
			element.setCustomValidity('Çok uzun be gardaş')
		} else if (element.validity.tooShort) {
			element.setCustomValidity('Bu da çok kısa kaldı')
		} else if (element.validity.typeMismatch) {
			element.setCustomValidity('Tipsiz misin biraz?')
		} else if (element.validity.valueMissing) {
			element.setCustomValidity('Buralar hep dutluk!')
		} else {
			element.setCustomValidity('')
		}
		element.reportValidity()
  }

	document.forms.form1.addEventListener('submit', e => {
		e.preventDefault();
		[...e.target.elements].reverse().forEach(element => {
			checkValidity(element)
      // elemanın kontrolünü anlık olarak yapmaya devam et
      element.addEventListener('input', function(e) {
				checkValidity(e.target)
      })
		})
	})
</script>
```

### checkValidity()

Form öğesinin geçerli olup olmadığını döndürür.

```html
<form action="" id="form1" novalidate>
  <input type="text" name="username" required> <br>
  <button type="submit">Gonder</button>
</form>

<script>
	document.forms.form1.addEventListener('submit', e => {
		e.preventDefault();
		console.log(e.target.checkValidity())
	})
</script>
```

## Event() ve dispatchEvent()

Bir olayı simüle etmek için bu sınıfı kullanıyoruz. Örneğin bir button'a click olayı tanımlayalım ve bunu programlamatik olarak simüle edelim. Simüle edebilmek içinse `dispatchEvent()` metoduna parametre olarak `Event()` sınıfını geçiyoruz.

```html
<button id="btn">bana tıkla</button>
<script>
	const btn = document.getElementById('btn')
	btn.addEventListener('click', e => {
		console.log('butona tikladin')
	})

  btn.dispatchEvent(new Event('click')) // olayi gerceklestir
</script>
```

ayrıca bir olayın kullanıcı tarafından mı yoksa programlamatik olarak mı olduğunu tespit etmek için `e.isTrusted` özellliğine bakılabilir.

```html
<button id="btn">bana tıkla</button>
<script>
	const btn = document.getElementById('btn')
	btn.addEventListener('click', e => {
		if (e.isTrusted) {
			console.log('butona kullanici bizzat tikladi')
		} else {
			console.log('butona tiklama simulasyonu')
		}
	})
	btn.dispatchEvent(new Event('click')) // olayi gerceklestir
</script>
```

## customEvent()

Bazen önceden tanımlı olaylar yerine özel olayları tetiklemek isteyebiliriz. Örneğin bir tab uygulaması yapalım ve tab değiştiğinde bir özel olay fırlatıp bunu yakalayalım.

```html
<style>
  .active {
      background: yellow;
  }
</style>

<div id="tab">
  <nav>
    <button>tab 1</button>
    <button>tab 2</button>
  </nav>
  <div>
    <section>content 1</section>
    <section>content 2</section>
  </div>
</div>

<script>
  const tab = document.getElementById('tab')
  const items = tab.querySelectorAll('nav button')
  const contents = tab.querySelectorAll('section')

  // ilk elemana active classi ekleyelim
  items[0].classList.add('active');

  // ilk eleman haric digerlerini gizleyelim
  [...contents].filter((item, key) => key !== 0).forEach(content => content.style.display = 'none')

  // tab degistirme
  items.forEach((item, index) => item.addEventListener('click', e => {
		items.forEach((item, i) => {
			if (i === index) {
				item.classList.add('active')
      } else {
				item.classList.remove('active')
      }
    })
    contents.forEach(content => content.style.display = 'none')
    contents[index].style.display = 'block'

    // tabChanged adinda ozel bir olay tetikleyelim
    tab.dispatchEvent(
			new CustomEvent('tabChanged', {
				detail: {
					tab: index
				}
			})
    )
  }))

  // ozel olayi dinleyelim
  tab.addEventListener('tabChanged', e => {
		console.log('tab degisti', e.detail)
  })
</script>
```
