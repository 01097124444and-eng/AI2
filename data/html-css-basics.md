# أساسيات HTML و CSS

## هيكل صفحة HTML أساسية
```html
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>عنوان الصفحة</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>هيدر الصفحة</header>
  <main>المحتوى الرئيسي</main>
  <footer>فوتر الصفحة</footer>
  <script src="script.js"></script>
</body>
</html>
```

## أهم العناصر
```html
<h1>عنوان رئيسي</h1>
<p>فقرة نصية</p>
<a href="https://example.com">رابط</a>
<img src="pic.jpg" alt="وصف الصورة">
<button>زرار</button>
<input type="text" placeholder="اكتب هنا">
<ul>
  <li>عنصر أول</li>
  <li>عنصر تاني</li>
</ul>
<div class="box">صندوق</div>
```

## نماذج (Forms)
```html
<form>
  <label for="email">البريد الإلكتروني</label>
  <input type="email" id="email" name="email" required>
  <button type="submit">إرسال</button>
</form>
```

## CSS أساسي
```css
body {
  font-family: sans-serif;
  margin: 0;
  padding: 0;
  background: #f4f5f7;
  color: #1c1e21;
}

.box {
  padding: 16px;
  border-radius: 10px;
  background: white;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}
```

## Flexbox (الأكثر استخداماً للتنسيق)
```css
.container {
  display: flex;
  justify-content: space-between; /* توزيع أفقي */
  align-items: center;             /* محاذاة رأسية */
  gap: 12px;
}
```

## Grid (لتقسيمات أكثر تعقيداً)
```css
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}
```

## التصميم المتجاوب (Responsive)
```css
@media (max-width: 600px) {
  .container {
    flex-direction: column;
  }
}
```

## متغيرات CSS
```css
:root {
  --primary-color: #7c5cff;
  --spacing: 16px;
}

.button {
  background: var(--primary-color);
  padding: var(--spacing);
}
```

## نصايح عملية
- استخدم Flexbox للتنسيقات البسيطة، وGrid للتقسيمات المعقدة (صفوف وأعمدة).
- خلّي أسماء الـ classes وصفية زي `.card-title` مش `.ct1`.
- استخدم `rem` أو `%` بدل `px` الثابت عشان تصميم متجاوب أحسن.
- اختبر التصميم على شاشات موبايل صغيرة قبل ما تعتبره خلص.
