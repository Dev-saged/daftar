<div align="center">

# 🏪 محلات العبادلة التجارية
### نظام إدارة الديون الذكي
**Al-Abadlah Trading Stores — Smart Debt Management System**

---

![Version](https://img.shields.io/badge/الإصدار-v1.0.0-e8840e?style=for-the-badge)
![Platform](https://img.shields.io/badge/المنصة-Android%20%7C%20Web-0f0f0f?style=for-the-badge)
![Offline](https://img.shields.io/badge/يعمل_بدون_إنترنت-✓-27ae60?style=for-the-badge)
![Firebase](https://img.shields.io/badge/Firebase-Firestore-FFCA28?style=for-the-badge&logo=firebase)

</div>

---

## 🌟 نظرة عامة | Overview

> نظام متكامل لإدارة ديون العملاء عبر ثلاثة فروع تجارية، يعمل بلا اتصال بالإنترنت ويتزامن فورياً بمجرد الاتصال.

> A complete customer debt management system across three commercial branches — works fully offline and syncs instantly upon connection.

---

## ✨ المميزات الرئيسية | Key Features

<div align="center">

| الميزة | Feature | التفاصيل |
|--------|---------|----------|
| 📴 **بدون إنترنت** | Offline First | يحفظ كل البيانات محلياً فوراً |
| 🔄 **مزامنة ذكية** | Smart Sync | تزامن تلقائي عند كل اتصال |
| ⚡ **سريع جداً** | Blazing Fast | لا توجد مكتبات خارجية |
| 🖨️ **طباعة حرارية** | Thermal Print | فواتير 80mm جاهزة للطباعة |
| 🌙 **Dark Mode** | Dark Theme | واجهة مريحة للعيون |
| 🔁 **تحديث تلقائي** | Auto Update | إشعار فوري بأي إصدار جديد |
| 📱 **موبايل فيرست** | Mobile First | مُحسَّن للهواتف الذكية |
| 🔀 **تعارض ذكي** | Conflict Resolution | الجهاز الأحدث يفوز دائماً |

</div>

---

## 🏗️ التقنيات المستخدمة | Tech Stack

```
🌐  HTML5 + CSS3 + Vanilla JavaScript   →  واجهة المستخدم
💾  IndexedDB (Web API)                 →  قاعدة بيانات محلية
☁️  Firebase Firestore                  →  مزامنة سحابية
📲  WebToApp (Android)                  →  تحويل لتطبيق Android
```

> ⚠️ **صفر اعتماديات خارجية** — يعمل من أي متصفح بدون تثبيت أي شيء
> Zero external dependencies — runs in any browser with no installation

---

## 📸 شاشات التطبيق | App Screens

```
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│   🏪 الرئيسية   │  │  👤 ملف العميل  │  │  💳 تسجيل دفعة  │
│                 │  │                 │  │                 │
│ إجمالي: 1,250  │  │  محمد علي       │  │  المبلغ: ____  │
│ عملاء: 12      │  │  المتبقي: 450   │  │  ملاحظات: ____ │
│                 │  │  [دين][دفعة]   │  │  [تسجيل وطباعة]│
│  [+ إضافة]     │  │  --- سجل ---   │  │                 │
└─────────────────┘  └─────────────────┘  └─────────────────┘
```

---

## 🔄 آلية المزامنة | Sync Architecture

```
📱 الجهاز A          ☁️ Firebase           📱 الجهاز B
فرع الفلافل    ←→   Firestore DB   ←→   فرع المشاوي
                          ↕
                    📱 الجهاز C
                    فرع المندي
```

### 🧠 حل التعارضات | Conflict Resolution
```
إذا دخل شخصان في نفس الوقت ← If two devices edit simultaneously:

  1️⃣  أحدث تعديل يفوز         (updatedAt)
  2️⃣  تساوي؟ → رقم الجهاز الأعلى يفوز  (deviceId tie-breaker)
  ✅  نفس النتيجة على كل الأجهزة — دائماً
```

---

## ⏰ جدول المزامنة التلقائية | Auto-Sync Schedule

```
🌙  00:00  ←  منتصف الليل
☀️  12:00  ←  الظهيرة
🌆  18:00  ←  المساء
📶  فوراً  ←  عند استعادة الاتصال بالإنترنت
```

---

## 🚀 البدء السريع | Quick Start

### الخطوة 1 — Firebase Setup
```
1. اذهب إلى console.firebase.google.com
2. أنشئ مشروع جديد
3. فعّل Firestore Database
4. احصل على: apiKey / authDomain / projectId
```

### الخطوة 2 — تهيئة التطبيق
```
1. افتح التطبيق في المتصفح
2. الإعدادات ← Firebase
3. الصق بيانات الاتصال الثلاثة
4. احفظ ← تم ✓
```

### الخطوة 3 — التوزيع على الفروع
```
📱 ارسل الرابط لكل فرع
🔗 كلهم يتصلون بنفس Firebase
✅ المزامنة تشتغل تلقائياً
```

---

## 📋 هيكل قاعدة البيانات | Data Structure

```
Firestore
├── customers/
│   └── {id}
│       ├── name         (اسم العميل)
│       ├── phone        (رقم الجوال)
│       ├── balance      (الرصيد المتبقي)
│       ├── deviceId     (معرّف الجهاز)
│       └── updatedAt    (وقت آخر تعديل)
│
└── transactions/
    └── {id}
        ├── type         (debt | payment)
        ├── amount       (المبلغ)
        ├── customerId   (رابط العميل)
        ├── shopName     (اسم الفرع)
        ├── employeeName (اسم الموظف)
        └── timestamp    (التاريخ والوقت)
```

---

## 🖨️ الفاتورة الحرارية | Thermal Invoice

```
================================
   محلات العبادلة التجارية
    إدارة أبو يامن العبادلة
         فرع الفلافل
--------------------------------
العميل:     محمد علي
الجوال:     07XXXXXXXX
--------------------------------
المدفوع:    500 ر.ي
المتبقي:    250 ر.ي
--------------------------------
التاريخ:    01/07/2026 14:30
الموظف:     خالد
--------------------------------
       شكراً لتعاملكم معنا
================================
```

---

## 🔒 الأمان | Security

| المستوى | الحماية |
|---------|---------|
| 🟡 **تجربة** | Firebase Rules مفتوحة (للاختبار فقط) |
| 🟢 **إنتاج** | Firebase Rules مقيدة + App Check |

> 💡 **قبل الإطلاق الرسمي:** قيّد Firebase Rules لمنع الوصول غير المصرح به

---

## 📱 متطلبات النظام | System Requirements

```
المتصفح:   Chrome / Safari / Firefox (أحدث إصدار)
Android:   API 28+ (Android 9+)
التخزين:   5 MB تقريباً
الإنترنت:  مطلوب للمزامنة فقط (اختياري)
```

---

## 🔔 نظام التحديث التلقائي | Auto-Update System

```
كل تشغيل للتطبيق يفحص version.json على GitHub
↓
إذا وجد إصدار أحدث → بنر RTL غير معيق
↓
المستخدم يضغط "تحديث الآن" → صفحة الإصدارات
```

---

## 🗺️ خارطة الطريق | Roadmap

- [x] إدارة العملاء والديون
- [x] تسجيل الدفعات
- [x] طباعة الفواتير الحرارية
- [x] مزامنة Firebase
- [x] conflict resolution ذكي
- [x] تحديث تلقائي
- [ ] تقارير شهرية
- [ ] إشعارات واتساب للعملاء
- [ ] نسخ احتياطي يدوي PDF
- [ ] إحصائيات متقدمة

---

## 🤝 المساهمة | Contributing

```
🐛 وجدت خطأ؟      → افتح Issue
💡 عندك تحسين؟    → أرسل Pull Request
❓ عندك سؤال؟     → افتح Discussion
```

---

<div align="center">

## 💛 صُنع بـ | Built with

**Vanilla JS · Firebase · IndexedDB · Love**

---

![Made in Yemen](https://img.shields.io/badge/Made_in-Yemen_🇾🇪-c0392b?style=for-the-badge)
![Open Source](https://img.shields.io/badge/Open-Source_❤️-e8840e?style=for-the-badge)

**الإصدار v1.0.0 — 2026**

</div>
