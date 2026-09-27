# خوارزميات وهياكل بيانات مهمة

## تعقيد الوقت (Big O) — نظرة سريعة
- `O(1)` — ثابت: الوصول لعنصر في مصفوفة بالـ index.
- `O(log n)` — لوغاريتمي: البحث الثنائي (Binary Search).
- `O(n)` — خطي: المرور على كل عناصر القائمة مرة واحدة.
- `O(n log n)` — خوارزميات الترتيب الكفؤة زي Merge Sort و Quick Sort.
- `O(n^2)` — تربيعي: خوارزميات الترتيب البسيطة زي Bubble Sort، أو حلقتين متداخلتين.

## البحث الثنائي (Binary Search)
يشتغل بس على قائمة مرتبة، وبيقسم المساحة نصين في كل خطوة.
```python
def binary_search(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1
```

## الترتيب بالفقاعات (Bubble Sort) — بسيط لكن بطيء
```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
    return arr
```

## الترتيب السريع (Quick Sort) — أكفأ للبيانات الكبيرة
```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quick_sort(left) + middle + quick_sort(right)
```

## الترتيب بالدمج (Merge Sort)
```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    result = []
    i = j = 0
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i]); i += 1
        else:
            result.append(right[j]); j += 1
    result.extend(left[i:])
    result.extend(right[j:])
    return result
```

## الاستدعاء الذاتي (Recursion) — مثال فيبوناتشي
```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

# نسخة أسرع باستخدام Memoization
def fib_memo(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 1:
        return n
    memo[n] = fib_memo(n - 1, memo) + fib_memo(n - 2, memo)
    return memo[n]
```

## هياكل البيانات الأساسية
- **Array / List**: تخزين متسلسل، وصول سريع بالـ index (`O(1)`)، إدراج/حذف في النص بطيء (`O(n)`).
- **Stack (مكدس)**: آخر داخل أول خارج (LIFO) — مفيد في تراجع العمليات (Undo) وتحليل الأقواس المتوازنة.
- **Queue (طابور)**: أول داخل أول خارج (FIFO) — مفيد في معالجة الطلبات بالترتيب.
- **Hash Map / Dictionary**: بحث وإدراج بمتوسط `O(1)` — أفضل هيكل لما تحتاج تربط مفتاح بقيمة بسرعة.
- **Linked List**: عناصر مربوطة ببعض بمؤشرات، إدراج/حذف سريع لكن وصول بطيء بالـ index.
- **Tree / Binary Search Tree**: تنظيم هرمي، بحث بمتوسط `O(log n)` لو الشجرة متوازنة.
- **Graph**: عُقد وحواف، بيتمثل بالـ DFS (بحث بالعمق) أو BFS (بحث بالعرض).

## نصايح عملية
- قبل ما تختار خوارزمية، اسأل نفسك: البيانات دي كبيرة قد إيه؟ وهل مرتبة بالفعل؟
- استخدم Hash Map لما تحتاج "تفتش بسرعة" — بيوفر وقت كتير.
- الـ Recursion حلو لكن احذر الـ Stack Overflow لو العمق كبير جداً من غير حالة توقف واضحة.
