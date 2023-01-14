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


........ DEVAM EDECEK .......
