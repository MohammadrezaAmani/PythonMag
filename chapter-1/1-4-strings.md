### فصل ۱ آموزک ۴: رشته‌ها :memo:

در دنیای برنامه‌نویسی ‍`رشته` یا `string` به دنباله‌ای از کاراکترها گفته میشه که تو اصطلاح عامیانه ما بهش میگیم متن یا تکست. 

برای تعریف متغییر از جنس `string` تنها کافی هست بعد از نوشتن نام متغییر و علامت مساوی `=` رشته مورد نظرتون رو میان دو کوتیشن ‍`'` و یا دابل کوتیشن `"` و
یا `'''` یا `"""` بذارید. 

فرق میون این‌ها رو می‌تونید رو [آموزک تعریف متغییر](./1-2-variables.md) ببینید. 

مثلا: 

``` python
string1 = 'ba deghat bekhonin darsatono!'
string2 = "نمی‌دونم چی باید بنویسم."
string3 = '''
salam khobi?
'''
string4 = """
e alie! aliiii! 
"""
```

### عملیات‌ها بین رشته‌ها

برای ساخت رشته‌ها روش‌های دیگه‌ای هم وجود داره که به شرح زیرن:

#### استفاده از عملات جمع `+`
``` python
text1 = 'salam man '
text2 = text1 + 'Mohammadreza Amani hastam.'
print(text2)
```
``` python
>>> salam man Mohammadreza Amani hastam.
```
#### استفاده از علامت ضرب `*`

``` python
text = 'hi ' * 5
print(text)
```
```
>>> hi hi hi hi hi 
```

#### استفاده از تابع درونی `str()`

تابع `str()` یکی از توابع درونی پایتون برای تبدیل هر شی به رشته هست.

برای کار با اون تنها کافی هست تا متغییرتون رو به عنوان ورودی به تابع بدید و اون مقدار رشته شده‌ی اون رو بر میگردونه. مثلا:

``` python
myAge = 22
text = 'I have ' + str(myAge) + ' years old.'
print(text)
```
``` python
>>> I have 22 years old.
```
#### استفاده از `f string` 

این یکی شاید خیلی ملموس نباشه ولی خب وقتی میخواییم از یک متغییر در دل یک رشته استفاده کنیم می‌تونیم از متدی استفاده کنیم به اسم `f'string'` اول یه نگاهی به 
کد زیر بندازید: 
``` python 
name = 'Mohammadreza Amani`
age = 22
info = f'Mr.{name} has {age} years old.'
print(info)
```
``` python
>>> Mr. Mohammadreza Amani has 22 years old.
```

در واقع در روش بالا اومدیم قبل از کوتیشن اول یک ‍`f` که مخفف `format` هست رو قرار دادیم و بعد متغییرهای خودمون و یا هر کد پایتونی که نیاز داریم رو در بین دو
کروشه می‌نویسیم و بعد ادامه متنمون. از این روش میشه برای تبدیل دیتا تایپ های دیگه به استرینگ هم استفاده کرد.

کد بالا معادل کد زیر هست:

``` python
name = 'Mohammadreza Amani'
age = 22
info = 'Mr. ' + name + ' has ' + str(age) + ' years old.'
print(info)
```
``` python
>>> Mr. Mohammadreza Amani has 22 years old.
```
#### استفاده از format

روش دیگه ای که شبیه به روش `f'string'` هست اما کمی قدیمی تر روش `format` هست. در این روش به شکل زیر عمل میکنیم.

``` python
name = 'Mohammadreza Amani'
age = 22
info = 'Mr. {} has {} years old.'.format(name, age)
print(info)
```
``` python
>>> Mr. Mohammadreza Amani has 22 years old.
```

در این روش بعد از استرینگ یا حتی متغییری با جنس استرینگ علامت `.foramt` رو قرار داده و بعد به عنوان ورودی به ترتیب متغییرهایی که نیاز داریم رو وارد کنیم.
البته این رو هم بگم که میشه ترتیب رو تغییر داد یعنی با قرار دادن اعدادی که از 0 شروع میشن تا تعداد ورودی‌ها منهای یک به ترتیب مکان اون‌ها رو مشخص کرد.

البته حس می‌کنم یه مقداری بد گفتم، به مثال زیر توجه کنید:

``` python
name = 'Mohammadreza Amani'
age = 22
info = 'Mr. {1} has {0} years old.'.format(name, age)
print(info)
```
``` python
>>> Mr. 22 has Mohammadreza Amani years old.
```

در واقع با دادن عدد یک به درون پرانتز اول گفتیم می‌خواییم دومین آرگومان ورودی تابع `format` برای تو باشه و با دادن عدد 0 به پرانتز دوم گفتیم میخواییم 
اولین ورودی تابع برای تو باشه. (این رو به خاطر داشته باشید که در پایتون اعداد از 0 شروع می‌شن.)

#### استفاده از علامت `%`

این روش که نسبت به روش‌های قبلی کم‌تر دیده شده ولی قدیمی‌تر و راحت‌تر هست به این صورته که بجای پرانتز و استفاده از تابع فرمت از % و نوع ورودی استفاده می‌کنیم.
به مثال زیر دقت کنید.
``` python
name = 'Mohammadreza Amani'
age = 22
info = 'Mr. %s has %d years old.'%(name, age)
print(info)
```
``` python
Mr. Mohammadreza Amani has 22 years old.
```

برای استفاده از % باید بعد از اون کارکاتر `s` و یا  `d` و یا `f‍‍` رو قرار داد. که ‍`%s` برای متن، `%d` برای اعداد صحیح و `%f` برای اعداد اعشاری هست.

نکته دیگه‌ای که وجود داره برای نشان دادن تعداد مشخصی از اعداد بعد از ممیز در اعداد اعشاری به شکل زیر عمل می‌کنیم:
``` python
pi = 3.141592653589793
info = "pi is %.2f" % pi
print(info)
```
``` python
>>> pi is 3.14
```

### متودهای رشته‌ها | string methods

در پایتون برای رشته‌ها متود‌هایی وجود داره که به شرح زیر هستند:

! باید ادیت بشه!

دقت داشته باشید که در مثال‌ها:
| نام | مقدار |
|----|-----|
| text1 | 'hi im moh\tammdreza' |
| text2 | 'mohammadreza' |
| text3 | 'MohaMMadreza |
| text4 | 'Moh{}ammadreza' |

| متود | توضیحات | مثال | خروجی | 
|-----|-----|-----|-----|
| capitalize() |	تبدیل کردن نخستین کاراکتر رشته به حرف بزرگ | text2.capitalize() | Mohammadreza |
| casefold() | تبدیل کردن کل کاراکترهای رشته به حروف کوچک | text3.casefold() | mohammadreza | 
| center(width, char) | قرار دادن متن میان `width` تعداد از کاراکتر `char` | text2.center(50, '&') |  &&&&&&&&&&&&&&&&&&&mohammadreza&&&&&&&&&&&&&&&&&&& |
| count(word) | شمارش تعداد بارهای تکرار کلمه ‍`word` در متن و برگرداندن آن | text2.count('m') | 3|
| encode()|  انکورد کردن متن | text2.encode('utf-8') | b'mohammadreza' |
| endswith(word) | اگر رشته با عبارت `word` تمام شده باشد مقدار `True` را بر می‌گرداند در غیر این صورت `False` | text2.endwith('reza') | True |
| expandtabs(int)	| تعیین مقدار `tab` در استرینگ | text1.expandtabs(10) | hi im moh          ammadreza |
| find(word) | جست و جو برای یک مقدار مشخص و برگرداندن ایندکس  آن | text2.find('ad') | 6 |
| format() | فورمت کردن متن | text4.format('hi') | Mohhiammadreza
| format_map()	Formats specified values in a string
| index()	Searches the string for a specified value and returns the position of where it was found
| isalnum()	Returns True if all characters in the string are alphanumeric
| isalpha()	Returns True if all characters in the string are in the alphabet
| isascii()	Returns True if all characters in the string are ascii characters
| isdecimal()	Returns True if all characters in the string are decimals
| isdigit()	Returns True if all characters in the string are digits
| isidentifier()	Returns True if the string is an identifier
| islower()	Returns True if all characters in the string are lower case
| isnumeric()	Returns True if all characters in the string are numeric
| isprintable()	Returns True if all characters in the string are printable
| isspace()	Returns True if all characters in the string are whitespaces
| istitle()	Returns True if the string follows the rules of a title
| isupper()	Returns True if all characters in the string are upper case
| join()	Converts the elements of an iterable into a string
| ljust()	Returns a left justified version of the string
| lower()	Converts a string into lower case
| lstrip()	Returns a left trim version of the string
| maketrans()	Returns a translation table to be used in translations
| partition()	Returns a tuple where the string is parted into three parts
| replace()	Returns a string where a specified value is replaced with a specified value
| rfind()	Searches the string for a specified value and returns the last position of where it was found
| rindex()	Searches the string for a specified value and returns the last position of where it was found
| rjust()	Returns a right justified version of the string
| rpartition()	Returns a tuple where the string is parted into three parts
| rsplit()	Splits the string at the specified separator, and returns a list
| rstrip()	Returns a right trim version of the string
| split()	Splits the string at the specified separator, and returns a list
| splitlines()	Splits the string at line breaks and returns a list
| startswith()	Returns true if the string starts with the specified value
| strip()	Returns a trimmed version of the string
| swapcase()	Swaps cases, lower case becomes upper case and vice versa
| title()	Converts the first character of each word to upper case
| translate()	Returns a translated string
| upper()	Converts a string into upper case
| zfill()	Fills the string with a specified number of 0 values at the beginning
