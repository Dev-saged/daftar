# دفتري — وثيقة المفهوم والهيكلية

> حالة: قيد التخطيط | النقلة النوعية v2.0.0

---

## الفكرة الأساسية

تطبيق Android أصيل لتتبع الديون الشخصية — بين الأفراد.

**نوعان من الديون:**
- **دين لي** → شخص يدين لك
- **دين علي** → أنت مدين لشخص

---

## النسخة الحالية (Legacy Web v1.0.0)

- ملف HTML واحد + LocalStorage
- بدون إنترنت — offline أولاً
- يعمل عبر WebToApp (Android APK)
- مميزات: جهات اتصال، ديون، دفعات، تقارير، PIN، عملات متعددة

**الملفات المرجعية:**
- `legacy/daftari-personal-v1.0.0.html` — الكود كاملاً
- APK v1.2.1 — في GitHub Releases

---

## النقلة النوعية v2.0.0

**الهدف:** إعادة بناء كاملة كتطبيق Android أصيل

**اللغة المقررة:** React Native (Expo) ← أفضل خيار
- ✅ نفس مفاهيم JS التي يعرفها المطور
- ✅ cross-platform جاهز
- ✅ Expo يلغي تعقيد Android Studio
- ✅ الكود القديم (JS logic) قابل للاستخدام

**التصميم:** تصميم جديد كلياً — يُحدد لاحقاً

---

## البيانات المحفوظة من النسخة الحالية

### هيكل البيانات (LocalStorage → JSON)
```js
{
  contacts: [{ id, name, phone, note, color, created_at, archived }],
  debts: [{
    id, contact_id, type, amount, currency, title, due_date, note,
    created_at, archived,
    payments: [{ id, amount, note, paid_at }]
  }],
  settings: {
    owner_name, default_currency, pin_enabled, pin_hash
  }
}
```

### العملات المدعومة (الافتراضية)
USD, ILS, JOD, EUR + قائمة كاملة قابلة للبحث

### الحسابات الأساسية
- `paid(debt)` = مجموع الدفعات
- `remaining(debt)` = المبلغ - المدفوع
- `status(debt)` = مكتمل | متأخر | جزئي | نشط
- `net(contact)` = مديونيتي له - مديونيته لي

---

## خطة التنفيذ (تُحدد مع المطور)

- [ ] اختيار Stack النهائي (React Native + Expo)
- [ ] تصميم شاشات جديدة
- [ ] هيكل المشروع
- [ ] بناء الشاشة الرئيسية
- [ ] قاعدة البيانات (SQLite / AsyncStorage / Realm)
- [ ] شاشات الديون والدفعات
- [ ] التقارير والإحصائيات
- [ ] PIN / حماية
- [ ] نظام تحديث تلقائي
- [ ] APK نهائي

---

*آخر تحديث: 2026-10-31*
