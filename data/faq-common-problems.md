# أسئلة وأمثلة شائعة في البرمجة

## FizzBuzz
السؤال الكلاسيكي: اطبع الأرقام من 1 لـ 100، بس لو الرقم قابل للقسمة على 3 اطبع "Fizz"، ولو على 5 اطبع "Buzz"، ولو الاتنين اطبع "FizzBuzz".
```python
for i in range(1, 101):
    if i % 15 == 0:
        print("FizzBuzz")
    elif i % 3 == 0:
        print("Fizz")
    elif i % 5 == 0:
        print("Buzz")
    else:
        print(i)
```

## عكس نص (Reverse String)
```python
def reverse_string(s):
    return s[::-1]
```
```javascript
function reverseString(s) {
  return s.split("").reverse().join("");
}
```

## التحقق من Palindrome
```python
def is_palindrome(s):
    s = s.lower().replace(" ", "")
    return s == s[::-1]
```

## إيجاد أكبر رقم في مصفوفة
```python
def find_max(arr):
    max_val = arr[0]
    for num in arr[1:]:
        if num > max_val:
            max_val = num
    return max_val
```

## عدّ تكرار العناصر
```python
def count_occurrences(arr):
    counts = {}
    for item in arr:
        counts[item] = counts.get(item, 0) + 1
    return counts
```

## إزالة التكرار من مصفوفة
```python
def remove_duplicates(arr):
    return list(set(arr))  # ملحوظة: بيفقد الترتيب الأصلي
```
```javascript
function removeDuplicates(arr) {
  return [...new Set(arr)];
}
```

## مشكلة شائعة: "kk Undefined is not a function"
غالباً السبب إنك بتنادي method مش موجودة، أو بتنادي على متغير لسه متعرّفش (null/undefined). الحل: اطبع (`console.log`) قيمة المتغير قبل ما تستخدمه، وتأكد إنه من النوع المتوقع.

## مشكلة شائعة: "IndexError: list index out of range" في Python
معناها إنك بتحاول توصل لعنصر مش موجود في القائمة (index أكبر من طول القائمة أو أصغر من الحد المسموح). الحل: اتأكد من طول القائمة قبل الوصول، أو استخدم `try/except`.

## مشكلة شائعة: تسريب ذاكرة في JavaScript (Memory Leak)
غالباً بيحصل من Event Listeners مش بتتشال، أو Closures بتحتفظ بمراجع لعناصر DOM اتشالت. الحل: استخدم `removeEventListener` لما العنصر يتشال، وراجع أي متغيرات عامة (global) بتتراكم من غير داعي.

## الفرق بين `==` و `===` في JavaScript
- `==` بيقارن القيمة بس، وبيحاول يحوّل الأنواع لبعض (Type Coercion) — ده بيسبب مفاجآت زي `"1" == 1` بترجع `true`.
- `===` بيقارن القيمة والنوع مع بعض — الأفضل والأكثر أماناً في أغلب الحالات.

## نصيحة عامة في تتبع الأخطاء (Debugging)
1. اقرأ رسالة الخطأ كاملة، خصوصاً رقم السطر.
2. اطبع (`print` أو `console.log`) قيم المتغيرات المهمة قبل السطر اللي بيفشل.
3. قسّم المشكلة لأجزاء أصغر واختبر كل جزء لوحده.
4. لو تعبت، سيب الكود شوية وارجعله بعقل صافي — غالباً هتلاقي الغلطة بسرعة.
