# خطة الربط المقترحة (غير مفعلة)

- Netlify: واجهة العرض، دون تضمين مفاتيح سرية أو بيانات تشغيلية. إعداد النشر موجود في netlify.toml.
- Supabase: مشروع تجريبي معزول لقاعدة PostgreSQL وAuth. تفعيل MFA وسياسات RLS وفصل صلاحيات القراءة والكتابة والتحقق من جلسات الدخول على الخادم. لا تستخدم مشروعاً قائماً دون التأكد من الغرض منه. سجل الأحداث الإنتاجي يتطلب حماية مستقلة من العبث؛ مجرد جدول PostgreSQL لا يكفي.
- Cloudflare: R2 خاص للمستندات العامة/غير الحساسة، Workers كطبقة خدمات، Workers AI لمساعدة استخدام البرنامج على أدلة غير حساسة فقط. لا تُرسل بيانات هوية أو سجلات فعلية إلى النموذج. لا تنشر مفاتيح R2 أو Supabase في المتصفح. لا تُفعّل خدمات مدفوعة دون موافقة.
- وثائق: https://docs.netlify.com/ ، https://supabase.com/docs/guides/auth ، https://supabase.com/docs/guides/database/postgres/row-level-security ، https://developers.cloudflare.com/r2/ ، https://developers.cloudflare.com/workers-ai/

هذه قائمة متطلبات للربط وليست ربطاً مفعلاً. الاستضافة السحابية لا تعادل شبكة داخلية مغلقة.
