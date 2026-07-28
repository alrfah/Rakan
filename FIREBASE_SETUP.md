# إعداد Firebase لمشروع ديوان

1. من Firebase Console افتح **Authentication > Sign-in method** وفعّل **Email/Password**. هذا يحل خطأ `auth/configuration-not-found`.
2. أنشئ حساب المدير في Authentication وتأكد أن UID هو `n4KBfNzDe3hkkA4FyzfUw9uPycF3`.
3. أنشئ Realtime Database في المشروع `alrfahchat`.
4. انشر القواعد: `firebase deploy --only database`.
5. انشر الوظائف الإدارية: `firebase deploy --only functions`.
6. ضع قيمة بسيطة مثل `true` في `admins/n4KBfNzDe3hkkA4FyzfUw9uPycF3` إن أردت توثيق المدير في البيانات.

لا تنشئ مستخدمين من واجهة Firebase Web مباشرة. لوحة المدير تستدعي Cloud Functions، وهي وحدها تستخدم Admin SDK لإنشاء وحذف حسابات Authentication وتغيير كلمات المرور.