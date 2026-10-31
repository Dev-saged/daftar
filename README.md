# دفتري — تطبيق تتبع الديون الشخصية

<div align="center">

![Version](https://img.shields.io/badge/الإصدار-v2.0.0_قيد_البناء-e8840e?style=for-the-badge)
![Platform](https://img.shields.io/badge/المنصة-Android-0f0f0f?style=for-the-badge)
![Stack](https://img.shields.io/badge/Stack-React_Native_Expo-61DAFB?style=for-the-badge&logo=react)
![Offline](https://img.shields.io/badge/يعمل_بدون_إنترنت-✓-27ae60?style=for-the-badge)

</div>

---

## نظرة عامة

تطبيق Android لتتبع الديون الشخصية — تسجّل من يدين لك ومن أنت مدين له، مع تتبع الدفعات والإشعار عند التأخر.

---

## الحالة الحالية

| النسخة | الوصف | الملف |
|--------|-------|-------|
| v1.0.0 (Legacy) | HTML واحد + LocalStorage | `legacy/daftari-personal-v1.0.0.html` |
| v1.2.1 APK | WebToApp → Android | GitHub Releases |
| **v2.0.0** | **React Native — قيد البناء** | — |

---

## الميزات المخطط لها في v2.0.0

- 📇 إدارة جهات الاتصال (المدينين / الدائنين)
- 💰 تسجيل الديون (دين لي / دين علي)
- 💳 تسجيل الدفعات مع تتبع المتبقي
- 📊 تقارير وإحصائيات
- 🔔 تنبيهات الاستحقاق
- 🔐 حماية بـ PIN / Biometric
- 💱 دعم عملات متعددة
- 📤 تصدير البيانات
- 🔄 تحديث تلقائي

---

## Stack

```
React Native + Expo     →  التطبيق
SQLite / AsyncStorage   →  قاعدة البيانات المحلية
Expo Router             →  التنقل
```

---

## المستودع

```
daftar/
├── legacy/              ← النسخ القديمة (مرجعية)
├── docs/                ← التوثيق والهيكلية
├── app/                 ← كود React Native (قريباً)
└── version.json         ← نظام التحديث التلقائي
```

---

## المطور

**ساجد العبادلة** — [@Dev-saged](https://github.com/Dev-saged)

---

*v2.0.0 — بناء من جديد | 2026*
