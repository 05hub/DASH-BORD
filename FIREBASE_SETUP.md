# إعداد Firebase للتطبيق 🔥

## خطوات الإعداد:

### 1️⃣ إنشاء مشروع Firebase
- اذهب إلى [Firebase Console](https://console.firebase.google.com)
- انقر على "إضافة مشروع" (Add Project)
- أدخل اسم المشروع (مثلاً: "5HUB Dashboard")
- اتبع الخطوات

### 2️⃣ تفعيل Firestore
- من القائمة الجانبية، اختر **Firestore Database**
- انقر على "إنشاء قاعدة بيانات" (Create Database)
- اختر "بدء في وضع الاختبار" (Start in test mode)
- اختر المنطقة الجغرافية

### 3️⃣ نسخ بيانات Firebase Config
- اذهب إلى **Project Settings** (⚙️ الإعدادات)
- اختر **Your apps** ثم انقر على **Web** icon
- انسخ كود Firebase Config
- يجب أن تحصل على شيء مثل:
```javascript
const firebaseConfig = {
  apiKey: "AIzaSyD...",
  authDomain: "your-project.firebaseapp.com",
  projectId: "your-project-id",
  storageBucket: "your-project.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcdef..."
};
```

### 4️⃣ تحديث ملف index.html
- افتح ملف `index.html`
- ابحث عن القسم `Firebase Configuration`
- استبدل كل البيانات الافتراضية بالبيانات الخاصة بك

### 5️⃣ إضافة Firestore Rules (اختياري لكن مهم)
- من **Firestore Database**، اذهب إلى تبويب **Rules**
- استبدل القواعس بهذا:

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{document=**} {
      allow create, read, update, delete: if true;
    }
    match /tasks/{document=**} {
      allow create, read, update, delete: if true;
    }
    match /messages/{document=**} {
      allow create, read, update, delete: if true;
    }
  }
}
```

⚠️ **ملاحظة أمان**: هذه القواعس تسمح للجميع بالوصول. في الإنتاج، استخدم:
```javascript
match /users/{document=**} {
  allow read, update: if request.auth != null;
  allow create: if false; // فقط الإدارة تنشئ
}
```

### 6️⃣ ابدأ الاستخدام! 🚀
- عد إلى `index.html`
- افتحه في المتصفح
- يجب أن يعمل التطبيق الآن

## بيانات الدخول الافتراضية:
| الاسم | اسم المستخدم | كلمة المرور | الدور |
|------|----------|-----------|------|
| المالك | owner | 5hubahmed125007@#$ | مالك |
| المشرف | admin | 5hubadmin123654 | مشرف |
| عضو | user | 123 | عضو |

## الميزات الجديدة:
✅ البيانات تُحفظ على السحابة (Firestore)  
✅ أي شخص يمكنه الدخول من أي جهاز بنفس البيانات  
✅ البيانات متزامنة بين جميع الأجهزة  
✅ لا حاجة لخادم خاص  

## استكشاف الأخطاء:

### ❌ "Firebase not defined"
- تأكد من أن ملف HTML يحتوي على `<script>` الخاص بـ Firebase
- تحقق من الاتصال بالإنترنت

### ❌ "خطأ في الاتصال بخادم البيانات"
- تحقق من بيانات Firebase Config
- تأكد من أنك نسخت البيانات الصحيحة
- جرب تحديث الصفحة

### ❌ "لا توجد بيانات"
- تأكد من أن Firestore تم تفعيله
- تأكد من أن القواعس تسمح بالقراءة والكتابة

---

هل تحتاج إلى مساعدة؟ راجع [Firebase Documentation](https://firebase.google.com/docs)
