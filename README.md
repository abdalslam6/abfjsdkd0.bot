# Devil Bot - Telegram Remote Control Bot

تطبيق Node.js يوفر واجهة تحكم عن بعد عبر بوت Telegram.

## المتطلبات

- **Node.js** الإصدار 16.13.2 أو أحدث
- **npm** (مدير الحزم)
- **حساب Telegram** مع بوت Telegram مُعد

## الإعداد المحلي

### 1. استنساخ المستودع أو تحميل الملفات

```bash
cd server
```

### 2. تثبيت التبعيات

```bash
npm install
```

### 3. إعداد متغيرات البيئة

قم بنسخ ملف `.env.example` إلى `.env` وأضف قيمك الخاصة:

```bash
cp .env.example .env
```

ثم عدّل ملف `.env` وأضف:

```
TELEGRAM_TOKEN=your_actual_telegram_bot_token
TELEGRAM_CHAT_ID=your_actual_chat_id
PORT=8999
```

### 4. تشغيل التطبيق محليًا

```bash
npm start
```

سيبدأ الخادم على المنفذ المحدد (افتراضيًا 8999).

## النشر على Render

### الخطوة 1: إنشاء حساب على Render

1. اذهب إلى [https://render.com](https://render.com)
2. قم بإنشاء حساب جديد أو تسجيل الدخول

### الخطوة 2: إعداد مستودع GitHub

1. اذهب إلى [https://github.com](https://github.com)
2. قم بإنشاء حساب جديد إذا لم يكن لديك واحد
3. قم بإنشاء مستودع جديد باسم `devil-bot` (أو أي اسم تفضله)
4. قم برفع ملفات المشروع إلى هذا المستودع:
   - انسخ جميع ملفات المشروع (بما فيها `package.json`, `server.js`, `Procfile`, `.env.example`, إلخ)
   - استخدم Git لرفع الملفات:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/your-username/devil-bot.git
   git push -u origin main
   ```

### الخطوة 3: ربط المستودع بـ Render

1. في لوحة تحكم Render، انقر على **"New +"** ثم اختر **"Web Service"**
2. اختر **"Connect a repository"** وابحث عن مستودعك `devil-bot`
3. اختر الفرع `main`
4. ملء التفاصيل:
   - **Name:** `devil-bot` (أو أي اسم تفضله)
   - **Environment:** `Node`
   - **Build Command:** `npm install`
   - **Start Command:** `npm start`
   - **Plan:** اختر **Free** (مجاني) أو **Paid** حسب احتياجاتك

### الخطوة 4: إضافة متغيرات البيئة

1. في صفحة إعدادات الخدمة على Render، انتقل إلى **"Environment"**
2. أضف المتغيرات التالية:
   ```
   TELEGRAM_TOKEN = your_actual_telegram_bot_token
   TELEGRAM_CHAT_ID = your_actual_chat_id
   PORT = 8999
   ```

### الخطوة 5: نشر التطبيق

1. انقر على **"Create Web Service"**
2. سيبدأ Render في بناء ونشر التطبيق تلقائيًا
3. بعد انتهاء النشر، ستحصل على رابط URL دائم لتطبيقك

## الملفات الهامة

| الملف | الوصف |
|------|-------|
| `server.js` | ملف الخادم الرئيسي |
| `package.json` | ملف التبعيات والإعدادات |
| `.env` | متغيرات البيئة (لا تشاركه علنًا) |
| `.env.example` | مثال على متغيرات البيئة |
| `Procfile` | ملف إعدادات النشر على Render |
| `README.md` | هذا الملف |

## الأمان

⚠️ **تحذير أمني مهم:**
- **لا تشارك ملف `.env` أو قيم `TELEGRAM_TOKEN` و `TELEGRAM_CHAT_ID` علنًا**
- تأكد من أن ملف `.env` مضاف إلى `.gitignore` لمنع رفعه إلى المستودع
- استخدم متغيرات البيئة على منصة Render بدلاً من وضع القيم مباشرة في الكود

## الدعم والمساعدة

إذا واجهت مشاكل:
1. تحقق من سجلات الأخطاء على Render (في لوحة التحكم)
2. تأكد من أن جميع متغيرات البيئة مضافة بشكل صحيح
3. تأكد من أن توكن Telegram صحيح ومعرف الدردشة صحيح

---

**تم إعداد هذا المشروع للنشر الدائم على Render.**
