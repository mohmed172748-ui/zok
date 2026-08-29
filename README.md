# ZOK STORE Discord Bot

بوت Discord لإدارة مخزون الحسابات والطلبات لمتجر ZOK STORE.

## المتطلبات
- Node.js 20 أو أحدث
- PostgreSQL 14 أو أحدث
- تطبيق Bot من Discord Developer Portal مع صلاحيات `applications.commands` و`bot`

## التشغيل
1. انسخ `.env.example` إلى `.env` وضع `DISCORD_TOKEN` و`CLIENT_ID` و`GUILD_ID` و`DATABASE_URL`.
2. أنشئ قاعدة البيانات ثم نفذ `schema.sql`:
   `psql -d zok_store -f schema.sql`
3. شغّل `START.BOT` أو نفذ `npm install` ثم `npm start`.

يتم تسجيل الأوامر في `GUILD_ID` فورًا للتجربة. احذف `GUILD_ID` بعد النشر العام لاستخدام التسجيل العام.

## الأوامر
- `/stats url:` يقرأ بيانات TikTok العامة إن كانت متاحة دون تجاوز الحماية.
- `/set-log-channel channel:` و`/set-min-views views:` للإدارة.
- `/add-inventory username:` لإضافة عنصر.
- `/عرض-المخزون` لعرض ملخص المخزون.
- `/ازالة-مخزون username:` لحذف عنصر متاح.
- `/حذف-مخزون-كامل` لحذف كامل المخزون بعد تأكيد نصي.
- `/deliver member: method: quantity: data:` للتسليم التلقائي أو اليدوي.

أسماء الأوامر العربية قد لا يقبلها Discord في بعض العملاء، لذلك توجد أوامر إنجليزية بديلة مثل `/inventory` و`/remove-inventory` و`/clear-inventory`. لا يتم حفظ بيانات التسليم اليدوي في السجلات، ويجب عدم إدخال كلمات مرور أو Tokens.

## الأمان
لا تضع التوكن الحقيقي في Git أو ترسله داخل Discord. ملف `.env` مستثنى من Git، والملف المرفق يحتوي قيمًا مكانية فقط.
