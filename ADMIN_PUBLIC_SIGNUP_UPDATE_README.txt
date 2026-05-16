تحديث إنشاء حساب الإدارة المباشر

تم تعديل admin.html بحيث يظهر زر: إنشاء حساب إدارة جديد.

ما الذي تغير؟
- إنشاء حساب Firebase Authentication مباشر من صفحة دخول الإدارة.
- بعد إنشاء الحساب يتم ربط UID تلقائياً في:
  tenants/{tenantId}/admins/{uid} = true
  user_tenants/{uid}/{tenantId} = admin
  tenants/{tenantId}/admin_profiles/{uid}
- تم تعديل firebase-rules.json ليسمح للحساب الجديد بكتابة صلاحية admin لنفسه.

مهم جداً:
هذا الوضع يعني أن أي شخص لديه رابط admin.html يستطيع إنشاء حساب إدارة لنفسه على الأكاديمية الحالية. استخدمه فقط إذا كنت تريد هذا السلوك فعلاً، وارفع firebase-rules.json الجديد إلى Firebase Realtime Database Rules حتى يعمل الربط تلقائياً.
