# 5HUB Dashboard - لوحة تحكم الفريق

## 🎉 تحديث جديد: الآن مع Firebase!

السابق: كانت البيانات تُحفظ محلياً على جهازك فقط  
**الآن**: البيانات تُحفظ على السحابة! ☁️

### ✨ الفوائد الجديدة:

✅ **تسجيل دخول من أي جهاز** - استخدم نفس بيانات الدخول من هاتفك أو كمبيوترك  
✅ **بيانات متزامنة** - جميع المستخدمين يرون نفس البيانات  
✅ **آمن وموثوق** - بيانات على خادم Google  
✅ **بدون تكاليف** - Firebase توفر خطة مجانية كافية  

---

## 🚀 البدء السريع

### ✅ كل شيء متصل الآن!
- **Firebase Project**: hub-f480a
- **الحالة**: جاهز وفعّال
- **index.html**: متصل ومجاهز

### افتح التطبيق فوراً:
1. فتح `index.html` في متصفح
2. دخّل: `owner` / `5hubahmed125007@#$`
3. جرّب من جهاز آخر - نفس البيانات!

---

## 📋 المهام والعمليات

### المالك (Owner) يمكنه:
- ✏️ إضافة/تعديل/حذف المستخدمين
- 📝 إنشاء المهام
- 🔒 إغلاق/فتح الشات
- 📊 عرض التقارير
- ⚙️ إعدادات المستخدم

### المشرف (Admin) يمكنه:
- 📝 إنشاء المهام
- 🔒 إغلاق/فتح الشات
- 📊 عرض التقارير
- ⚙️ إعدادات المستخدم

### العضو (Member) يمكنه:
- ✅ قبول المهام
- ✔️ إكمال المهام
- 💬 التحدث في الشات
- ⚙️ عرض بيانات المستخدم

---

## 🔧 التكوين

### تغيير بيانات الدخول الافتراضية
افتح `index.html` وجد:
```javascript
const defaultUsers = {
  owner: { password: 'كلمتك', label: 'اسمك', role: 'owner', ... },
  admin: { password: 'كلمتك', label: 'اسمك', role: 'admin', ... },
  user: { password: 'كلمتك', label: 'اسمك', role: 'member', ... }
};
```

### إضافة بيانات Firebase
البحث عن `Firebase Configuration` في `index.html`:
```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "your-project.firebaseapp.com",
  projectId: "your-project-id",
  // ... إلخ
};
```

---

## 📦 البيانات المحفوظة على Firebase

### Collections:

#### 1. `users` - بيانات المستخدمين
```javascript
{
  username: "string",        // اسم الدخول
  password: "string",        // كلمة المرور
  label: "string",          // الاسم الظاهر
  role: "owner|admin|member", // الدور
  email: "string",          // البريد الإلكتروني
  online: boolean,          // متصل أم لا
  blocked: boolean,         // محظور أم لا
  createdAt: timestamp,
  updatedAt: timestamp
}
```

#### 2. `tasks` - المهام
```javascript
{
  title: "string",
  files: ["string"],
  comment: "string",
  assignedTo: "username",
  accepted: boolean,
  completed: boolean,
  completedBy: "username",
  completionMessage: "string",
  createdAt: timestamp,
  updatedAt: timestamp
}
```

---

## ⚙️ المزيد من الخيارات

### تغيير كلمات المرور الثابتة
في `index.html`:
```javascript
const ownerLoginPassword = '5hubahmed125007@#$';  // غيّر هنا
const adminPassword = '5hubadmin123654';          // غيّر هنا
```

### تخصيص أسماء الأدوار
جد `getDisplayName()`:
```javascript
function getDisplayName(role) {
  if (role === 'owner') return 'المالك';
  if (role === 'admin') return 'المشرف';
  return 'مجهول';
}
```

---

## ❓ الأسئلة الشائعة

**س: هل بيانات المستخدمين آمنة؟**  
ج: نعم، Firebase توفر تشفير وحماية. في الإنتاج، يجب تحديث Firestore Rules.

**س: ماذا لو فقدت الاتصال بالإنترنت؟**  
ج: قد لا تتمكن من تسجيل الدخول لكن البيانات ستُحفظ عند العودة للاتصال.

**س: كم عدد المستخدمين الذي يمكنني إضافته؟**  
ج: بلا حد! Firebase توفر خطة مجانية تحتمل آلاف المستخدمين.

**س: كيف أحذف بيانات المستخدم؟**  
ج: فقط اضغط على زر الحذف في قسم الإدارة.

---

## 📞 الدعم والمساعدة

- 📖 [Firebase Documentation](https://firebase.google.com/docs)
- 🐛 تحقق من Console للأخطاء: `F12` → `Console`
- 📧 تواصل عبر WhatsApp: 201275716588

---

**الإصدار**: 2.0 مع Firebase  
**تاريخ التحديث**: 2026  
**الحالة**: ✅ يعمل بكفاءة
