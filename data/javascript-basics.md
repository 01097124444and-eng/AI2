# أساسيات JavaScript

## المتغيرات
```javascript
let age = 25;          // متغير ممكن يتغير
const name = "محمد";    // ثابت، مينفعش يتغير
var old = "قديم";       // نادراً ما بنستخدمه دلوقتي
```

## أنواع البيانات
```javascript
const str = "نص";
const num = 42;
const bool = true;
const arr = [1, 2, 3];
const obj = { key: "value" };
const nothing = null;
const notDefined = undefined;
```

## الشروط والحلقات
```javascript
if (age >= 18) {
  console.log("بالغ");
} else if (age >= 13) {
  console.log("مراهق");
} else {
  console.log("طفل");
}

for (let i = 0; i < 5; i++) {
  console.log(i);
}

arr.forEach(item => console.log(item));
```

## الدوال
```javascript
function greet(name, greeting = "أهلاً") {
  return `${greeting} يا ${name}`;
}

const greetArrow = (name) => `أهلاً يا ${name}`;
```

## Array Methods المهمة
```javascript
const numbers = [1, 2, 3, 4, 5];

const doubled = numbers.map(n => n * 2);
const evens = numbers.filter(n => n % 2 === 0);
const sum = numbers.reduce((acc, n) => acc + n, 0);
const found = numbers.find(n => n > 3);
const hasEven = numbers.some(n => n % 2 === 0);
const allPositive = numbers.every(n => n > 0);
```

## Promises و Async/Await
```javascript
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve("تم التحميل"), 1000);
  });
}

// باستخدام then
fetchData().then(result => console.log(result));

// باستخدام async/await (أوضح وأسهل)
async function loadData() {
  try {
    const result = await fetchData();
    console.log(result);
  } catch (err) {
    console.error("حصل خطأ:", err);
  }
}
```

## التعامل مع الـ DOM
```javascript
const el = document.getElementById("myId");
const els = document.querySelectorAll(".myClass");

el.textContent = "نص جديد";
el.addEventListener("click", () => {
  console.log("تم الضغط");
});

el.classList.add("active");
el.classList.remove("hidden");
```

## Destructuring و Spread
```javascript
const { a, b } = { a: 1, b: 2 };
const [first, second] = [10, 20];

const merged = { ...obj1, ...obj2 };
const combinedArr = [...arr1, ...arr2];
```

## نصايح عملية
- استخدم `const` دايماً إلا لو محتاج تغيّر القيمة، وساعتها استخدم `let`.
- استخدم `===` مش `==` عشان تتجنب مقارنات غير متوقعة.
- خلّي الدوال قصيرة ومركزة على حاجة واحدة (Single Responsibility).
- استخدم `console.log` بذكاء وقت الديباج، وامسحه قبل الرفع النهائي.
