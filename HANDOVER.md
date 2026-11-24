# دليل التسليم الكامل — Master Handover Guide
# كل مشاريع آدم (Adam) — لمن يكمل الشغل من بعدنا

> **آخر تحديث:** 2026-11-24 ~10:50 EET — كتبه Muse (مساعد آدم).
> **الغرض:** أي شخص أو AI يقرأ هذا الملف يقدر يكمل شغل آدم من غير ما يسأله أسئلة بديهية.
> **القاعدة الذهبية:** لا تكتب أي كلمة سر أو مفتاح API أو كود تحقق في هذا الملف أبداً — أماكن الأسرار مكتوبة، قيمها لأ. (شوف قسم 9 — سياسة الأسرار.)
> **لغة الملف:** عربي (مصري) + مصطلحات تقنية إنجليزية زي ما آدم متعود.

---

## فهرس المحتويات

1. [آدم — مين هو وإزاي تشتغل معاه](#1-آدم--مين-هو-وإزاي-تشتغل-معاه)
2. [جرد المشاريع — الحالة الحالية والخطوة الجاية](#2-جرد-المشاريع--الحالة-الحالية-والخطوة-الجاية)
3. [الحسابات والريبو وأماكن الملفات](#3-الحسابات-والريبو-وأماكن-الملفات)
4. [إجراءات البناء والنشر لكل مشروع](#4-إجراءات-البناء-والنشر-لكل-مشروع)
5. [دروس صعبة / Gotchas — لا تعيد الغلط](#5-دروس-صعبة--gotchas--لا-تعيد-الغلط)
6. [قائمة DO NOT RETRY — حاجات متجربهاش تاني](#6-قائمة-do-not-retry--حاجات-متجربهاش-تاني)
7. [أسئلة وقرارات معلّقة عند آدم](#7-أسئلة-وقرارات-معلّقة-عند-آدم)
8. [الأتمتة الشغالة (crons)](#8-الأتمتة-الشغالة-crons)
9. [سياسة الأسرار](#9-سياسة-الأسرار)
10. [أوامر سريعة Cheat Sheet](#10-أوامر-سريعة-cheat-sheet)

---

## 1. آدم — مين هو وإزاي تشتغل معاه

### مين آدم
- **الاسم:** آدم (Adam). مصري، عايش في أمريكا. رسايله بتوصل بتوقيت **Africa/Cairo (EET)**.
- **اللغة:** عربي مصري مباشر وقصير. **كل الردود عليه لازم تكون بالعربي المصري، قصيرة ودافئة ومباشرة** — مش شرح تقني طويل.
- **الجهاز:** موبايل بس — **OPPO Reno15 F 5G**. مفيش كمبيوتر، مفيش كارت بنكي، ومفيش فلوس دلوقتي. أي شغل لازم يشتغل على موبايله.
- **بيحكم على الشغل من اللي يشوفه على موبايله** — مش من الشرح. أي إصلاح لازم يتأكد بصورة/سكرين شوت قبل ما يتقال إنه شغال.

### قواعد التعامل (دي مش اقتراحات — دي قواعد اتعلمت بالتجربة)
- **"ابشرني"** = ابدأ بالخبر الحلو أولاً، وبعدين التفاصيل.
- **"ايه كل دا"** = اختصر في سطرين. الشرح الطويل بيضايقه.
- **متوعدش أبداً بوقت تسليم أو ملف قبل ما يوصل فعلاً.** لو حاجة لسه متبعتتش، قول "لسه" بصراحة.
- **اتأكد قبل ما تدّعي:** أي نسخة APK لازم تتأكد منها بـ curl (HTTP 200 + الحجم + MD5) قبل ما تبعت الرابط لآدم. وأي إصلاح بصري لازم يتأكد من سكرين شوت على موبايله هو.
- **قوله الحقيقة زي ما هي:** لو حاجة شغالة جزئياً (مثلاً 38 حلقة من 52)، قوله الرقم الحقيقي. متجمّلش.
- **قراراته نهائية:** لما يقول "سيبك من كذا" أو "متعملش كذا تاني"، ده قرار — متناقشوش ولا ترجع الحاجة اللي شالها (مثال: الـ waves في Snake Colony اتشالت بقراره، والترجمة المخترعة اتشالت لسبب).
- **لما يقول إن حاجة بتاعته، صدّقه واشتغل** — متعيدش النقاش (مثال: أكد إن فيديوهات "الرسالة الأخيرة" بتاعته، وإن تطبيق Instinct على GitHub بتاعه هو).
- **متعملش حسابات ولا توافق على شروط ولا تختار دولة/عملة/ضرايب/دفع بالنيابة عنه** من غير إذنه الصريح وبياناته هو.
- **مصاريف بس المجانية أو اللي وافق عليها صراحة.** متدفعش، متشتركش، متصرفش أي حاجة زيادة.

### حدود عامة
- **حقوق النشر:** محتوى يملك حقوقه أو مرخّص فقط — ممنوع كليبات أفلام/مسلسلات أو أي محتوى مسروق.
- **الـ keystores:** أي keystore يضيع = التطبيق مينفعش يتحدث أبداً. حافظ عليها وخلّيها ظاهرة في كل دليل.
- **السرية:** دخول الأدمن في CineReels سرّي تماماً بين آدم وMuse — لا يُذكر اسمه ولا كلمة سره في أي شات ولا أي ملف عام. اكتب بس "دخول أدمن موجود؛ اسأل آدم". (تفاصيل أكتر في قسم 9.)

---

## 2. جرد المشاريع — الحالة الحالية والخطوة الجاية

### 2.1 Snake Colony — لعبة Godot 4.3 (المشروع الأول)

- **إيه هي:** لعبة حضارات ثعابين (cobra / python / mamba) — بناء قاعدة + معارك أرينا 5v5 أونلاين.
- **التقنية:** Godot 4.3. كود المشروع في `~/workspace/snake-colony-work/snake_colony/` (فيه `project.godot` + `export_presets.cfg`).
- **الحالة الحالية — v3.6.2 (versionCode 4):**
  - أونلاين حقيقي بـ **Nakama** شغال ومتأكد بماتش حقيقي بين لاعبين اتنين على Railway (2026-11-22).
  - **مفيش waves** — اتشالت في الـ pivot بتاع v3.0 (2026-11-21). اللعبة 5v5 أونلاين، أرينا عشوائية عند البحث عن ماتش، بوتات بتملا الأماكن الفاضية، نظام جنود ستايل Lords Mobile (أنواع + counters + tiers)، مهارات ستايل League of Legends (passive + Q/W/E/R، ليفل داخل المعركة، R بتتفتح ليفل 6).
  - المعارك لازم تبقى أطول وأمتع، مش بتخلص بسرعة (طلب آدم).
  - الـ potions تظهر كقوارير إكسير صغيرة فوق أزرار المهارات، واضحة بعددها.
  - أيقونات المهارات مرسومة ستايل LoL، وزر النشر (Space) لازم يبقى أيقونة مرسومة زيهم مش سهم أخضر عادي.
- **السيرفر (Nakama):**
  - Nakama v3.26.0 + CockroachDB v24.3.9. شغال محلياً هنا من غير Docker (binaries في `~/workspace/snake-colony-work/nakama/`، API على `:7350`، console على `:7351`).
  - **الافتراضي الحي:** Railway host `mainline.proxy.rlwy.net:58627` (مكتوب في `online.gd`؛ إعدادات اللاعب override بتكسب).
  - Matchmaker: `+properties.mode:5v5`، min 2 / max 10، timeout 15 ثانية → fallback للبوتات.
  - **Gotcha مهم:** السيرفر لازم يشتغل بـ `--matchmaker.interval_sec 1 --matchmaker.max_intervals 1` (الافتراضي بيطابق بعد 30 ثانية).
  - الـ client: Nakama SDK v3.4.0، autoloads `Nakama` + `Online`؛ دخول بالـ device ID (persistent) + اسم حساب، وإلا guest. الـ damage بيتبعت لصاحب الثعبان (مفيش double damage).
  - الاستضافة الذاتية لو حب VPS: Hetzner CX23 (~€5.49–5.99/شهر ex-VAT، ~$7) هو المقترح؛ DigitalOcean $6/شهر minimum. مفيش خطة Nakama بـ $5 — مفيش أصلاً. السكربت: `~/workspace/snake-colony-work/nakama-vps-setup.sh` (بيتنفذ كـ root على الـ VPS)، وملفات Railway في `~/workspace/snake-colony-work/railway-nakama/` (Dockerfile + entrypoint.sh + railway.json).
- **الملفات المسلمة:**
  - APK (v3.6.2، 113,828,170 بايت) على Google Drive — file id `1CAx4PIElPCrLboNotfXxNvoH6R_ZVZ3u`.
  - ZIP للمشروع — Drive `1kHYyuyOQiOk54xgMNzbe27QLOxkXSnPG`.
  - Web ZIP لـ itch.io — Drive `1-do4iVKn8qqeMsdSKmgyX-ojAtA70mku` (الرابط اتبعت لآدم 2026-11-23).
  - ريبو GitHub: `https://github.com/adam2211dmdm-ux/snake-colony-nakama` (Dockerfile/start.sh/README_AR.txt، commit `941b5acd...`).
- **itch.io:** حساب `adam2211dmdm-ux`. أول play test فشل (`'.pck file missing?'`) — الـ web zip نفسه سليم (`index.pck` 43,890,208 بايت) والسبب غالباً رفع ناقص أو نت بطيء (6 KB/s). اتقاله يرفع تاني على Wi-Fi ويضغط Restore. **لسه متأكدش إنه اشتغل.**
- **الإعلانات — نقطة مهمة:** الـ APKs المشحونة فيها **إعلانات محاكاة (3 ثواني countdown) مش AdMob حقيقي**. كود AdMob الحقيقي + الـ IDs موجودة في الكود و`ADMOB_REAL=true`، بس الـ APK الحقيقي بالإعلانات محتاج custom Gradle build — **والـ build ده متعطّل هنا (قسم 6) — متحاولش تاني.** آدم لسه بيسأل إزاي يعمل الإعلانات الحقيقية بنفسه وليه اللي فاكرها اتضافت مش شغالة — الفرق ده لسه مش محسوم عنده.
- **الخطوة الجاية:** آدم ناوي يبني اللعبة بنفسه على موبايله في Godot، وسأل إزاي يضيف الإعلانات الحقيقية في الـ build بتاع الموبايل. كمان لسه مهتم يتعلم يعمل كود حديث زي ريبو PUBG Mobile External ESP اللي شاركه (`https://github.com/NotName1999/Pubg-Mobile-External-ESP`).

### 2.2 CineReels — تطبيق مسلسلات قصيرة (المشروع الرئيسي دلوقتي)

- **إيه هو:** تطبيق أندرويد Native Java (package `com.cinereels.app`) — فيديوهات عمودية قصيرة ستايل DramaBox/ReelShort: فيد عمودي، تشغيل تلقائي متتابع (الحلقة تخلص → عد تنازلي 3 ثواني → اللي بعدها)، ترجمة عربي/إنجليزي، تصنيفات، بحث، مفضلة، سجل مشاهدة، حسابات + دخول، لوحة أدمن.
- **النموذج:** DramaBox — **أول 25 حلقة مجاناً، بعدها اشتراك**. اشتراك يدوي (واتساب + فودافون كاش) — شوف قسم الاشتراكات تحت.
- **الحالة الحالية — v1.26 (versionCode 27) — DELIVERED والرابط اتبعت لآدم 2026-11-24 10:45 EET (يمسح القديم الأول):**
  - **تم التحقق الحي 2026-11-24 ~10:50 EET:** `https://adam2211dmdm-ux.github.io/CineReels-v1.26.apk` = **HTTP 200**، الحجم **1,300,586 بايت**، MD5 = **`193bae916eb49fba07274300ff3d9ba3`** (مطابق للـ build)، و`index.html` بتقول v1.26. الـ manifest الحي فيه **198 فيديو / 5 مسلسلات** (commit `3ed4f7b`)؛ الـ APK اترفع من المتصفح (commit `e41ef07`).
  - **الجديد في v1.26:** (1) **Admin provider picker — 7 مزودين شغالين + 'random from all'** (المستبعدين: ShortMax وMelolo وGoodShort وDramaNova — شوف أحكام التشغيل في §2.5)؛ **playback حسب المزوّد** (DramaBox: بناء رابط الـ proxy أوفلاين؛ NetShort: playVoucher؛ ReelShort: ld؛ FreeReels/MyDrama/PineDrama/FlickReels: جلب طازج وقت التشغيل). (2) **زر جلب مسلسل عشوائي بدون تكرار** — كل ضغطة بتضيف مسلسل واحد عشوائي مش موجود أصلاً في الكتالوج (dedupe بـ bookId + العنوان normalized، ومجموعة persistent من الـ bookIds المستوردة، لحد ~10 محاولات لو الاختيار مكرر). (3) معاينة قبل الاستيراد (العنوان + البوستر + عدد الحلقات + الوصف) وآدم بيأكد الاستيراد.
  - **المسلسل الجديد في v1.26:** "انتقام إله الأمواج" (ReelShort، 52 حلقة، روابط `-ld` 540p H264).
  - **⚠️ عيب معروف وصريح — متقدمش v1.26 على إنه 52 حلقة كاملة:** بس **38 من 52** رابط شغالين (HTTP 200). **14 حلقة ميتة (HTTP 404):** 18، 22، 23، 24، 26، 27، 29، 34، 38، 41، 44، 45، 46، 51. اتأكد مرتين بـ curl (mobile UA). الـ `-sd` fallback ميت برضه + H265 = شاشة سوداء على موبايل آدم. الـ 14 دول محتاجين إعادة جلب `videoList` من Sansekai API لما الـ IP blacklist يترفع (قسم 6). **آدم اختار بنفسه (2026-11-24 10:39 EET): ابعت v1.26 دلوقتي مع التنبيه الصريح 38/52.**
  - **لسه متأكدش على موبايل آدم:** لا v1.26 ولا إصلاح الـ blur بتاع v1.25 اتأكدوا منه على موبايله لسه (الجلب من الموبايل، والتشغيل حسب المزوّد، ومكان الـ blur، والـ 14 حلقة الميتة — كلها معلّقة على اختبار موبايله).
- **إصلاح الـ blur (v1.25):** رقعة التمويه فوق شعار ReelShort "R" أعلى الشمال — الـ margins بقت `setMargins(dp(28), dp(75), 0, 0)` في `SeriesActivity.java` و`FeedActivity.java` (الحجم 64dp، gravity `TOP | LEFT`). اتبعت 2026-11-24 07:26 EET. **تأكيد آدم من موبايله لسه معلّق** (اتطلب سكرين شوت مرتين؛ رد "تمام" من غير إجابة).
- **المحتوى الحالي (manifest حي — 198 فيديو):**
  - **"The Last Message / الرسالة الأخيرة"** — 25 حلقة في الكتالوج. الحلقات 1–15 منشورة (مقاطع آدم — 60 ثانية، صوت إنجليزي، ترجمة محروقة في الصورة burned-in). الحلقات 16–25 `coming_soon` (صور picsum مؤقتة). الحلقات 14 و15 نشرهم آدم بنفسه على GitHub. السيناريو الكامل في `cinereels/drama-series/SCRIPT_AR_EN.md` (ليلى + سارة + عمر + خالد؛ النسخة دي لغت الـ outline القديم بتاع العم/البيت/الفلوس).
  - **"A Second Chance / فرصة ثانية"** — رومانسي، 3 حلقات؛ الحلقة 1 منشورة (`videos/romantic-drama-30s.mp4`)، 2–3 `coming_soon`. **آدم لسه ما أكدش إن ملف romantic-drama-30s.mp4 هو فعلاً الحلقة 1.**
  - **narto-runaway-mother** — "الأم العازبة الهاربة وزوجها الملياردير" (56 حلقة، ReelShort، روابط مباشرة 540p H264، أول 25 مجاناً) — **شغالة ومؤكدة على موبايل آدم من v1.21.**
  - **narto-my-revenge** — "انتقامي من زوجي وصديقتي المفضل" (62 حلقة، أول 25 مجاناً) — لسه حلقات ويب (WebView) مش روابط مباشرة، والمزوّد بتاعها مجهول. آدم قال "سيبك من المسلسل التاني" (2026-11-24) — متكملش تدوير عليه إلا لو طلب تاني.
  - **rs-wave-god-revenge** — "انتقام إله الأمواج" (52 حلقة، 38 شغالة — شوف العيب فوق).
  - الفيديوهات التجريبية (Blender open movies) اتمسحت بقرار آدم 2026-11-23 — مفيش أي فيديو تجريبي في الكتالوج.
- **الاشتراكات (يدوي — خارج Google Play بس):**
  - الأسعار (جنيه): **3 أيام 50 / أسبوع 200 / شهر 600**.
  - الرقم: **201080482372** للواتساب وفودافون كاش معاً (مصر حالياً).
  - التدفق: المستخدم يربط Gmail → يختار باقة → طلب برقم `CR-XXXX` + واتساب بيتفتح لآدم → يدفع فودافون كاش → آدم يوافق من الأدمن → فتح لحد تاريخ الانتهاء → قفل تلقائي.
  - **المصدر الحقيقي = GitHub `subscribers.json`** في ريبو `cinereels-videos` (التطبيق بيجيبه عند الفتح وعند كل حلقة؛ نسخة GitHub بتغلب نسخة الجهاز — مسح التطبيق أو اللعب في الداتا المحلية مش بينفع). التطبيق **مش** بيدفع لـ GitHub أبداً (مفيش توكن في الـ APK) — الأدمن بيعمل Export والرفع يدوي.
  - **Play Billing متوقف بقرار آدم.** الدفع اليدوي للتوزيع خارج Google Play بس — Play بيفرض Play Billing على الفتح الرقمي، فلازم يتعطّل قبل أي رفع على Play.
  - صفحة الدخول أول شاشة (دخول / تسجيل / ضيف) مع intro سينمائي. دخول الأدمن موجود بس مخفي تماماً — **لا يظهر ولا يتلمّح له في التطبيق إطلاقاً**، واسأل آدم عنه بس.
- **Monetag (إعلانات صفحة التحميل — مش داخل التطبيق):**
  - الموقع `adam2211dmdm-ux.github.io` **Verified** في Monetag (meta tag في `index.html` — كل تسجيل موقع بيطلع tag جديد؛ القديم بتاع muse.ai ميت).
  - **In-Page Push zone `12329911` شغال** (سكربت `nap5k.com/tag.min.js` بعد `<head>` في الصفحة الحية).
  - صفحة التحميل البديلة في ريبو `cinereels-videos` تحت `docs/index.html`.
  - الإحصائيات بتبدأ من صفر وده طبيعي، بتاخد وقت تتجمع.
  - **مفيش إعلانات داخل التطبيق** بقرار آدم ("لا انا مش عايز اعلانات" — 2026-11-23). أي SDK إعلانات محتاج Gradle (متعطّل — قسم 6). اختيار شبكة الإعلانات (AppLovin MAX / Unity Ads / Meta) لسه معلّق عند آدم.
  - صفحة artifact بتاعة muse.ai مينفعش يتحط فيها سكربت الإعلانات — GitHub Pages هو الحل الوحيد الحي.
- **الترجمة التلقائية:** cron كل 30 دقيقة (قسم 8) — بيفرّغ صوت الحلقات اللي ملهاش ترجمة (faster-whisper tiny) وبيكتشف الترجمة المحروقة في الصورة (detector متأكد منه) وبيترجم EN↔AR وبيكتب .vtt ويحدّث الـ manifest. **الـ push بتاع GitHub مش pre-approvable — كل push بيطلع approval card لآدم.**
- **النسخ السابقة (مختصر):** v1.7 إصلاح كراش R8 (اتأكد على موبايل آدم)؛ v1.13 إصلاح bug الـ manifest (قراءة بايتات دقيقة)؛ v1.17 دخول أول شاشة + intro؛ v1.18 صفحة تسجيل منفصلة (نتيجتها عند آدم مش معروفة)؛ v1.19 استيراد مسلسل من رابط + حلقات ويب narto؛ v1.20 روابط 720p H265 — **مكسورة (شاشة سوداء)**؛ v1.21 إصلاحها بـ H264 540p — **آدم أكد إنها اتصلحت**؛ v1.22 رقعة التمويه (غلط: جت يمين بسبب RTL)؛ v1.23 إصلاح الـ gravity لـ LEFT المطلق؛ v1.24 **التوقيع HMAC اتلغى تماماً** — الـ manifest بيتقبل لو اتحلل وعدّى فحص same-origin/allowed-hosts (مفيش `.sig` تاني)؛ v1.25 تصحيح مكان الرقعة. التفاصيل الكاملة في `~/workspace/your_files/cinereels/CineReels-HANDOVER-GUIDE.md` (§12).
- **الخطوة الجاية:**
  1. تأكيد آدم على موبايله: v1.26 شغالة؟ والـ blur مغطي الـ R؟
  2. إعادة جلب الـ 14 حلقة الميتة لما الـ Sansekai blacklist يترفع.
  3. الـ English harvest (قوائم lang=en + حلقات + ترجمة) — متأجلة بعد شغل التشفير، لسه متعملتش.
  4. اختبار زرار الجلب العشوائي + الـ provider picker على موبايل آدم (مكالمات HTTP من الموبايل لـ Sansekai ممكن Cloudflare يحجبها — غير مؤكد).
  5. حاجات Play listing لسه ناقصة من آدم (قسم 7).

### 2.3 IPTV — تطبيق قنوات عربية — ✅ تم التسليم وقُفل

- **الحالة:** v1.0 تم تسليمه 2026-11-23 والتتبع اتقفل. افتحه تاني بس لو آدم بلّغ عن مشكلة.
- **إيه هو:** `com.adam.iptvplayer`، v1.0 (code 1)، **57 قناة عربية مجانية شغالة** في 10 تصنيفات (أخبار 27، مصر 5، ديني 5، رياضة 4، مسلسلات 4، أطفال 3، موسيقى 3، أفلام 2، وثائقي 2، ترفيه 2 — MBC مصر/ماس/دراما، الجزيرة، العربية، سكاي نيوز عربية، فرانس 24 عربي، RT عربي، كرتون نتورك عربي، سبيستون).
- **المصدر:** iptv-org (اتفحص HTTP 200 + HLS). **beIN/OSN/premium مستبعدة بقرار سياسة** (قنوات مدفوعة)؛ BBC عربي مستبعدة (DASH، محتاجة ExoPlayer/Gradle).
- **الملفات:** APK 29,215 بايت، MD5 `19f2a3f4bb3c21ce451afe490ac512e0`؛ `channels.m3u` للتحديث البعيد على `https://adam2211dmdm-ux.github.io/channels.m3u`؛ كوميت Pages `dba4a07` (اتأكد 200). **متجرّبش على موبايل حقيقي.**
- **Keystore:** `~/workspace/snake-colony-work/keystore/iptv.keystore` (alias `iptv`، SHA-256 `99:5F:58:49:34:AA:96:54:EC:80:F6:58:8F:AC:F2:E0:29:5C:CC:FD:F7:BA:77:A6:FD:0F:74:4C:DE:79:FA:33`) — آدم لازم يحتفظ بيه. كلمة السر في ملف `.pass.txt` جنبه.
- **Gotcha:** `apksigner --ks-pass file:` بيقرا سطرين (store pass + key pass) — ملف سطر واحد بيفشل.

### 2.4 Whiteout Survival bot + Game Assistant APK

- **الفكرة:** آدم بيتعلم ببناء بوت للعبة Whiteout Survival (`com.gof.global`، Century Games) يساعد في البناء/التطوير. اختار **البوت على الموبايل نفسه** (مش محاكي PC).
- **AutoX.js starter:** `workspace/your_files/whiteout-mobile-bot/whiteout_bot.js` + README عربي — نقر بقوالب صور (جمع/فرن/تطوير/إغلاق)، loop كل 5 دقايق، زر خفض الصوت للإيقاف، إعدادات OPPO Reno15 F 5G. **تحذير مسجل: يجرّب على حساب تانوي (خطر ban).**
- **Game Assistant APK v1:** `com.adam.gameassistant`، v1.0، Java بس، من غير Gradle. بيعرض الألعاب المثبتة؛ محرر مهام (Tap/Wait/Swipe، JSON)؛ تدريب بلقطة شاشة عبر MediaProjection؛ تشغيل عبر AccessibilityService + foreground service + زر إيقاف عائم؛ شاشة أذونات بملاحظات OPPO؛ مهمة جاهزة "جمع Whiteout" (إحداثياتها placeholders). **متأكد منه:** 37,353 بايت، MD5 `7fa6df32fe2b1cd7cd815e22dc22ae4d`، apksigner v2+v3، zipalign سليم. **متجرّبش على موبايل حقيقي.**
- **Keystore:** `~/workspace/snake-colony-work/keystore/game_assistant.keystore`، كلمة السر في `.pass.txt` جنبه — آدم لازم يحتفظ بيه للتحديثات.
- **الملفات:** `workspace/your_files/game-assistant-app/` (APK + source zip + README_AR.md + PLAN_AR.md).
- **الحدود:** إحداثيات ثابتة بس — لسه مفيش بحث بالصور/OCR/شروط/جدولة.
- **الخطوة الجاية:** مفيش طلب معلّق — آدم مكمل تعلم، والنسخة الجاية (بحث بالصور/OCR) لسه متطلبتش.

### 2.5 Sansekai API — مصدر المسلسلات الشغالة (CineReels)

- **إيه هو:** API عام مجاني لمسلسلات قصيرة على `https://api.sansekai.my.id` (الـ docs صفحة Swagger على `https://api.sansekai.my.id/`). **مفيش API key** — GET عادي. **Rate limit: 5 طلبات/دقيقة** (headers حية؛ الـ docs بتقول 10) — باعد المكالمات 12–15 ثانية. **ممنوع تشغيل مهمتين browser على Sansekai في نفس الوقت** (هيتجاوزوا الليمت مع بعض).
- **ملاحظة تشخيصية مهمة:** curl من الـ VM بيرجع 403 (`{"error":"Forbidden","message":"LO KONTOL."}`) — دي حماية Cloudflare ضد الطلبات غير المتصفح، مش نقص مفتاح. **المتصفح الحقيقي بيشتغل.** الـ endpoint بتاع الحلقات هو **`/dramabox/get-allepisode`** (مش `/allepisode`)، وبطيء (~40 ثانية لـ ~80 حلقة).
- **11 مزوّد:** DramaBox، ReelShort، ShortMax، GoodShort، NetShort، DramaNova، FlickReels، FreeReels، Melolo، MyDrama، PineDrama. (فيه كمان Komik/MovieBox/Viu — مش مسلسلات قصيرة.)
- **الحصاد batch 1 (2026-11-24 07:35–08:21 EET):** سجله الكامل في `~/workspace/your_files/cinereels/sansekai-harvest-batch1.md` — top-5 lists، endpoints، أسماء الحقول، والأحكام، وكل روابط ReelShort الـ 52.
- **الحصاد batch 2 (2026-11-24 09:47 EET):** سجله في `~/workspace/your_files/cinereels/sansekai-harvest-batch2.md` (الـ task الأول errored والـ recovery جاب Parts B/C/D كاملة وPart A جزئية).
- **أحكام التشغيل (Part D — أولوية آدم القصوى):**
  | المزوّد | الحكم | التفاصيل |
  |---|---|---|
  | **ReelShort** | ✅ **الوحيد بروابط مباشرة ثابتة** | `videoList[].url` — مفيش token/expiry. استخدم **540p H264 `-ld`**، مش 720p H265 `-sd` (شاشة سوداء على موبايل آدم). **الـ token بتاع `-ld` بيختلف كل حلقة — مينفعش تشتقه من `-sd`؛ لازم تجيب videoList كل حلقة.** |
  | **DramaBox** | ✅ شغال | ملفات `.encrypt.mp4` مشفرة؛ ابنِ رابط الـ proxy `get-decrypt-video?url=…` **أوفلاين من غير مكالمات API زيادة** (اتأكد إنه شغال). الجودات 1080/720/540/360/144، الافتراضي 720p، و1080p VIP. |
  | **NetShort** | ✅ شغال | `playVoucher` mp4 مباشر (اتأكد). بس الـ `foryou`/`theaters` بـ lang=ar بترجع `null` — الـ top list جت من `lang=id` (عناوين إندونيسي). |
  | **ShortMax** | ❌ **مش شغال بمشغّل عادي** | تشفير قطاعات مخصص: header 1040 بايت 'shortmax'، مفتاح AES 16 بايت مضمّن، أول 1024 بايت AES-128-CBC بـ IV `shortmax00000000`. محتاج proxy HLS من السيرفر أو ExoPlayer DataSource مخصص — وExoPlayer محتاج Gradle (متعطّل). مفيش endpoint فك تشفير في Sansekai. |
  | **GoodShort** | ❌ مفيش ستريمات أصلاً | metadata بس — متستخدمهوش للتشغيل من الـ API ده. |
  | **FreeReels** | ✅ مباشر/ثابت (56/56) | 'My Ex Gave Me to the Coconut Mayor'، id `hKpitmwIz8` — بس روابط الحلقات **موصلتش في الـ summary**، محتاجة إعادة جلب. |
  | **MyDrama** | ✅ مباشر/ثابت | 'A Queen for the Mafia Kings'، 90 حلقة، `cdn.my-drama.tv` main.m3u8 — بس الحلقة 1 بس اللي اتجابت. |
  | **PineDrama** | ⚠️ tokenized | 76 حلقة (1–25 اتجابت، 26–76 ناقصة، الروابط مش في الـ summary). |
  | **Melolo** | ⚠️ tokenized/encrypted | 72 حلقة (الحلقة 1 بس). |
  | **FlickReels** | ⚠️ tokenized | 80 حلقة (الحلقة 1 بس). |
  | **DramaNova** | ❓ | **مش موجود أصلاً في docs الـ API.** |
- **أهم المسلسلات (lang=ar):**
  - DramaBox: "وداع بلا ندم (مدبلج)" `42000001128`، 65 حلقة.
  - ReelShort: "انتقام إله الأمواج" `6adabb702d149b359f09097c`، 52 حلقة (اتخبزت في v1.26 — 38/52 شغالة)؛ "أخوهم، قربان التنانين" `6adb1792e617791aa509e88f`، 50 حلقة؛ "لولو الإلهة الصغيرة" `6ad5e84ea0f7d495980630bf`، 61 حلقة؛ "متحدث التنانين بلا قيود" `6aca0e86879cac5ec505e33e`، 47 حلقة.
  - ShortMax: "[مدبلج]حياتي ليست لعبة" `59074`، 25 حلقة.
  - GoodShort: "المدبلج-نساء الزوج البطل" `31001928423`، 61 حلقة (metadata بس).
  - NetShort: "Ibu Rahasia Sang Pewaris Serigala" `2124348784462745602`، 36 حلقة.
- **⚠️ الـ API IP blacklist:** من 2026-11-24 الصبح، الـ API بيرجع Cloudflare 502 → "bandwidth limit" → رسالة إندونيسي "IP blacklisted". اتأكد 07:41 UTC لسه محظور. **متحاولش تتخطاه بـ proxies — ممنوع.** الحلقات الناقصة محتاجة IP مش محظور بعدين.
- **ملحوظة:** عناوين إنجليزية مش بترجع للكتب دي — قوائم `lang=en` ترتيبات مختلفة مش ترجمات.
- **`dramabox.sansekai.my.id` واقع:** كل الطلبات Cloudflare Error 522 "Connection timed out" (اتفحص 2026-11-24 07:22–08:20 EET). جرّب تاني بعدين — أولوية واطية؛ الـ harvest من `api.sansekai.my.id` هو الطريق الشغال.

### 2.6 narto-drama.com — موقع آدم للمسلسلات

- **الموقع بتاع آدم** (أكّد ملكيته 2026-11-23). الكتالوج الكامل في `~/workspace/your_files/cinereels/narto-site-catalog.md` — **77 مسلسل عربي** (5 featured + 24 في كل صفحة كتالوج 1–3؛ صفحة رابعة موجودة ومتجمعتش).
- **"ND" هو label الموقع نفسه مش مزوّد** — الكتالوج العربي مفيهوش badge مزوّد لكل مسلسل. الطريقة الوحيدة تعرف مزوّد مسلسل هي تدوير على عنوانه في الـ gateway.
- **الدراما 1 — محلولة وشغالة:** "الأم العازبة الهاربة وزوجها الملياردير" (56 حلقة) — ReelShort Arabic book `6ae163e2ef56d22b5e020027` (مدبلج `is_dub: 1`، `paid_start: 14`)؛ الروابط AliyunOSS ثابتة (`v-mps.crazymaplestudios.com`)، من غير token/expiry؛ `urls[1]` = 540p H264 `-ld.m3u8` (هو المستخدم)؛ `urls[0]` = 720p H265 (ممنوع — شاشة سوداء)؛ `urls[2]` = master H265 (ملوش لازمة). الترجمة العربية محروقة في الصورة (اتأكدت بصرياً). الملفات: `narto-runaway-mother-streams.json` + `narto-runaway-mother-detail.json` في `~/workspace/your_files/cinereels/`.
- **الدراما 2 — اتسابت بقرار آدم** ("سيبك من المسلسل التاني دا هاتلي اي مسلسلات شغاله" — 2026-11-24 07:34 EET). مزوّدها لسه مجهول (مش dramabox ولا reelshort ولا على Sansekai). متكملش التدوير عليها إلا لو طلب.
- **الـ gateway بتاع آدم:** `https://api.narto-drama.com/` (header `X-Api-Key`؛ الخطة المجانية $0: **50 طلب/ساعة، مزوّد واحد، مفتاح واحد**). المفاتيح اتبعتت في الشات باختيار آدم و**قيمها مش مسجلة في أي مكان — استخدمت transient في curl بس. متطلبهاش تاني منه؛ لو مفتاح اتحتاج، اعرض رابط الـ secure capture الأول.** رابط secure capture اتبعت 2026-11-24 00:42 EET ولسه مفيش رد.
- **مشغّل الموقع نفسه مقفول بإعلانات** (play → "افتح 6 من 6 إعلانات") ومفيش رابط ستريم مباشر في الصفحة، وcurl من الـ VM محجوب بـ Cloudflare. **آدم مش عايز إعلانات في التطبيق.** الموقع بيفتح popunder 1xBet عند الضغط على حلقة.
- **مسلسلات narto المرشحة من الكتالوج (featured):** "عروس بديلة تغزو الأثرياء" (40 حلقة)، "ندمت الإمبراطورة على خسارتي" (51)، "أستاذهم العراب" (50)، "حصلت على ثلاث حبيبات من النظام" (30) — آدم لسه مختارش منها.

---

## 3. الحسابات والريبو وأماكن الملفات

### الحسابات
| الخدمة | الحساب | ملاحظات |
|---|---|---|
| GitHub | `adam2211dmdm-ux` | الإيميل `adam2211dmdm@gmail.com` (جديد — فيه رسايل إعداد بس). GitHub App API **مش** بيعمل repos (403 "Resource not accessible by integration") — الـ repos اتعملت من المتصفح. تسجيل الدخول من المتصفح بيحتاج كود جهاز بيتبعت على الجيميل كل مرة. الـ OAuth app "Instinct" (repo scope) **بتاع آدم هو** (أكّد بنفسه 2026-11-24) — **متبلغش عنه إنه مشبوه تاني.** |
| Gmail (إعدادات) | `adam2211dmdm@gmail.com` | رسايل الإعداد بس. |
| Gmail (اللعبة) | `karimbakr20@gmail.com` | إيميل اللعبة بتاع آدم. |
| itch.io | `adam2211dmdm-ux` | يخص Snake Colony. |
| Monetag | موقع `adam2211dmdm-ux.github.io` | Verified؛ In-Page Push zone `12329911`. |
| Google Drive | حساب آدم المتصل | فيه APKs (Snake Colony v3.6.2 + CineReels v1.4). |

### الريبو (GitHub — `adam2211dmdm-ux`)
| الريبو | إيه فيه | الرابط |
|---|---|---|
| `cinereels-videos` | كتالوج CineReels (`videos.json` + `videos.json.sig` — الـ `.sig` قديم ومتقريش من v1.24 — + `subscribers.json` + فيديوهات + ثمبنيلز + ترجمات) | `https://github.com/adam2211dmdm-ux/cinereels-videos` |
| `adam2211dmdm-ux.github.io` | موقع صفحة التحميل (user Pages site، main root): `index.html` + ملفات APK + `HANDOVER.md` (هذا الملف) + `channels.m3u` | `https://github.com/adam2211dmdm-ux/adam2211dmdm-ux.github.io` |
| `snake-colony-nakama` | سيرفر Nakama على Railway (Dockerfile/start.sh/README_AR.txt) | `https://github.com/adam2211dmdm-ux/snake-colony-nakama` |
| `cinereels-videos` (docs) | صفحة التحميل البديلة `docs/index.html` | نفس ريبو cinereels-videos |

**الـ manifest اللي التطبيق بيجيبه:** `https://raw.githubusercontent.com/adam2211dmdm-ux/cinereels-videos/main/videos.json`
**صفحة التحميل الحية:** `https://adam2211dmdm-ux.github.io/`
**رابط APK المباشر (النمط):** `https://adam2211dmdm-ux.github.io/CineReels-vX.Y.apk`

### أماكن الملفات المحلية (على جهاز الـ agent)
```
~/workspace/your_files/cinereels-apk/     ← كود CineReels (الأصل؛ symlink لـ goals/cinereels-short-video-app/files/cinereels-apk/)
  src/com/cinereels/app/*.java            ← كل الأكواد
  res/values/strings.xml + res/values-ar/strings.xml
  AndroidManifest.xml                     ← versionCode/versionName هنا
  build.sh                                ← سكربت البناء
  proguard-rules.pro                      ← قواعد R8
  assets/videos.json                      ← نسخة manifest مضمّنة (fallback) — نسخة منفصلة، زامنها قبل كل build
  assets/subtitles/*.vtt
  tools/sign_manifest.py                  ← توقيع manifest (متقريش من v1.24 بس موجود)
  out/                                    ← مخرجات البناء

~/workspace/your_files/cinereels/         ← المحتوى والحصاد
  github-videos/                          ← نسخة محلية من ريبو cinereels-videos (videos.json + subscribers.json + subtitles/)
  github-videos.muse-github-snapshot-sync.json  ← سجل مزامنة الـ push
  pages-site.muse-github-snapshot-sync.json     ← سجل مزامنة ريبو Pages
  CineReels-HANDOVER-GUIDE.md             ← دليل CineReels التفصيلي (v1.19 — اقرأه مع هذا الملف)
  drama-series/SCRIPT_AR_EN.md            ← سيناريو "الرسالة الأخيرة"
  transcripts/                            ← تفريغ صوت الحلقات (whisper)
  sansekai-harvest-batch1.md / sansekai-harvest-batch2.md
  narto-site-catalog.md                   ← 77 مسلسل من narto-drama.com
  narto-runaway-mother-streams.json / narto-runaway-mother-detail.json
  narto-gateway-notes.md
  tools/auto_translate.py                 ← watcher الترجمة التلقائية
  tools/add_narto_series.py
  support/bugs.md                         ← سجل bugs من ترياج الدعم

~/workspace/snake-colony-work/
  snake_colony/                           ← مشروع Godot (project.godot + export_presets.cfg)
  keystore/
    snake_colony.keystore                 ← Snake Colony (alias snake_colony) + .keystore_pass.txt جنبه
    cinereels.keystore                    ← CineReels (alias cinereels) + .cinereels_pass.txt جنبه
    game_assistant.keystore               ← Game Assistant + .pass.txt جنبه
    iptv.keystore                         ← IPTV (alias iptv) + .pass.txt جنبه
  cinereels-hmac.key                      ← مفتاح توقيع manifest (HEX-encoded — شوف قسم 5) — chmod 600
  nakama/                                 ← Nakama 3.26.0 + CockroachDB 24.3.9 binaries (API :7350، console :7351)
  nakama-vps-setup.sh                     ← سكربت إعداد VPS
  railway-nakama/                         ← Dockerfile + entrypoint.sh + railway.json
  android-sdk/                            ← SDK (build-tools 34.0.0 + platforms/android-35)
  jdk17/                                  ← Temurin JDK 17
  bundletool-all-1.17.2.jar
  gradle-8.2-bin.zip + local-maven/       ← بقايا محاولة Gradle المتعطلة (قسم 6)
  v3.0-spec.md                            ← مواصفات الـ pivot بتاع v3.0

~/workspace/your_files/whiteout-mobile-bot/   ← whiteout_bot.js + README_AR.md
~/workspace/your_files/game-assistant-app/    ← GameAssistant-v1.apk + source zip + README_AR.md + PLAN_AR.md
~/workspace/your_files/handover/HANDOVER.md   ← هذا الملف (نسخته المحلية)
~/workspace/whisper-venv/                 ← venv فيه faster-whisper (للتفريغ)
~/workspace/goals/snake-colony-game-development/GOAL.md
~/workspace/goals/cinereels-short-video-app/GOAL.md
~/workspace/goals/whiteout-survival-mobile-bot/GOAL.md
```

**⚠️ تنبيه عن نسخة الـ keystore:** فيه نسخة من `cinereels.keystore` + ملف كلمة السر في `~/workspace/your_files/cinereels-apk/` — **لا تُرفع أبداً على GitHub ولا تدخل في أي zip للمصدر.**

---

## 4. إجراءات البناء والنشر لكل مشروع

### 4.1 CineReels — بناء APK (Java أصلي، لا Flutter، لا Gradle)

```bash
cd ~/workspace/your_files/cinereels-apk
# 1) غيّر الإصدار أولاً في ملفين:
#    AndroidManifest.xml: android:versionCode + android:versionName
#    build.sh: VER="x.y"
# 2) زامن assets/videos.json مع النسخة الحية من GitHub (نسخة منفصلة — شوف قسم 5)
./build.sh
# المخرجات: out/CineReels-vX.Y.apk + out/CineReels-vX.Y.aab
```

**التحقق بعد كل بناء (إلزامي قبل الإرسال لآدم):**
```bash
aapt2 dump badging out/CineReels-vX.Y.apk | grep -E "package:|version"
# كل الـ Activities لسه عندها constructor (R8 ممكن يشيله — قسم 5):
unzip -o -q out/CineReels-vX.Y.apk classes.dex -d /tmp/dexcheck
dexdump /tmp/dexcheck/classes.dex | grep -A2 "HomeActivity" | grep "<init>"
# التوقيع بنفس المفتاح (نفس الـ fingerprint كل مرة):
export PATH=~/workspace/snake-colony-work/jdk17/bin:$PATH
apksigner verify --print-certs out/CineReels-vX.Y.apk
# الـ fingerprint بتاع cinereels: 28:DF:4A:3D:D7:11:E8:A3:47:8A:15:5C:6E:B3:BE:E2:81:34:29:A8:3F:A2:B6:FE:38:15:03:05:42:BD:B6:1C
```

**النشر (رفع APK جديد):**
1. ابنِ النسخة واتأكد من التحققات.
2. انسخ الـ APK + `index.html` المحدّث إلى `~/workspace/your_files/thumbnail-upload/` (مسارات المتصفح مبتحبش الـ symlinks).
3. حدّث `index.html`: غيّر رابط الـ APK (`CineReels-vX.Y.apk`) ورقم النسخة الظاهر.
4. ارفع الملفين لريبو `adam2211dmdm-ux.github.io` (root, main) من **المتصفح** (Add file → Upload files) — **Environment 2 أنجح واحد**. رسالة الكوميت: `CineReels vX.Y: <ملخص قصير>`.
5. **استنى دقايق واتأكد بـ curl قبل ما تبعت الرابط لآدم** (GitHub Pages بيتأخر دقايق بعد الكوميت — 404 مؤقت طبيعي؛ أعد الفحص بعد ~75 ثانية لو قديم):
   ```bash
   curl -sI https://adam2211dmdm-ux.github.io/CineReels-vX.Y.apk
   # لازم: HTTP 200 + content-type application/vnd.android.package-archive + الحجم الصح
   curl -s https://adam2211dmdm-ux.github.io/CineReels-vX.Y.apk -o /tmp/check.apk
   md5sum /tmp/check.apk   # لازم يطابق md5 الـ build المحلي
   curl -s https://adam2211dmdm-ux.github.io/ | grep "vX.Y"
   ```
6. ابعت لآدم الرابط المباشر + قوله **يمسح النسخة القديمة الأول** (نفس الـ package والتوقيع، فالتحديث بيركب فوقها، بس المسح أنضف لو فيه مشكلة).

**تحديث الـ manifest (`videos.json`):**
- **قبل أي push: هات آخر نسخة من GitHub (head) وادمج عليها** — آدم نفسه بينشر حلقات من متصفحه أثناء الشغل، ونسخة محلية قديمة ممكن تلغي شغله. استخدم connector `get_file_contents` لقراءة الـ head الحي.
- ملفات نصية (videos.json, .vtt, .md, .json): ادفع بـ `github push-files` (شوف `/opt/hatch/connectors/github/references/snapshot-push.md`) — اتأكد من head بالـ `list_commits` قبل الدفع مباشرة، وسجّل الـ commit SHA في ملف المزامنة (`github-videos.muse-github-snapshot-sync.json` — ضيف entry `{owner, repo, branch, source_dir, commit_sha, paths}` واحتفظ بالقديمة).
- ملفات binary (mp4, apk, webp): **من المتصفح بس** — `push-files` مبيعملش binary ولا حذف.
- **من v1.24: مفيش توقيع HMAC تاني** — الـ manifest بيتقبل لو اتحلل وعدّى فحص same-origin/allowed-hosts. ملف `videos.json.sig` الحي قديم (`779e760b…`) وده متوقع ومش مشكلة. متعيدش التوقيع إلا لو رجّعت نظام التوقيع بقرار صريح.
- **الـ push بتاع GitHub مش pre-approvable** — كل push بيطلع **approval card لآدم** لازم يدوس عليها، والكارت ممكن **يخلص وقته (timeout)** — لو حصل، أعد المحاولة وقوله.
- إضافة حلقة جديدة: ارفع الـ mp4 من المتصفح → ضيف entry في `videos.json` (الـ `duration_sec` لازم يساوي المدة الحقيقية من `ffprobe`، مش تقدير) → ثمبنيل → ترجمات (قسم الترجمة في دليل CineReels §8/§16) → ادفع → اتأكد بـ curl.

### 4.2 Snake Colony — بناء وتصدير (Godot 4.3)

- المشروع: `~/workspace/snake-colony-work/snake_colony/` — افتحه في Godot 4.3 وصدّر من `export_presets.cfg` (Android + Web).
- التوقيع: keystore في `~/workspace/snake-colony-work/keystore/snake_colony.keystore` (alias `snake_colony`)، كلمة السر في `.keystore_pass.txt` جنبه — **نفس الـ keystore مطلوب لكل تحديث مستقبلي على Google Play.**
- سيرفر Nakama محلياً: binaries في `~/workspace/snake-colony-work/nakama/` (من غير Docker). شغّل CockroachDB الأول وبعدين Nakama بـ `--matchmaker.interval_sec 1 --matchmaker.max_intervals 1` (الـ flags دي إلزامية — شوف قسم 2.1). API على `:7350`، console على `:7351`.
- النشر على Railway: ملفات `~/workspace/snake-colony-work/railway-nakama/` (Dockerfile + entrypoint.sh + railway.json) — ريبو `snake-colony-nakama`. الـ host الافتراضي الحالي `mainline.proxy.rlwy.net:58627`.
- itch.io: الـ web zip (Drive `1-do4iVKn8qqeMsdSKmgyX-ojAtA70mku`) — ارفع على Wi-Fi، علّم "played in the browser"، واضغط Restore لو ظهر خطأ `.pck`.

### 4.3 IPTV + Game Assistant — بناء Java من غير Gradle

- نفس طريقة CineReels: aapt2 + javac + (d8) + zipalign + apksigner، JDK 17 من `~/workspace/snake-colony-work/jdk17/bin` على الـ PATH.
- كل تطبيق له keystore الخاص بيه (قسم 3) — متبدلش الـ keystores بين التطبيقات.
- IPTV: قنوات جديدة بتتضاف في `channels.m3u` (اتأكد HTTP 200 + HLS قبل الإضافة)؛ الـ `channels.m3u` البعيد على Pages بيتحدّث من غير ما التطبيق يتحدث.
- **Gotcha:** `apksigner --ks-pass file:` بيقرا **سطرين** (store pass + key pass) — ملف سطر واحد بيفشل.

### 4.4 Whiteout bot (AutoX.js)

- السكربت `workspace/your_files/whiteout-mobile-bot/whiteout_bot.js` — بيشتغل على الموبايل نفسه بـ AutoX.js. التعديل = تعديل الإحداثيات/قوالب الصور في السكربت وإعادة إرساله لآدم. مفيش build.
- **تحذير دائم: يجرّب على حساب تانوي (خطر ban).**

---

## 5. دروس صعبة / Gotchas — لا تعيد الغلط

1. **R8 بيشيل الـ constructors (الدرس القاتل):** قاعدة الـ ProGuard لازم تحافظ على `<init>();` لكل Activity، مش `onCreate` بس. غير كده التطبيق بيموت فور فتحه برسالة صامتة (`Unable to instantiate activity ... has no zero argument constructor`) — حصل في v1.2 لحد v1.6 واتكشف بـ Appetize.io. اتصلح في v1.7.
2. **ممنوع Lambda:** المشروع بيتبني على android.jar مباشرة (مفيش LambdaMetafactory) — استخدم anonymous inner classes دايماً.
3. **Android 15 edge-to-edge:** targetSdk 35 بيرسم المحتوى تحت شريط الحالة — `BaseActivity` بيضيف padding حسب الـ insets (top + bottom) لكل الـ Activities.
4. **RTL بيقلب Gravity.START:** في العربي، `Gravity.START` بيروح **يمين** مش شمال. أي حاجة مثبتة على جهة فيزيائية لازم `Gravity.LEFT` المطلق (الدرس ده كلفنا v1.22 كاملة — الرقعة راحت يمين).
5. **`assets/videos.json` نسخة منفصلة:** الـ manifest المضمّن في الـ APK نسخة تانية غير `github-videos/videos.json` — **زامنها قبل كل build** وإلا الـ APK هيشحن كتالوج قديم.
6. **HMAC byte-exact (تاريخي):** الـ `fetchUrl` القديم كان بيضيف `\n` بعد كل سطر فالتوقيع كان بيفشل بصمت — ده كان سبب bug v1.13. **من v1.24 التوقيع اتلغى أصلاً** — بس لو رجّعته، القراءة لازم تكون بايتات دقيقة. ومفتاح HMAC (`cinereels-hmac.key`) **HEX-encoded** — اتأكد بـ `bytes.fromhex(...)` مش بايتات الملف الخام.
7. **Manifest cache version stamp:** `ManifestLoader.load()` بيفضّل الـ cache المخزن (`manifest_cache` في SharedPreferences) على الـ manifest المضمّن. من v1.22 الـ cache بيتختم بـ versionName التطبيق (`manifest_cache_version`) والـ cache اللي versionه مختلف بيتجاهل. لو حلقات جديدة مش ظاهرة بعد تحديث، ده أول مكان تبص عليه.
8. **GitHub push approval cards + timeouts:** كل push بيطلع approval card لآدم ولازم يدوس عليها، والكارت ممكن يخلص وقته. لو push فشل بـ timeout، أعد المحاولة وبلّغ آدم. **ومتستخدمش GitHub App API لإنشاء repos — بيرفض 403؛ الـ repos بتتعمل من المتصفح.**
9. **Pages deploy lag:** GitHub Pages بيتأخر دقايق بعد الكوميت — 404 مؤقت طبيعي. أعد الفحص بعد ~75 ثانية قبل ما تقول إن الرفع فشل.
10. **`/tmp` صغير (512 MB tmpfs):** بيتملي بسرعة — حط ملفات الاختبار تحت الـ home مش /tmp.
11. **Nakama gRPC vs HTTP:** الـ gRPC بيتبع `--console.port`، والـ HTTP gateway بيتبع `--socket.port`، والـ console بتصرّ على 7351.
12. **ReelShort H265 = شاشة سوداء:** أي رابط `-sd` (720p H265) أو master playlist على موبايل آدم بيطلع شاشة سوداء. استخدم **`-ld` 540p H264 بس**. والـ token بتاع `-ld` بيختلف كل حلقة — مينفعش تشتقه.
13. **Sansekai من الـ VM = 403 دايماً:** curl من الـ VM محجوب بـ Cloudflare — ده مش معناه إن الـ API واقع. المتصفح الحقيقي (Environment 2 أنجح) هو اللي بيشتغل.
14. **الـ `.sig` القديم مش مشكلة:** الـ `videos.json.sig` الحي stale من v1.24 — متوقع ومش مشكلة، متعيدش توقيعه.
15. **آدم بيعدّل الـ manifest من متصفحه أثناء الشغل** — قبل أي push لـ `videos.json` هات الـ head الحي وادمج عليه (قسم 4.1).
16. **raw.githubusercontent ممكن يخدم نسخة قديمة من الـ CDN** بعد push — استنى شوية وأعد الفحص قبل ما تقول إن التحديث موصلش.
17. **MEMORY.md اتغيرت من عمليات خارجية قبل كده** (سطور اتشالت/اتبدلت) — اتأكد من الحقائق من الـ disk/dex/مصادر حية لما الموضوع مهم.
18. **الثمبنيلز:** picsum placeholders ممكن متفشلش على نت بطيء (آدم شاف 2 KB/s)؛ الثمبنيلز الحقيقية (stills سينمائية) في `thumbnails/` على GitHub. وGTV-bucket sample thumbnails بترجع 403.
19. **الترجمة المضمّنة fallback:** ملفات .vtt لازم تتحدث في 3 أماكن بنفس المحتوى (`github-videos/subtitles/drama/` + `github-videos/subtitles/` + `cinereels-apk/assets/subtitles/`) — لو نسيت التالتة، المستخدم على نت بطيء هيشوف الترجمة القديمة الغلط.
20. **الـ subtitles المضمّنة بتتسرب بين المسلسلات لو مش مربوطة بـ series:** من v1.21 الـ fallback المضمّن مقيّد بـ `last-message`/`second-chance` بس.

---

## 6. قائمة DO NOT RETRY — حاجات متجربهاش تاني

| الحاجة | ليه ممنوع | البديل |
|---|---|---|
| **Real-AdMob custom Gradle build** (Snake Colony + CineReels) | **BLOCKED هنا:** Gradle مبيقدرش ينزّل من Maven Central/Plugin Portal من ورا الـ egress proxy. اتجرب واتقفل 2026-11-22 ~19:04 EET بقرار صريح: **متكملش المهمة دي، متعيدش تفويضها، متعيدش صياغتها، ومتعملهاش من طريق تاني.** الشغل حوالينها موجود (Temurin JDK 17 + SDK + Gradle 8.2 + mirror init script + local Maven repo) بس الـ build نفسه مبيكملش. | الإعلانات المحاكاة (3 ثواني) في الـ APKs الحالية؛ آدم يعمل الـ build الحقيقي بنفسه على جهازه (أو على VPS) — هو سأل إزاي يعملها بنفسه. |
| **توليد الفيديو بالـ AI** | **403 دائم — قيود دولة/منطقة على الحساب ده** (5 محاولات فاشلة 2026-11-22). العيشة في أمريكا مش بتلغي الحظر لأنه مربوط بالـ account region (مصر من إعدادات AdMob). | صور ثابتة سينمائية + تجميع بـ ffmpeg (slow zoom/pan + voiceover + ترجمة) — العرض ده لسه آدم موافقش عليه ("كمّل بالصور" لسه معلّق). |
| **Appetize.io emulator** | **الـ free tier خلص لحد 1 ديسمبر 2026.** مفيش تحقق emulator لحد التاريخ ده. | موبايل آدم هو جهاز الاختبار. |
| **Sansekai API IP blacklist — تخطي بـ proxies** | الـ IP محظور (Cloudflare 502 → "bandwidth limit" → "IP blacklisted"). **ممنوع تتخطاه بـ proxies.** | استنى لما الحظر يترفع، أو استخدم IP مش محظور (متصفح/موبايل آدم). |
| **`dramabox.sansekai.my.id`** | واقع (Cloudflare 522) من 2026-11-24. | الـ harvest من `api.sansekai.my.id` هو الطريق الشغال. |
| **إعادة إنشاء keystore** | فقدان/استبدال الـ keystore = مستحيل تحديث التطبيق. | استخدم نفس الـ keystore دايماً (قسم 3). |
| **إرجاع الـ waves في Snake Colony** | اتشالت بقرار آدم (v3.0 pivot). | 5v5 أونلاين + بوتات. |
| **إرجاع الترجمة المخترعة / الفيديوهات التجريبية** | اتشالت لسبب (الترجمة مكانتش مطابقة للصوت الحقيقي؛ الفيديوهات التجريبية اتمسحت بقرار آدم). | ترجمة مفرّغة من الصوت الحقيقي بس. |

---

## 7. أسئلة وقرارات معلّقة عند آدم

1. **v1.25/v1.26 على موبايله:** الـ blur مغطي حرف الـ R دلوقتي؟ وv1.26 شغالة والمسلسل الجديد ظاهر؟ (اتطلب سكرين شوت 2026-11-24 07:26 و~08:30؛ رد "تمام" من غير إجابة.)
2. **الـ 14 حلقة الميتة** (18، 22، 23، 24، 26، 27، 29، 34، 38، 41، 44، 45، 46، 51) — إعادة جلب لما الـ Sansekai blacklist يترفع.
3. **اختيار مسلسلات narto جديدة** من الكتالوج (الـ 4 featured اتقترحت 2026-11-24 00:42 EET) + **إرسال مفتاح ReelShort gateway عبر رابط الـ secure capture** (اتبعت 00:42 EET — لسه مفيش رد). أولوية أقل بعد الـ pivot لـ Sansekai، بس لسه مفتوحة.
4. **اختيار شبكة إعلانات داخل التطبيق** (AppLovin MAX / Unity Ads / Meta) — أي SDK محتاج Gradle (متعطّل). آدم لسه مختارش.
5. **Play listing لسه ناقص منه:** privacy-policy URL، أيقونة 512px، feature graphic، استبيان content rating، نموذج Data Safety.
6. **English harvest + الترجمة** ("هات انجليزي والترجمه بتعته" — 2026-11-24 08:35 EET) — متأجلة بعد شغل التشفير؛ لسه متجابش حاجة.
7. **نتيجته لاختبار v1.18** (رفض الدخول الفاضي + صفحة التسجيل) — متبلغش بيها.
8. **هل الـ web demo (artifact `cinereels`) يقرا/يكتب GitHub `subscribers.json`؟** — سؤال مفتوح (الـ demo حالياً بيخزن الاشتراكات في قاعدة بياناته الخاصة مش GitHub).
9. **هل نرجع قصة المسلسل للـ outline القديم (العم/البيت/الفلوس)؟** — سؤال مفتوح (النسخة الحالية: ليلى + سارة).
10. **عرض "كمّل بالصور":** تجميع فيديوهات من الـ stills السينمائية + narration بـ ffmpeg — لسه موافقش.
11. **سطور الترجمة غير المؤكدة** (الحلقات 1/4/8/9 — مثلاً ep1 cue 3 "Yeah, I have been…" مقطوعة؛ ep8 cue 1 "What do you mean, two lives?"؛ ep9 cue 6 + اسم شارع "Alman Sua Street"؛ ep4 cue 3) — آدم لسه مأكدهاش.
12. **هل ملف `romantic-drama-30s.mp4` هو فعلاً الحلقة 1 من "A Second Chance"؟** — افتراض لسه متأكدش.
13. **إعادة فحص `dramabox.sansekai.my.id`** بعدين (واقع 522 من 2026-11-24).
14. **روابط حلقات FreeReels (56/56) وMyDrama (90 حلقة) وPineDrama (26–76) وMelolo/FlickReels** — موصلتش في الـ summaries، محتاجة إعادة جلب من IP مش محظور.
15. **itch.io play test** — إعادة الرفع على Wi-Fi + Restore لسه متأكدتش.

---

## 8. الأتمتة الشغالة (crons)

اتعملوا 2026-11-23، والاتنين اتأكد إنهم شغالين 2026-11-24 ~07:12 EET. الـ owner: `goal:cinereels-short-video-app`.

### 8.1 `cinereels-support-triage` — كل 15 دقيقة
- بيفحص `adam2211dmdm@gmail.com` عن إيميلات `[CineReels Support]`، بيجهز ردود بلغة المستخدم، وبيسجل الـ bugs في `~/workspace/your_files/cinereels/support/bugs.md`.
- **الإرسال محتاج دوسة آدم.**

### 8.2 `cinereels-auto-translate` — كل 30 دقيقة
- الـ watcher: `~/workspace/your_files/cinereels/tools/auto_translate.py` (venv في `~/workspace/whisper-venv/`، tesseract 5.3.4 ara+eng في `/usr/bin/tesseract`).
- بيلاقي الحلقات المنشورة اللي عندها فيديو بس ملهاش روابط ترجمة ولا `burned_subs`، بيفرّغ الصوت (faster-whisper tiny)، بيكتشف الترجمة المحروقة (detector متأكد منه: band السفلي 22%، PIL luminance ≥190 + tesseract TSV؛ الحلقة burned_in = ≥2 frame hits؛ الفريمات عند midpoints أول 3 speech segments + 3 كسور ثابتة؛ المدة الحقيقية من ffprobe)، بيترجم EN↔AR، بيكتب .vtt، بيحدّث الـ manifest، ويدفع.
- **الـ GitHub push مش pre-approvable — كل push بيطلع approval card لآدم.**
- (خطوة إعادة التوقيع بقت moot من v1.24 لأن التوقيع اتلغى.)

---

## 9. سياسة الأسرار

**القاعدة: لا قيمة سرّية في أي ملف عام أو أي شات — أبداً.**

- **ممنوع كتابته في أي مكان (ملفات، شات، GitHub، zips):** أي كلمة سر، أي API key، أي كلمة سر keystore، كلمة سر الأدمن، أكواد التحقق/الـ OTP، مفاتيح HMAC.
- **المسموح كتابته: مكان السر بس** (مثال: "كلمة سر الـ keystore في `.cinereels_pass.txt` جنب الـ keystore"، "مفتاح HMAC في `~/workspace/snake-colony-work/cinereels-hmac.key`").
- **دخول الأدمن في CineReels:** سري تماماً بين آدم وMuse. اكتب بس **"دخول أدمن موجود؛ اسأل آدم"** — لا اسم مستخدم ولا كلمة سر، ولا تلميح لوجوده في التطبيق.
- **مفاتيح narto gateway (dramabox/reelshort):** آدم بعتها في الشات باختياره، واستخدمت transient في curl بس، و**قيمها مش مسجلة في أي مكان**. متطلبهاش تاني منه؛ لو مفتاح اتحتاج، اعرض رابط الـ secure capture الأول (connector `custom.narto-drama`).
- **الـ keystores وكلمات سرها:** مكانها في قسم 3. **متترفعش أبداً على GitHub ولا تدخل في أي zip للمصدر.** نسخة احتياطية من cinereels keystore موجودة في `~/workspace/your_files/cinereels-apk/` — نفس القاعدة.
- **ملفات كلمات السر chmod 600.** متبعتش محتواها في أي تقرير أو شات.
- **الـ OTP/أكواد الجهاز:** كود جهاز GitHub بيتبعت على الجيميل كل مرة — يتجاب من الإيميل وقت الحاجة بس، وميتسجلش.
- **الـ WhatsApp/Vodafone رقم 201080482372** رقم تواصل تجاري عام (موجود أصلاً في `subscribers.json` على GitHub) — مش سرّي.
- **أرقام الـ Drive file IDs والـ hosts العامة** (زي `mainline.proxy.rlwy.net:58627`) مش أسرار.

---

## 10. أوامر سريعة Cheat Sheet

```bash
# بناء CineReels
cd ~/workspace/your_files/cinereels-apk && ./build.sh
# حالة APK الحي
curl -sI https://adam2211dmdm-ux.github.io/CineReels-vX.Y.apk | grep -i -e HTTP -e content-length -e content-type
# حالة الـ manifest الحي
curl -s https://raw.githubusercontent.com/adam2211dmdm-ux/cinereels-videos/main/videos.json | python3 -c "import json,sys; d=json.load(sys.stdin); print(len(d.get('videos',[])), 'videos')"
# حالة الاشتراكات
curl -s https://raw.githubusercontent.com/adam2211dmdm-ux/cinereels-videos/main/subscribers.json | python3 -m json.tool | head -30
# مدة/أبعاد فيديو
ffprobe -v error -show_entries stream=codec_type,width,height -show_entries format=duration -of default=noprint_wrappers=1 file.mp4
# صورة من فيديو
ffmpeg -y -v error -i file.mp4 -ss 00:00:03 -frames:v 1 frame.jpg
# تفريغ صوت حلقة (whisper)
OMP_NUM_THREADS=1 ~/workspace/whisper-venv/bin/python ~/workspace/your_files/cinereels/transcripts/run_transcribe.py
# توقيع manifest (تاريخي — متقريش من v1.24)
python3 tools/sign_manifest.py ~/workspace/your_files/cinereels/github-videos/videos.json
```

---

## ملاحظات أخيرة للي هيكمل

- **ابدأ أي شغل بقراءة الملف ده + `~/workspace/your_files/cinereels/CineReels-HANDOVER-GUIDE.md` + `~/MEMORY.md` + ملاحظات اليوم في `~/memory/2026-11-24.md`.** التفاصيل الكاملة للـ harvest في `sansekai-harvest-batch1.md` و`sansekai-harvest-batch2.md`.
- **آدم بيشتغل على موبايله وبيبعت سكرين شوتس** — اقرا الصورة كويس قبل ما ترد؛ اللي باين فيها هو التشخيص.
- **قبل أي push لـ `videos.json`: هات الـ head الحي وادمج عليه** — آدم بينشر من متصفحه أثناء الشغل.
- **متدّعيش حاجة شغالة من غير تحقق** (curl + MD5 + سكرين شوت من موبايل آدم). الصدق مع آدم هو اللي بنى الثقة دي.
- **حدّث هذا الملف** كل ما حالة مشروع تتغير (نسخة جديدة، عيب جديد، قرار جديد من آدم) — هو دليل حي، مش أرشيف.

*آخر تحديث: 2026-11-24 ~10:55 EET — v1.26 DELIVERED والرابط اتبعت لآدم 10:45 EET (HTTP 200، 1,300,586 بايت، MD5 `193bae916eb49fba07274300ff3d9ba3`، manifest commit `3ed4f7b`، APK commit `e41ef07`)، manifest حي 198 فيديو / 5 مسلسلات، عيب 38/52 معروف ومبلّغ بيه.*
