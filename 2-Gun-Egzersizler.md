# 2. Gün Egzersizleri

## Egzersiz: Seviye 1

1. Bir değişken oluşturmak ve başlangıç değeri atamak:

```js
let challenge = '30 Days Of JavaScript';
```

2. Stringi tarayıcı konsolunda yazdırma:

```js
console.log(challenge);
```

3. Stringin uzunluğunu tarayıcı konsolunda yazdırma:

```js
console.log(challenge.length);
```

4. Stringdeki tüm karakterleri büyük harfe çevirme:

```js
console.log(challenge.toUpperCase());
```

5. Stringdeki tüm karakterleri küçük harfe çevirme:

```js
console.log(challenge.toLowerCase());
```

6. Stringin ilk kelimesini kesme:

```js
console.log(challenge.substr(0, challenge.indexOf(' ')));
```

7. '30 Days Of JavaScript' stringinden 'Days Of JavaScript' ifadesini kesme:

```js
console.log(challenge.substr(challenge.indexOf(' ') + 1));
```

8. Stringin 'Script' kelimesini içerip içermediğini kontrol etme:

```js
console.log(challenge.includes('Script'));
```

9. Stringi bir diziye dönüştürme:

```js
console.log(challenge.split());
```

10. '30 Days Of JavaScript' stringini boşluktan bölme:

```js
console.log(challenge.split(' '));
```

11. 'Facebook, Google, Microsoft, Apple, IBM, Oracle, Amazon' stringini virgülden bölüp diziye dönüştürme:

```js
let techCompanies = 'Facebook, Google, Microsoft, Apple, IBM, Oracle, Amazon';
console.log(techCompanies.split(', '));
```

12. '30 Days Of JavaScript' ifadesini '30 Days Of Python' ile değiştirme:

```js
console.log(challenge.replace('JavaScript', 'Python'));
```

13. '30 Days Of JavaScript' stringinde 15. indexdeki karakter:

```js
console.log(challenge.charAt(15));
```

14. '30 Days Of JavaScript' stringindeki 'J' karakterinin karakter kodu:

```js
console.log(challenge.charCodeAt(challenge.indexOf('J')));
```

15. '30 Days Of JavaScript' stringinde 'a' harfinin ilk geçtiği konum:

```js
console.log(challenge.indexOf('a'));
```

16. '30 Days Of JavaScript' stringinde 'a' harfinin son geçtiği konum:

```js
console.log(challenge.lastIndexOf('a'));
```

17. 'You cannot end a sentence with because because because is a conjunction' cümlesinde 'because' kelimesinin ilk geçtiği konum:

```js
let sentence = 'You cannot end a sentence with because because because is a conjunction';
console.log(sentence.indexOf('because'));
```

18. 'You cannot end a sentence with because because because is a conjunction' cümlesinde 'because' kelimesinin son geçtiği konum:

```js
console.log(sentence.lastIndexOf('because'));
```

19. 'You cannot end a sentence with because because because is a conjunction' cümlesinde 'because' kelimesinin ilk geçtiği konumu bulma:

```js
console.log(sentence.search('because'));
```

20. Bir stringin başındaki ve sonundaki boşlukları kaldırma:

```js
let challengeWithSpaces = ' 30 Days Of JavaScript ';
console.log(challengeWithSpaces.trim());
```

21. '30 Days Of JavaScript' stringinin belirli bir stringle başlayıp başlamadığını kontrol etme:

```js
console.log(challenge.startsWith('30'));
```

22. '30 Days Of JavaScript' stringinin belirli bir stringle bitip bitmediğini kontrol etme:

```js
console.log(challenge.endsWith('JavaScript'));
```

23. '30 Days Of JavaScript' stringindeki tüm 'a' harflerini bulma:

```js
console.log(challenge.match(/a/g));
```

24. '30 Days of' ve 'JavaScript' stringlerini birleştirme:

```js
let part1 = '30 Days of';
let part2 = 'JavaScript';
console.log(part1.concat(' ', part2));
```

25. '30 Days Of JavaScript' stringini 2 kere yazdırma:

```js
console.log(challenge.repeat(2));
```

## Egzersiz: Seviye 2

1. Aşağıdaki ifadeyi konsola yazdırın:

```
The quote 'There is no exercise better for the heart than reaching down and lifting people up.' by John Holmes teaches us to help one another.
```

```js
console.log("The quote 'There is no exercise better for the heart than reaching down and lifting people up.' by John Holmes teaches us to help one another.");
```

2. Aşağıdaki `Mother Teresa` alıntısını konsola yazdırın:

```
"Love is not patronizing and charity isn't about pity, it is about love. Charity and love are the same -- with charity you give love, so don't just give money but reach out your hand instead."
```

```js
console.log("\"Love is not patronizing and charity isn't about pity, it is about love. Charity and love are the same -- with charity you give love, so don't just give money but reach out your hand instead.\"");
```

3. `'10'` tipinin tam olarak `10`'a eşit olup olmadığını kontrol edin. Eşit değilse, tam olarak eşitleyin:

```js
let num = '10';
if (typeof num !== typeof 10) {
    num = Number(num);
}
console.log(num, typeof num);
```

4. `parseFloat('9.8')`'in `10`'a eşit olup olmadığını kontrol edin, eşit değilse 10'a eşitleyin:

```js
let floatNum = parseFloat('9.8');
if (floatNum !== 10) {
    floatNum = Math.ceil(floatNum);
}
console.log(floatNum);
```

5. `'on'` kelimesinin hem python hem de jargon kelimesinde geçip geçmediğini kontrol edin:

```js
console.log('python'.includes('on') && 'jargon'.includes('on'));
```

6. "I hope this course is not full of jargon." cümlesinde 'jargon' kelimesinin geçip geçmediğini kontrol edin:

```js
let sentence = "I hope this course is not full of jargon.";
console.log(sentence.includes('jargon'));
```

7. 0 ile 100 arasında rastgele bir sayı oluşturun:

```js
console.log(Math.floor(Math.random() * 101));
```

8. 50 ile 100 arasında rastgele bir sayı oluşturun:

```js
console.log(Math.floor(Math.random() * 51) + 50);
```

9. 0 ile 255 arasında rastgele bir sayı oluşturun:

```js
console.log(Math.floor(Math.random() * 256));
```

10. 'JavaScript' stringindeki karakterlere rastgele bir sayı kullanarak erişin:

```js
let js = "JavaScript";
let randIndex = Math.floor(Math.random() * js.length);
console.log(js[randIndex]);
```

11. Aşağıdaki deseni yazdırmak için console.log() ve kaçış karakterlerini kullanın:

```
1 1 1 1 1
2 1 2 4 8
3 1 3 9 27
4 1 4 16 64
5 1 5 25 125
```

```js
console.log("1 1 1 1 1\n2 1 2 4 8\n3 1 3 9 27\n4 1 4 16 64\n5 1 5 25 125");
```

12. Aşağıdaki cümleden "because because because" ifadesini çıkarmak için substr kullanın: 
"You cannot end a sentence with because because because is a conjunction"

```js
let fullSentence = 'You cannot end a sentence with because because because is a conjunction';
let start = fullSentence.indexOf('because');
let end = fullSentence.lastIndexOf('because') + 'because'.length;
let becausePhrase = fullSentence.substr(start, end-start);
console.log(becausePhrase);
```

## Egzersiz: Seviye 3

1. `Love is the best thing in this world. Some found their love and some are still looking for their love` cümlesinde `love` kelimesinin kaç kere geçtiğini bulun:

```js
let sentence = 'Love is the best thing in this world. Some found their love and some are still looking for their love.';
let count = (sentence.match(/love/gi) || []).length;
console.log(count);
```

2. Aşağıdaki cümlede `'because'` kelimesinin kaç kez geçtiğini sayın:

```
You cannot end a sentence with because because because is a conjunction
```

```js
let sentenceBecause = 'You cannot end a sentence with because because because is a conjunction';
let countBecause = (sentenceBecause.match(/because/g) || []).length;
console.log(countBecause);
```

3. Aşağıdaki metni temizleyin ve en sık kullanılan kelimeyi bulun:

```
%I $am@% a %tea@cher%, &and& I lo%#ve %te@a@ching%;. The@re $is no@th@ing; &as& mo@re rewarding as educa@ting &and& @emp%o@weri@ng peo@ple. ;I found tea@ching m%o@re interesting tha@n any ot#her %jo@bs. %Do@es thi%s mo@tiv#ate yo@u to be a tea@cher!? %Th#is 30#Days&OfJavaScript &is al@so $the $resu@lt of &love& of tea&ching
```

```js
let messySentence = '%I $am@% a %tea@cher%, &and& I lo%#ve %te@a@ching%;. The@re $is no@th@ing; &as& mo@re rewarding as educa@ting &and& @emp%o@weri@ng peo@ple. ;I found tea@ching m%o@re interesting tha@n any ot#her %jo@bs. %Do@es thi%s mo@tiv#ate yo@u to be a tea@cher!? %Th#is 30#Days&OfJavaScript &is al@so $the $resu@lt of &love& of tea&ching';
let cleanSentence = messySentence.replace(/[^a-zA-Z ]/g, " ");

let words = cleanSentence.split(' ');
let wordCounts = {};
for(let i = 0; i < words.length; i++) {
    if(words[i] !== '') {
        wordCounts[words[i]] = (wordCounts[words[i]] || 0) + 1;
    }
}

let maxWord = '';
let maxCount = 0;
for(let word in wordCounts) {
    if(wordCounts[word] > maxCount) {
        maxCount = wordCounts[word];
        maxWord = word;
    }
}

console.log(`Most frequent word is '${maxWord}' with count ${maxCount}`);
```

🎉 Tebrikler :) 3. günün egzersizlerine geçebilirsiniz. 🎉
