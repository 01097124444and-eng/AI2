# أساسيات Python

## المتغيرات وأنواع البيانات
```python
name = "محمد"          # str
age = 25                # int
price = 19.99           # float
is_active = True        # bool
items = [1, 2, 3]        # list
info = {"a": 1, "b": 2}  # dict
point = (10, 20)         # tuple
unique = {1, 2, 3}       # set
```

## الشروط
```python
if age >= 18:
    print("بالغ")
elif age >= 13:
    print("مراهق")
else:
    print("طفل")
```

## الحلقات
```python
for i in range(5):
    print(i)

for item in items:
    print(item)

i = 0
while i < 5:
    print(i)
    i += 1
```

## الدوال
```python
def greet(name, greeting="أهلاً"):
    return f"{greeting} يا {name}"

print(greet("سارة"))
print(greet("علي", "صباح الخير"))
```

## List Comprehension
```python
squares = [x**2 for x in range(10)]
evens = [x for x in range(20) if x % 2 == 0]
```

## التعامل مع الملفات
```python
with open("data.txt", "r", encoding="utf-8") as f:
    content = f.read()

with open("out.txt", "w", encoding="utf-8") as f:
    f.write("مرحباً")
```

## البرمجة كائنية التوجه (OOP)
```python
class Animal:
    def __init__(self, name, sound):
        self.name = name
        self.sound = sound

    def make_sound(self):
        return f"{self.name} بيقول {self.sound}"

class Dog(Animal):
    def __init__(self, name):
        super().__init__(name, "هاو هاو")

d = Dog("بوني")
print(d.make_sound())
```

## معالجة الأخطاء
```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("مينفعش تقسم على صفر")
except Exception as e:
    print(f"حصل خطأ: {e}")
finally:
    print("انتهى التنفيذ")
```

## مكتبات شائعة
- `requests` — للتعامل مع الإنترنت والـ APIs
- `pandas` — لتحليل البيانات
- `numpy` — للحسابات العددية
- `flask` / `django` — لعمل مواقع وسيرفرات
- `os`, `sys`, `json`, `datetime` — مكتبات أساسية مدمجة

## نصايح عملية
- استخدم أسماء متغيرات واضحة، مش `x1, x2, x3`.
- اكتب دوال صغيرة بتعمل حاجة واحدة بس.
- استخدم virtual environment (`venv`) لكل مشروع عشان متلخبطش المكتبات.
- اقرأ الـ Traceback بالكامل لما يظهر Error — الغلطة غالباً في آخر سطر بيشاور عليه.
