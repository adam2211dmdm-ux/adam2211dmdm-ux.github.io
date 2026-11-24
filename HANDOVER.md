# دليل التسليم الكامل — CineReels Master Handover Guide
# (CineReels فقط — بطلب آدم 2026-11-24)

> **آخر تحديث:** 2026-11-24 ~11:00 EET — كتبه Muse (مساعد آدم).
> **الغرض:** أي شخص أو AI يقرأ هذا الملف يقدر يكمل شغل **CineReels** من غير ما يسأل آدم أسئلة بديهية.
> **الأساس:** هذا الدليل مبني على `~/workspace/your_files/cinereels/CineReels-HANDOVER-GUIDE.md` (دليل v1.19) ومحدَّث بكل اللي حصل بعده لحد v1.26 + حصاد Sansekai + قصة التشفير.
> **القاعدة الذهبية:** لا تكتب أي كلمة سر أو مفتاح API أو كود تحقق في هذا الملف أبداً — أماكن الأسرار مكتوبة، قيمها لأ. (شوف §17 — سياسة الأسرار.)
> **لغة الملف:** عربي (مصري) + مصطلحات تقنية إنجليزية زي ما آدم متعود.

---

## آدم — قواعد التعامل (اقرأها الأول)

- **آدم (Adam):** مصري، عايش في أمريكا. رسايله بتوصل بتوقيت **Africa/Cairo (EET)**. بيكلم عربي مصري مباشر وقصير — **كل الردود عليه لازم تكون بالعربي المصري، قصيرة ودافئة ومباشرة**، مش شرح تقني طويل.
- **موبايل بس — OPPO Reno15 F 5G.** مفيش كمبيوتر، مفيش كارت بنكي، ومفيش فلوس دلوقتي. أي شغل لازم يشتغل على موبايله.
- **بيحكم على الشغل من اللي يشوفه على موبايله** — مش من الشرح. أي إصلاح لازم يتأكد بصورة/سكرين شوت قبل ما يتقال إنه شغال.
- **"ابشرني"** = ابدأ بالخبر الحلو أولاً. **"ايه كل دا"** = اختصر في سطرين.
- **متوعدش أبداً بوقت تسليم أو ملف قبل ما يوصل فعلاً.** لو حاجة لسه متبعتتش، قول "لسه" بصراحة.
- **اتأكد قبل ما تدّعي:** أي نسخة APK لازم تتأكد منها بـ curl (HTTP 200 + الحجم + MD5) قبل ما تبعت الرابط لآدم. وأي إصلاح بصري لازم يتأكد من سكرين شوت على موبايله هو.
- **قوله الحقيقة زي ما هي:** لو حاجة شغالة جزئياً (مثلاً 38 حلقة من 52)، قوله الرقم الحقيقي. متجمّلش.
- **قراراته نهائية:** لما يقول "سيبك من كذا" أو "متعملش كذا تاني"، ده قرار — متناقشوش ولا ترجع الحاجة اللي شالها.
- **لما يقول إن حاجة بتاعته، صدّقه واشتغل** — متعيدش النقاش (مثال: أكد إن فيديوهات "الرسالة الأخيرة" بتاعته).
- **متعملش حسابات ولا توافق على شروط ولا تختار دولة/عملة/ضرايب/دفع بالنيابة عنه** من غير إذنه الصريح وبياناته هو. مصاريف بس المجانية أو اللي وافق عليها صراحة.
- **حقوق النشر:** محتوى يملك حقوقه أو مرخّص فقط — ممنوع كليبات أفلام/مسلسلات أو أي محتوى مسروق.
- **الـ keystore:** لو ضاع = التطبيق مينفعش يتحدث أبداً. حافظ عليه وخلّيه ظاهر في كل دليل.

---

## فهرس المحتويات

1. [التطبيق بيعمل إيه](#1-التطبيق-بيعمل-إيه)
2. [الحالة الحالية — v1.26 والمحتوى](#2-الحالة-الحالية--v126-والمحتوى)
3. [الحسابات والريبو وأماكن الملفات](#3-الحسابات-والريبو-وأماكن-الملفات)
4. [البناء (Build)](#4-البناء-build)
5. [النشر (Release) — رفع APK جديد](#5-النشر-release--رفع-apk-جديد)
6. [الـ manifest — `videos.json` (قلب التطبيق)](#6-الـ-manifest--videosjson-قلب-التطبيق)
7. [الترجمة (Subtitles) + الترجمة التلقائية](#7-الترجمة-subtitles--الترجمة-التلقائية)
8. [الاشتراكات (Manual — WhatsApp + Vodafone Cash)](#8-الاشتراكات-manual--whatsapp--vodafone-cash)
9. [Monetag (إعلانات صفحة التحميل)](#9-monetag-إعلانات-صفحة-التحميل)
10. [استيراد مسلسل من رابط + narto-drama.com](#10-استيراد-مسلسل-من-رابط--narto-dramacom)
11. [حصاد Sansekai API — مصدر المسلسلات الشغالة](#11-حصاد-sansekai-api--مصدر-المسلسلات-الشغالة)
12. [التشفير والتشغيل — القصة الكاملة لكل مزوّد](#12-التشفير-والتشغيل--القصة-الكاملة-لكل-مزوّد)
13. [الدعم — لما آدم يبلّغ عن مشكلة](#13-الدعم--لما-آدم-يبلّغ-عن-مشكلة)
14. [دروس صعبة / Gotchas — لا تعيد الغلط](#14-دروس-صعبة--gotchas--لا-تعيد-الغلط)
15. [قائمة DO NOT RETRY — حاجات متجربهاش تاني](#15-قائمة-do-not-retry--حاجات-متجربهاش-تاني)
16. [أسئلة وقرارات معلّقة عند آدم](#16-أسئلة-وقرارات-معلّقة-عند-آدم)
17. [سياسة الأسرار](#17-سياسة-الأسرار)
18. [دليل صناعة الفيديو — للـ AI اللي هيعمل الحلقات](#18-دليل-صناعة-الفيديو--للـ-ai-اللي-هيعمل-الحلقات)
19. [أوامر سريعة (Cheat sheet)](#19-أوامر-سريعة-cheat-sheet)

---

## 1. التطبيق بيعمل إيه

**CineReels** — تطبيق أندرويد لمشاهدة فيديوهات قصيرة عمودية (ستايل DramaBox / ReelShort):
- فيد عمودي full-screen، سوايب، تشغيل تلقائي، كتم صوت، لايك/مفضلة/مشاركة/تعليقات.
- مسلسلات بحلقات متتابعة (الحلقة تخلص → عدّ تنازلي 3 ثواني → الحلقة اللي بعدها تلقائي).
- ترجمة على كل فيديو (عربي/إنجليزي/إيقاف، زر CC، حجم قابل للتعديل).
- تصنيفات + بحث + مفضلة + سجل مشاهدة.
- حسابات (تسجيل/دخول) + ملف شخصي عربي/إنجليزي (RTL/LTR كامل). صفحة الدخول هي أول شاشة (دخول / تسجيل / ضيف) مع intro سينمائي.
- اشتراك مدفوع: **25 حلقة مجانية، بعدها اشتراك** (نموذج DramaBox) — يدوي عبر واتساب + فودافون كاش (§8).
- لوحة أدمن (رفع/حذف فيديوهات، ترجمات، تصنيفات، الموافقة على الاشتراكات، استيراد مسلسلات، جلب مسلسلات عشوائية من المزوّدين).
- تصميم داكن سينمائي (near-black #0A0A0F/#121218، ذهبي كلمسة خفيفة بس — مفيش بلوكات حمرا كبيرة؛ آدم رفض التصميم "الابتدائي" وطلب احترافي لأقصى شيء).
- **التقنية:** Java أصلي (Native) — **لا Flutter، لا Gradle**. البناء بـ aapt2 + javac + R8 + zipalign + apksigner + bundletool. يعمل أوفلاين (الـ manifest المضمّن fallback).
- فيه نسخة Flutter source قديمة (36 ملف، ~4,067 سطر في `~/workspace/your_files/cinereels/flutter/`) — **متروكة، مش هي اللي بتتبني**. الـ APK الأصلي هو الشغال.
- فيه web demo (artifact `cinereels`) — نسخة ويب بنفس المزايا تقريباً، بس اشتراكاتها في قاعدة بياناتها الخاصة مش GitHub `subscribers.json` (فرق صريح متبلغ بيه آدم).

---

## 2. الحالة الحالية — v1.26 والمحتوى

### v1.26 (versionCode 27) — DELIVERED والرابط اتبعت لآدم 2026-11-24 10:45 EET
- **تم التحقق الحي 2026-11-24 ~10:50 EET:** `https://adam2211dmdm-ux.github.io/CineReels-v1.26.apk` = **HTTP 200**، الحجم **1,300,586 بايت**، MD5 = **`193bae916eb49fba07274300ff3d9ba3`** (مطابق للـ build)، و`index.html` بتقول v1.26. الـ manifest الحي فيه **198 فيديو / 5 مسلسلات** (commit `3ed4f7b`)؛ الـ APK اترفع من المتصفح (commit `e41ef07`). آدم اتقاله يمسح القديم الأول.
- **الجديد في v1.26:**
  1. **Admin provider picker — 7 مزودين شغالين + 'random from all'** (المستبعدين: ShortMax وMelolo وGoodShort وDramaNova — شوف §12).
  2. **زر "جلب مسلسل جديد" — عشوائي بدون تكرار:** كل ضغطة بتضيف مسلسل واحد عشوائي مش موجود أصلاً في الكتالوج (dedupe بـ bookId + العنوان normalized، ومجموعة persistent من الـ bookIds المستوردة، لحد ~10 محاولات لو الاختيار مكرر). معاينة قبل الاستيراد (العنوان + البوستر + عدد الحلقات + الوصف) وآدم بيأكد الاستيراد.
  3. **Playback حسب المزوّد** (DramaBox: بناء رابط الـ proxy أوفلاين؛ NetShort: playVoucher؛ ReelShort: ld؛ FreeReels/MyDrama/PineDrama/FlickReels: جلب طازج وقت التشغيل — التفاصيل في §12).
- **المسلسل الجديد في v1.26:** "انتقام إله الأمواج" (ReelShort، 52 حلقة، روابط `-ld` 540p H264).
- **⚠️ عيب معروف وصريح — متقدمش v1.26 على إنه 52 حلقة كاملة:** بس **38 من 52** رابط شغالين (HTTP 200). **14 حلقة ميتة (HTTP 404):** 18، 22، 23، 24، 26، 27، 29، 34، 38، 41، 44، 45، 46، 51. اتأكد مرتين بـ curl (mobile UA). الـ `-sd` fallback ميت برضه + H265 = شاشة سوداء على موبايل آدم. الـ 14 دول محتاجين إعادة جلب `videoList` من Sansekai API لما الـ IP blacklist يترفع (§11/§12). **آدم اختار بنفسه (2026-11-24 10:39 EET): ابعت v1.26 دلوقتي مع التنبيه الصريح 38/52.**
- **لسه متأكدش على موبايل آدم:** لا v1.26 ولا إصلاح الـ blur بتاع v1.25 اتأكدوا منه على موبايله لسه (الجلب من الموبايل، والتشغيل حسب المزوّد، ومكان الـ blur، والـ 14 حلقة الميتة — كلها معلّقة على اختبار موبايله).

### إصلاح الـ blur (v1.25 — versionCode 26)
رقعة التمويه فوق شعار ReelShort "R" أعلى الشمال — الـ margins بقت `setMargins(dp(28), dp(75), 0, 0)` في `SeriesActivity.java` و`FeedActivity.java` (الحجم 64dp، gravity `TOP | LEFT`). اتبعت 2026-11-24 07:26 EET (MD5 `fbec674d9d112ee7d3f0731cdd94413e`). **تأكيد آدم من موبايله لسه معلّق** (اتطلب سكرين شوت مرتين؛ رد "تمام" من غير إجابة).

### المحتوى الحالي (manifest حي — اتفحص 2026-11-24 ~11:00 EET — 198 فيديو / 5 مسلسلات)
| المسلسل | الحلقات | المنشور | التفاصيل |
|---|---|---|---|
| **The Last Message / الرسالة الأخيرة** | 25 | 1–15 | مقاطع آدم — 60 ثانية، صوت إنجليزي، ترجمة محروقة في الصورة (`burned_subs: true`)، الترجمة الافتراضية عربي. 16–25 `coming_soon`. الحلقات 14 و15 نشرهم آدم بنفسه على GitHub. |
| **A Second Chance / فرصة ثانية** | 3 | 1 | رومانسي؛ الحلقة 1 منشورة (60 ثانية، صوت إنجليزي، burned-in). 2–3 `coming_soon`. |
| **narto-runaway-mother** — "الأم العازبة الهاربة وزوجها الملياردير" | 56 | 56 | ReelShort، روابط مباشرة 540p H264 (`-ld`)، صوت عربي مدبلج، ترجمة عربية محروقة. **شغالة ومؤكدة على موبايل آدم من v1.21.** |
| **narto-my-revenge** — "انتقامي من زوجي وصديقتي المفضل" | 62 | 62 (ويب) | حلقات **ويب** (`web_page: true`) — بتتفتح في WebView بمشغّل موقع narto (فيه شاشة إعلانات قبل التشغيل — مش الاختيار المقبول عند آدم، شوف §10). مزوّدها مجهول. |
| **rs-wave-god-revenge** — "انتقام إله الأمواج" | 52 | 52 (38 شغالة) | ReelShort، روابط `-ld` 540p H264، صوت عربي. **14 حلقة ميتة (404)** — شوف العيب فوق. |
- كل المسلسلات `free_episodes: 25` — أول 25 حلقة مجاناً، بعدها اشتراك.
- الفيديوهات التجريبية (Blender open movies) اتمسحت بقرار آدم 2026-11-23 — مفيش أي فيديو تجريبي في الكتالوج.
- السيناريو الكامل لـ "الرسالة الأخيرة" في `cinereels/drama-series/SCRIPT_AR_EN.md` (ليلى + سارة + عمر + خالد؛ النسخة دي لغت الـ outline القديم بتاع العم/البيت/الفلوس).
- **ملحوظة عن المدد:** `duration_sec` في الـ manifest هو اللي التطبيق بيعرضه، بس **الحقيقة من `ffprobe`** — فيه حالات المدة في الـ manifest غلط (مثال: ملف sc-ep1 فعلياً 10 ثواني رغم إن اسمه 30s). اتأكد بـ `ffprobe` قبل ما تعتمد مدة.

### سجل الإصدارات (مختصر — التفاصيل في دليل v1.19 §12)
| نسخة | التاريخ | أهم ما فيها |
|---|---|---|
| v1–v1.1 | 2026-11-22 | أول APK + تصميم DramaBox |
| v1.2 | 2026-11-22 | R8 + حماية (Guard) + توقيع الـ manifest |
| v1.3 | 2026-11-23 | الاشتراك اليدوي + فيسبوك |
| v1.4 | 2026-11-23 | GitHub مصدر حقيقة الاشتراكات + ثمبنيلز + سلايدر + دخول أدمن |
| v1.5 | 2026-11-23 | كراش عند الفتح (سبب مجهول وقتها) |
| v1.6 | 2026-11-23 | نسخة تشخيص (نفس الكراش — **متتبعتش لآدم**) |
| v1.7 | 2026-11-23 | **إصلاح الكراش** (R8 كان شايل الـ constructors) + اتأكد على موبايل آدم |
| v1.8 | 2026-11-23 | إصلاح تداخل شريط الحالة + إزالة شاشة التشخيص |
| v1.9 | 2026-11-23 | بوستر تحميل دهبي + الفيديو بيملا الشاشة + مدة حقيقية + ترجمات مفرغة من الصوت الحقيقي؛ وبعدها مسح الـ 8 فيديوهات التجريبية (36←28 فيديو) |
| v1.10–v1.12 | 2026-11-23 | إصلاح خروج التصنيفات + full-frame + إصلاحات QA |
| v1.13 | 2026-11-23 | إصلاح bug الـ manifest (قراءة بايتات دقيقة) |
| v1.14 | 2026-11-23 | قبول الـ manifest بالتوقيع أو فحص same-origin |
| v1.15 | 2026-11-23 | `burned_subs` + tap-to-play/pause |
| v1.16 | 2026-11-23 | صفحة دعم بالإيميل |
| v1.17 | 2026-11-23 | صفحة الدخول أول شاشة + intro سينمائي؛ دخول الأدمن مخفي تماماً |
| v1.18 | 2026-11-23 | صفحة تسجيل منفصلة + إصلاح الدخول الفاضي — **نتيجتها عند آدم مش معروفة** |
| v1.19 | 2026-11-23 | استيراد مسلسل من رابط + حلقات ويب narto |
| v1.20 | 2026-11-23 | روابط narto المباشرة 720p H265 — **مكسورة (شاشة سوداء على موبايل آدم)** |
| v1.21 | 2026-11-24 | إصلاحها بـ H264 540p + `burned_subs` + تقييد fallback الترجمة — **آدم أكد إن الشاشة السوداء اتصلحت** |
| v1.22 | 2026-11-24 | رقعة تمويه فوق شعار R (غلط: جت يمين بسبب RTL) + ختم version للـ cache |
| v1.23 | 2026-11-24 | إصلاح الـ gravity لـ LEFT المطلق |
| **v1.24** | 2026-11-24 | **التوقيع HMAC اتلغى تماماً** — الـ manifest بيتقبل لو اتحلل وعدّى فحص same-origin/allowed-hosts (مفيش `.sig` تاني) |
| v1.25 | 2026-11-24 | تصحيح مكان رقعة التمويه (28dp، 75dp) |
| **v1.26** | **2026-11-24** | **provider picker + جلب عشوائي بدون تكرار + playback حسب المزوّد + مسلسل "انتقام إله الأمواج" (38/52 شغالة)** |

---

## 3. الحسابات والريبو وأماكن الملفات

### الحسابات
| الخدمة | الحساب | ملاحظات |
|---|---|---|
| GitHub | `adam2211dmdm-ux` | الإيميل `adam2211dmdm@gmail.com` (جديد — فيه رسايل إعداد بس). GitHub App API **مش** بيعمل repos (403 "Resource not accessible by integration") — الـ repos اتعملت من المتصفح. تسجيل الدخول من المتصفح بيحتاج كود جهاز بيتبعت على الجيميل كل مرة. الـ OAuth app "Instinct" (repo scope) **بتاع آدم هو** (أكّد بنفسه 2026-11-24) — **متبلغش عنه إنه مشبوه تاني.** |
| Gmail (للاشتراكات) | `adam2211dmdm@gmail.com` | هوية الاشتراك — المستخدم بيربط الجيميل بتاعه في التطبيق. |
| Monetag | موقع `adam2211dmdm-ux.github.io` | Verified. شوف §9. |
| Google Drive | حساب آدم المتصل | فيه CineReels v1.4 APK (file id `1RWiyuAIF28W5FKPA8YtW8H6SNdH6xR_i`) — رابط التحميل المباشر القديم. |

### الريبو (GitHub — `adam2211dmdm-ux`)
| الريبو | إيه فيه | الرابط |
|---|---|---|
| `cinereels-videos` | كتالوج CineReels (`videos.json` + `videos.json.sig` — الـ `.sig` قديم ومتقريش من v1.24 — + `subscribers.json` + فيديوهات + ثمبنيلز + ترجمات) + صفحة التحميل البديلة `docs/index.html` | `https://github.com/adam2211dmdm-ux/cinereels-videos` |
| `adam2211dmdm-ux.github.io` | موقع صفحة التحميل (user Pages site، main root): `index.html` + ملفات APK + `HANDOVER.md` (هذا الملف) | `https://github.com/adam2211dmdm-ux/adam2211dmdm-ux.github.io` |

**الـ manifest اللي التطبيق بيجيبه:** `https://raw.githubusercontent.com/adam2211dmdm-ux/cinereels-videos/main/videos.json`
**صفحة التحميل الحية:** `https://adam2211dmdm-ux.github.io/`
**رابط APK المباشر (النمط):** `https://adam2211dmdm-ux.github.io/CineReels-vX.Y.apk`

### أماكن الملفات المحلية (على جهاز الـ agent)
```
~/workspace/your_files/cinereels-apk/     ← كود التطبيق (الأصل؛ symlink لـ goals/cinereels-short-video-app/files/cinereels-apk/)
  src/com/cinereels/app/*.java            ← كل الأكواد (FeedActivity, SeriesActivity, HomeActivity, ...)
  res/values/strings.xml                  ← النصوص الإنجليزية
  res/values-ar/strings.xml               ← النصوص العربية
  AndroidManifest.xml                     ← versionCode/versionName هنا
  build.sh                                ← سكربت البناء (اقرأ §4)
  proguard-rules.pro                      ← قواعد R8 (اقرأ الدرس القاتل في §14)
  assets/videos.json                      ← نسخة الـ manifest المضمّنة (fallback) — نسخة منفصلة، زامنها قبل كل build
  assets/subtitles/*.vtt                  ← الترجمات المضمّنة (fallback)
  tools/sign_manifest.py                  ← توقيع الـ manifest (تاريخي — متقريش من v1.24)
  out/CineReels-vX.Y.apk / .aab           ← مخرجات البناء
  README_AR.md                            ← دليل عربي قديم

~/workspace/your_files/cinereels/         ← المحتوى والسيناريو والحصاد
  github-videos/                          ← نسخة محلية من ريبو cinereels-videos
    videos.json / videos.json.sig         ← الـ manifest + توقيعه (القديم)
    subtitles/drama/episode*_ar|en.vtt   ← الترجمات (المصدر الحقيقي)
    subtitles/episode*_ar|en.vtt         ← نسخ مكررة (نفس المحتوى، تُرفع معها)
    subscribers.json                      ← الاشتراكات (المصدر: GitHub)
  github-videos.muse-github-snapshot-sync.json  ← سجل مزامنة الـ push لريبو cinereels-videos
  pages-site.muse-github-snapshot-sync.json     ← سجل مزامنة ريبو Pages
  CineReels-HANDOVER-GUIDE.md             ← دليل v1.19 التفصيلي (الأساس اللي اتبنى عليه هذا الملف)
  drama-series/SCRIPT_AR_EN.md            ← سيناريو "الرسالة الأخيرة" (389 سطر)
  transcripts/                            ← تفريغ صوت الحلقات (whisper) + السكربت
  sansekai-harvest-batch1.md / sansekai-harvest-batch2.md  ← حصاد Sansekai (§11/§12)
  narto-site-catalog.md                   ← 77 مسلسل من narto-drama.com (§10)
  narto-runaway-mother-streams.json / narto-runaway-mother-detail.json
  narto-gateway-notes.md
  tools/auto_translate.py                 ← watcher الترجمة التلقائية (§7)
  tools/add_narto_series.py
  support/bugs.md                         ← سجل bugs من ترياج الدعم (§13)

~/workspace/snake-colony-work/            ← (مجلد أدوات مشترك — فيه حاجات CineReels بس اللي تحت)
  keystore/cinereels.keystore             ← مفتاح التوقيع (alias cinereels) — لا يُعاد إنشاؤه أبداً
  keystore/.cinereels_pass.txt            ← كلمة سر الـ keystore (chmod 600)
  cinereels-hmac.key                      ← مفتاح توقيع الـ manifest (HEX-encoded — شوف §14) — chmod 600
  android-sdk/                            ← SDK (build-tools 34.0.0 + platforms/android-35)
  jdk17/                                  ← Temurin JDK 17
  bundletool-all-1.17.2.jar

~/workspace/whisper-venv/                 ← venv فيه faster-whisper (لتفريغ صوت الفيديوهات)
~/workspace/your_files/thumbnail-upload/  ← منطقة تجهيز قبل الرفع بالمتصفح (APK + index.html)
~/workspace/your_files/handover/HANDOVER.md   ← هذا الملف (نسخته المحلية)
~/workspace/goals/cinereels-short-video-app/GOAL.md
```

**⚠️ تنبيه عن نسخة الـ keystore:** فيه نسخة من `cinereels.keystore` + ملف كلمة السر في `~/workspace/your_files/cinereels-apk/` — **لا تُرفع أبداً على GitHub ولا تدخل في أي zip للمصدر.**

**معلومات التوقيع (ثابتة):**
- Package: `com.cinereels.app` — Keystore: `cinereels.keystore` (alias `cinereels`)
- SHA-256 fingerprint: `28:DF:4A:3D:D7:11:E8:A3:47:8A:15:5C:6E:B3:BE:E2:81:34:29:A8:3F:A2:B6:FE:38:15:03:05:42:BD:B6:1C`
- صالح لحد 2054. **فقدان الـ keystore = مستحيل تحديث التطبيق على أي جهاز تاني.**

---

## 4. البناء (Build)

```bash
cd ~/workspace/your_files/cinereels-apk
# 1) غيّر الإصدار أولاً في ملفين:
#    AndroidManifest.xml: android:versionCode + android:versionName
#    build.sh: VER="x.y"
# 2) زامن assets/videos.json مع النسخة الحية من GitHub (نسخة منفصلة — شوف §14)
./build.sh
# المخرجات: out/CineReels-vX.Y.apk + out/CineReels-vX.Y.aab
```

**التحقق بعد كل بناء (إلزامي قبل الإرسال):**
```bash
# أ) الـ badging: versionCode/versionName الصح
aapt2 dump badging out/CineReels-vX.Y.apk | grep -E "package:|version"
# ب) كل الـ Activities لسه عندها constructor (R8 ممكن يشيله — شوف الدرس تحت)
unzip -o -q out/CineReels-vX.Y.apk classes.dex -d /tmp/dexcheck
dexdump /tmp/dexcheck/classes.dex | grep -A2 "HomeActivity" | grep "<init>"
# ج) مفيش بقايا أدوات تشخيص (مثلاً: strings "سجل التشغيل" لازم = 0)
unzip -p out/CineReels-vX.Y.apk classes.dex | strings | grep -c "سجل التشغيل"
# د) التوقيع بنفس المفتاح (نفس الـ fingerprint كل مرة)
export PATH=~/workspace/snake-colony-work/jdk17/bin:$PATH
apksigner verify --print-certs out/CineReels-vX.Y.apk
```

**دروس البناء الصعبة (لا تعيد الغلط):**
1. **R8 بيشيل الـ constructors:** قاعدة الـ ProGuard لازم تحافظ على `<init>();` لكل Activity، مش `onCreate` بس. غير كده التطبيق بيموت فور فتحه برسالة صامتة (`Unable to instantiate activity ... has no zero argument constructor`) — حصل في v1.2 لحد v1.6 واتكشف بـ Appetize.io. اتصلح في v1.7.
2. **ممنوع Lambda:** المشروع بيتبني على android.jar مباشرة (مفيش LambdaMetafactory) — استخدم anonymous inner classes دايماً.
3. **Android 15 edge-to-edge:** targetSdk 35 بيرسم المحتوى تحت شريط الحالة — `BaseActivity` بيضيف padding حسب الـ insets (top + bottom) لكل الـ Activities.
4. **الـ APK الحالي فيه إعلانات محاكاة مش حقيقية** (عدّ تنازلي 3 ثواني) — أي SDK إعلانات حقيقي محتاج بناء Gradle مخصص، **والبناء ده متعطّل في هذه البيئة** (Gradle مش بيوصل Maven Central من ورا البروكسي — لا تحاول تاني من غير حل بديل، شوف §15).

---

## 5. النشر (Release) — رفع APK جديد

1. ابنِ النسخة (§4) وتأكد من التحققات.
2. انسخ الـ APK + `index.html` المحدّث إلى `~/workspace/your_files/thumbnail-upload/` (مسارات المتصفح مبتحبش الـ symlinks).
3. حدّث `index.html`: غيّر رابط الـ APK (`CineReels-vX.Y.apk`) ورقم النسخة الظاهر.
4. ارفع الملفين لريبو `adam2211dmdm-ux.github.io` (root, main) من **المتصفح** (Add file → Upload files) — **Environment 2 أنجح واحد**. رسالة الكوميت: `CineReels vX.Y: <ملخص قصير>`.
5. **استنى دقايق واتأكد بـ curl قبل ما تبعت الرابط لآدم:**
   ```bash
   curl -sI https://adam2211dmdm-ux.github.io/CineReels-vX.Y.apk
   # لازم: HTTP 200 + content-type application/vnd.android.package-archive + الحجم الصح
   curl -s https://adam2211dmdm-ux.github.io/CineReels-vX.Y.apk -o /tmp/check.apk
   md5sum /tmp/check.apk   # لازم يطابق md5 الـ build المحلي
   curl -s https://adam2211dmdm-ux.github.io/ | grep "vX.Y"
   ```
   (GitHub Pages بيتأخر دقايق بعد الكوميت — 404 مؤقت طبيعي؛ أعد الفحص بعد ~75 ثانية لو قديم.)
6. ابعت لآدم الرابط المباشر + قوله **يمسح النسخة القديمة الأول** (نفس الـ package والتوقيع، فالتحديث بيركب فوقها، بس المسح أنضف لو فيه مشكلة).

---

## 6. الـ manifest — `videos.json` (قلب التطبيق)

- **المكان:** ريبو `cinereels-videos` (root). التطبيق بيجيبه من:
  `https://raw.githubusercontent.com/adam2211dmdm-ux/cinereels-videos/main/videos.json`
- **التوقيع اتلغى في v1.24:** من v1.24 مفيش `.sig` تاني — الـ manifest بيتقبل لو اتحلل وعدّى فحص same-origin/allowed-hosts. ملف `videos.json.sig` الحي قديم ومتقريش — ده متوقع ومش مشكلة. متعيدش التوقيع إلا لو رجّعت نظام التوقيع بقرار صريح. (تاريخياً: التوقيع كان HMAC-SHA256 بمفتاح `cinereels-hmac.key`، وسكربت `tools/sign_manifest.py` كان بيطلع الـ `.sig`.)
- **قبل أي push: هات آخر نسخة من GitHub (head) وادمج عليها** — آدم نفسه بينشر حلقات من متصفحه أثناء الشغل، ونسخة محلية قديمة ممكن تلغي شغله. استخدم connector `get_file_contents` لقراءة الـ head الحي.
- **حقول الفيديو المهمة:**

  | الحقل | معناه |
  |---|---|
  | `id`, `series_id`, `episode_number` | هوية الحلقة وترتيبها |
  | `title_en` / `title_ar` | عناوين الحلقات بتبدأ باسم المسلسل (الكود بيشيل التكرار تلقائياً) |
  | `video_url`, `thumbnail_url` | روابط raw.githubusercontent أو روابط ستريم مباشرة (شوف §12 — المسموح خبزه إيه) |
  | `subtitles_en_url`, `subtitles_ar_url` | ملفات .vtt (شوف §7) |
  | `duration_sec` | **لازم يساوي مدة الملف الحقيقية** (اتأكد بـ `ffprobe`) — التطبيق بيعرضها بصيغة `0:10` / `1:30` |
  | `language` | لغة الصوت: `"ar"` أو `"en"` — بيحدد سطر "صوت عربي • ترجمة إنجليزية" |
  | `subtitle_default` | الترجمة الافتراضية: `"ar"` أو `"en"` |
  | `burned_subs` | `true` لو الترجمة محروقة في الصورة (مفيش VTT مطلوب) |
  | `coming_soon: true` | حلقة معلنة بلا فيديو — **لا تُشغَّل أبداً** |
  | `web_page: true` | حلقة ويب (مش mp4) — بتتفتح في WebPlayerActivity (§10) |
  | `is_locked` | بعد الحلقات المجانية (25) — بتتفتح بالاشتراك |
  | `views`, `likes_count` | أرقام العرض (أعلى فيديو lm-ep1: 12,500) |

- **إضافة حلقة جديدة:** ارفع الـ mp4 (§6.1) → ضيف entry في `videos.json` → ثمبنيل → ترجمات (§7) → ادفع (§6.1).
- **السلسلة (series):** `description` / `description_ar` فيها عدد الحلقات — حدّثها لو اتغير العدد أو المدة. `free_episodes: 25` في كل المسلسلات.

### 6.1 رفع الملفات على GitHub (طرق الرفع)

**أ) ملفات نصية (videos.json, .vtt, .md, .json) — من الـ terminal بـ `github push-files`:**
```bash
# اكتب قائمة المسارات (NUL-separated) برّه مجلد المصدر
python3 -c "
paths = ['videos.json']
open('/tmp/push-paths.txt','wb').write(b'\x00'.join(p.encode() for p in paths) + b'\x00')
"
github push-files --owner adam2211dmdm-ux --repo cinereels-videos --branch main \
  --message "رسالة الكوميت" \
  --source-dir ~/workspace/your_files/cinereels/github-videos \
  --paths-file /tmp/push-paths.txt
# النجاح بيرجع commit SHA كامل — سجّله في ملف المزامنة:
# ~/workspace/your_files/cinereels/github-videos.muse-github-snapshot-sync.json
# (ضيف entry جديدة {owner, repo, branch, source_dir, commit_sha, paths} واحتفظ بالقديمة)
# اتأكد بعدها بـ curl إن الملفات الحية اتغيرت (raw.githubusercontent).
```
- الإجراء الكامل في `/opt/hatch/connectors/github/references/snapshot-push.md` — اقرأه قبل أي push.
- **قبل الدفع:** اتأكد إن الريموت لسه على نفس الحالة اللي اشتغلت عليها — لو حد غيّر حاجة (آدم بيرفع فيديوهات من المتصفح)، لازم تزامن الأول.
- `push-files` مبيعملش حذف ولا ملفات binary — للـ mp4 والـ apk استخدم (ب).
- **الـ push بتاع GitHub مش pre-approvable** — كل push بيطلع **approval card لآدم** لازم يدوس عليها، والكارت ممكن **يخلص وقته (timeout)** — لو حصل، أعد المحاولة وقوله.

**ب) ملفات binary (mp4, apk, webp) — من المتصفح فقط:**
- ريبو `cinereels-videos`: Add file → Upload files → حط الملف في `videos/` أو `thumbnails/` → Commit.
- ريبو `adam2211dmdm-ux.github.io`: نفس الطريقة للـ APK و `index.html` (§5).
- تسجيل الدخول بيحتاج كود جهاز من الجيميل كل مرة.
- **رفع فيديو جديد:** الملف لازم يكون mp4 (H.264 + AAC)، يفضل 720p. بعد الرفع خد رابط `raw.githubusercontent.com/.../main/videos/اسم.mp4` وحطه `video_url` في الـ manifest.

**ج) الثمبنيلز:**
- `thumbnails/ep1.webp` … `ep5.webp` = صور سينمائية حقيقية (اترفعت 2026-11-22).
- أي فيديو تاني بيستخدم `https://picsum.photos/seed/cinereels-<id>/720/1280` كبديل مؤقت.
- ثمبنيل جديد: ارفع webp/jpg لـ `thumbnails/` وحدّث `thumbnail_url`.

---

## 7. الترجمة (Subtitles) + الترجمة التلقائية

**اللي حصل:** الترجمة القديمة كانت مكتوبة لقصة إنجليزية مخترعة (90 ثانية) بينما الفيديوهات الحقيقية مقاطع عربية 10 ثواني — فمفيش حاجة كانت ماشية مع بعض. الترجمة الصح لازم تتفرغ من **الصوت الحقيقي**.

**خطوات عمل ترجمة لحلقة جديدة (مجرّبة 2026-11-23):**
```bash
# 1) حمّل الفيديو واستخرج الصوت 16kHz mono
curl -sL -o epN.mp4 https://raw.githubusercontent.com/.../videos/episodeN.mp4
ffmpeg -y -v error -i epN.mp4 -vn -ac 1 -ar 16000 epN_audio.wav
ffprobe -v error -show_entries format=duration -of csv=p=0 epN.mp4   # المدة الحقيقية
# 2) فرّغ الصوت (whisper-tiny، عربي)
OMP_NUM_THREADS=1 ~/workspace/whisper-venv/bin/python \
    ~/workspace/your_files/cinereels/transcripts/run_transcribe.py
# ملاحظات تقنية: faster-whisper المثبت بيكسر مع PyAV الحديث (metadata_errors) —
# السكربت بيتجاوز ده بتحميل الـ WAV بـ wave+NumPy مباشرة. متحاولش تصلح PyAV،
# الطريقة دي شغالة. النتيجة JSON في transcripts/episodeN.json
# 3) صحّح الإملاء يدوياً (whisper-tiny بيغلط في العامية المصرية — مثلاً
#    "فلحل قل أولى" = "في الحلقة الأولى"، "تطصاعد الموجهة" = "تتصاعد المواجهة").
#    لو مقطع مش واضح، سيبه بصياغة آمنة واكتب في الدليل إنه غير مؤكد.
# 4) اكتب ملفين WebVTT (نفس التوقيتات):
#    episodeN_ar.vtt = الكلام العربي كما قيل (مع NOTE إنها مفرغة من الصوت)
#    episodeN_en.vtt = الترجمة الإنجليزية لنفس الكلام
# 5) حدّث 3 أماكن بنفس المحتوى:
#    github-videos/subtitles/drama/ + github-videos/subtitles/ + cinereels-apk/assets/subtitles/
#    (التالتة هي الـ fallback المضمّن في الـ APK — لو نسيتها، المستخدم على نت بطيء
#     هيشوف الترجمة القديمة الغلط لما التحميل البعيد يفشل)
# 6) لو غيّرت duration/language/subtitle_default في videos.json، ادفع (§6.1).
#    ملفات الـ vtt نفسها مش موقّعة — التطبيق بيجيبها من روابط الـ manifest.
```

**صيغة WebVTT:**
```
WEBVTT

NOTE CineReels — The Last Message — Episode 3 — Arabic subtitles — the ACTUAL spoken dialogue (language: ar)

1
00:00:00.910 --> 00:00:03.910
لماذا لم تخبرني بكل هذا من قبل؟
```
- التوقيتات `HH:MM:SS.mmm` ولازم تكون **داخل مدة الفيديو** (فيديو 10 ثواني ماينفعش ترجمة لـ 90 ثانية).
- الترجمة الافتراضية في التطبيق = `subtitle_default` من الـ manifest؛ زر CC بيبدّل بين ar/en/off.
- في المشغّل: الترجمة بتظهر فوق الفيديو (feed: 272px فوق الأسفل، series: 216px)، خلفية سوداء شفافة، حجم افتراضي 19px.
- **سطور غير مؤكدة لسه (آدم لسه مأكدهاش):** ep1 cue 3 "Yeah, I have been…" (مقطوعة)؛ ep8 cue 1 "What do you mean, two lives?"؛ ep9 cue 6 + اسم شارع "Alman Sua Street"؛ ep4 cue 3.

### 7.1 الترجمة التلقائية — cron شغال (LIVE من 2026-11-23 13:44 EET)
- **الـ cron:** `cinereels-auto-translate` — كل 30 دقيقة. الـ watcher: `~/workspace/your_files/cinereels/tools/auto_translate.py` (venv في `~/workspace/whisper-venv/`، tesseract 5.3.4 ara+eng في `/usr/bin/tesseract`).
- بيلاقي الحلقات المنشورة اللي عندها فيديو بس ملهاش روابط ترجمة ولا `burned_subs`، بيفرّغ الصوت (faster-whisper tiny)، بيكتشف الترجمة المحروقة في الصورة، بيترجم EN↔AR، بيكتب .vtt، بيحدّث الـ manifest، ويدفع.
- **كاشف الترجمة المحروقة — VALIDATED:** band السفلي 22%، PIL luminance ≥190 + tesseract TSV؛ frame HIT = ≥3 كلمات (طول ≥2، conf ≥60)؛ الحلقة burned_in = ≥2 frame hits؛ الفريمات عند midpoints أول 3 speech segments + 3 كسور ثابتة (الكسور الثابتة لوحدها فشلت — midpoints هي الإشارة الأساسية؛ seek دقيق؛ المدة الحقيقية من ffprobe لأن مدد الـ manifest ممكن تبقى غلط). اختبارات: ep6 (معروفة محروقة) 3/6 hits → burned_in؛ ep4 (مفيش ترجمة) 0/3 → نظيفة؛ sc-ep1 → burned_in بنص عربي حقيقي، اتأكد بصرياً.
- **الـ GitHub push مش pre-approvable — كل push بيطلع approval card لآدم.**
- الحلقات اللي ترجمتها محروقة مش محتاجة VTT أصلاً.

---

## 8. الاشتراكات (Manual — WhatsApp + Vodafone Cash)

- **Play Billing متوقف بقرار آدم.** النظام الحالي يدوي و**للتوزيع خارج Google Play فقط** (Play بيفرض Play Billing على الفتح الرقمي — لازم يتعطّل قبل أي رفع على Play).
- **الأسعار (جنيه):** 3 أيام 50 / أسبوع 200 / شهر 600.
- **الرقم:** `201080482372` للواتساب وفودافون كاش معاً (مصر حالياً، دولي لاحقاً).
- **التدفق:** المستخدم يربط Gmail → يختار باقة → الطلب بيتحفظ برقم `CR-XXXX` + واتساب بيتفتح لآدم → يدفع فودافون كاش → آدم يوافق من الأدمن → فتح لحد تاريخ الانتهاء → قفل تلقائي.
- **المصدر الحقيقي = GitHub `subscribers.json`:**
  ```bash
  curl -s https://raw.githubusercontent.com/adam2211dmdm-ux/cinereels-videos/main/subscribers.json
  # {version, updated_at, admin_whatsapp, vodafone_cash, facebook_url, plans[], subscribers[]}
  # subscriber: {gmail, plan, status: pending/active/rejected/expired,
  #   requested_at, approved_at, starts_at, expires_at, approved_by}
  ```
  التطبيق بيجيب الملف عند الفتح وعند كل حلقة؛ نسخة GitHub بتغلب نسخة الجهاز (مسح التطبيق أو اللعب في الداتا المحلية مش بينفع). التطبيق **مش** بيدفع لـ GitHub أبداً (مفيش توكن في الـ APK) — الأدمن بيعمل Export والرفع يدوي.
- **دخول الأدمن:** موجود بس **مخفي تماماً** — لا يظهر ولا يتلمّح له في التطبيق إطلاقاً. **اسأل آدم عنه بس** — لا اسم مستخدم ولا كلمة سر في أي ملف أو شات (§17).
- **صفحة الاشتراك لازم تبقى احترافية جداً** عشان محدش يحس إن التطبيق نصب (طلب آدم): كروت باقات بتوضح إيه اللي بيتفتح بالظبط، الشهري "Best value"، 4 خطوات مرقّمة، رقم فودافون كاش واضح مع زر نسخ، رقم طلب لكل طلب، كارت "اشتراكي" (Pending → Approved → Active حتى تاريخ → Expired)، سطر دعم، وملاحظة ثقة إنه مفيش خصم داخل التطبيق لو التحويل متأكدش. مفيش عدّادات تنازلية ولا خصومات وهمية ولا ضغط.
- **فيسبوك:** زر Follow + مشاركة + لينك في الفوتر؛ رابط الصفحة آدم بيحطه بنفسه من الأدمن (فاضي افتراضياً — الزر بيقول "coming soon" لحد ما يتحط). حقل `facebook_url` في `subscribers.json`.

---

## 9. Monetag (إعلانات صفحة التحميل)

- الموقع `adam2211dmdm-ux.github.io` **Verified** في Monetag (meta tag في `index.html` — كل تسجيل موقع بيطلع tag جديد، القديم بتاع muse.ai ميت).
- **In-Page Push zone `12329911` شغال:** سكربت `https://nap5k.com/tag.min.js` بعد `<head>` في الصفحة الحية.
- صفحة التحميل البديلة في ريبو `cinereels-videos` تحت `docs/index.html` — نفس المحتوى.
- الإحصائيات بتبدأ من صفر وده طبيعي، بتاخد وقت تتجمع.
- **صفحة artifact بتاعة muse.ai مينفعش يتحط فيها سكربت الإعلانات** — GitHub Pages هو الحل الوحيد الحي.
- **إعلانات داخل التطبيق:** لسه مفيش قرار (AppLovin MAX / Unity Ads / Meta) — وأي SDK محتاج Gradle (متعطّل، §4/§15). **آدم مش عايز إعلانات داخل التطبيق أصلاً** ("لا انا مش عايز اعلانات" — 2026-11-23) — الاختيار ده لو اتعمل هيبقى لصفحة التحميل أو لمستقبل مختلف، مش للتطبيق الحالي.

---

## 10. استيراد مسلسل من رابط + narto-drama.com

### 10.1 الاستيراد من رابط (v1.19)
- **الاستيراد (صفحة الأدمن):** الصق رابط مسلسل من narto-drama.com → «جلب» → معاينة (الاسم + عدد الحلقات) → «استيراد المسلسل». التطبيق بيجيب الاسم والبوستر والوصف وقايمة الحلقات بالترتيب من صفحة التفاصيل نفسها (الكود: `SeriesImporter.java` — بيقرا `og:title` / `og:image` / `og:description` + روابط `/detail/watch/<slug>/<n>`).
- **الحلقات دي «ويب» مش mp4:** صفحة narto مش بتعرض لينك فيديو مباشر (المشغّل بيجيب الفيديو وقت التشغيل + فيه شاشة إعلان قبل المشاهدة). فالحلقة المستورَدة `video_url` بتاعها هو رابط صفحة المشاهدة، و`"web_page": true`، وبتتفتح في `WebPlayerActivity` (WebView بمشغّل الموقع نفسه + ملء الشاشة، من غير نوافذ جديدة عشان الإعلانات متفتحش تابات).
- **أماكن التوجيه:** `SeriesActivity.playEpisode` و`FeedActivity.playVideo` بيحوّلوا حلقات الويب لمشغّل الويب؛ `FeedActivity.rebuildFeed` بيستبعد حلقات الويب من الفيد العمودي (مكانها الطبيعي: صفوف المسلسلات ← صفحة المسلسل ← المشغّل).
- **الـ manifest:** `ManifestLoader.isSameOriginManifest` بيسمح بروابط وسائط من `narto-drama.com` و`img.nartodrama-api.online` (موقع آدم) — غير كده أي مضيف أجنبي لسه مرفوض. ده مهم عشان تعديل آدم لـ videos.json من غير إعادة توقيع يفضل شغال بعد ما بقى فيه مسلسلات مستورَدة.
- **تحذير:** آدم نفسه بينشر حلقات على GitHub من متصفحه أثناء الشغل — قبل أي push لـ videos.json لازم تجيب آخر نسخة من GitHub (head) وتدمج عليها. شوف `tools/add_narto_series.py` (بيكتشف الـ indent بتاع الملف تلقائياً عشان الـ diff يفضل صغير).

### 10.2 narto-drama.com — موقع آدم للمسلسلات
- **الموقع بتاع آدم** (أكّد ملكيته 2026-11-23). الكتالوج الكامل في `~/workspace/your_files/cinereels/narto-site-catalog.md` — **77 مسلسل عربي** (5 featured + 24 في كل صفحة كتالوج 1–3؛ صفحة رابعة موجودة ومتجمعتش).
- **"ND" هو label الموقع نفسه مش مزوّد** — الكتالوج العربي مفيهوش badge مزوّد لكل مسلسل. الطريقة الوحيدة تعرف مزوّد مسلسل هي تدوير على عنوانه في الـ gateway.
- **الدراما 1 — محلولة وشغالة (روابط مباشرة):** "الأم العازبة الهاربة وزوجها الملياردير" (56 حلقة) — ReelShort Arabic book `6ae163e2ef56d22b5e020027` (مدبلج `is_dub: 1`، `paid_start: 14`)؛ الروابط AliyunOSS ثابتة (`v-mps.crazymaplestudios.com`)، من غير token/expiry؛ `urls[1]` = 540p H264 `-ld.m3u8` (هو المستخدم)؛ `urls[0]` = 720p H265 (ممنوع — شاشة سوداء)؛ `urls[2]` = master H265 (ملوش لازمة). الترجمة العربية محروقة في الصورة (اتأكدت بصرياً). الملفات: `narto-runaway-mother-streams.json` + `narto-runaway-mother-detail.json` في `~/workspace/your_files/cinereels/`.
- **الدراما 2 — اتسابت بقرار آدم** ("سيبك من المسلسل التاني دا هاتلي اي مسلسلات شغاله" — 2026-11-24 07:34 EET). مزوّدها لسه مجهول (مش dramabox ولا reelshort ولا على Sansekai). متكملش التدوير عليها إلا لو طلب.
- **الـ gateway بتاع آدم:** `https://api.narto-drama.com/` (header `X-Api-Key`؛ الخطة المجانية $0: **50 طلب/ساعة، مزوّد واحد، مفتاح واحد**). المفاتيح اتبعتت في الشات باختيار آدم و**قيمها مش مسجلة في أي مكان — استخدمت transient في curl بس. متطلبهاش تاني منه؛ لو مفتاح اتحتاج، اعرض رابط الـ secure capture الأول.** رابط secure capture اتبعت 2026-11-24 00:42 EET ولسه مفيش رد.
- **مشغّل الموقع نفسه مقفول بإعلانات** (play → "افتح 6 من 6 إعلانات") ومفيش رابط ستريم مباشر في الصفحة، وcurl من الـ VM محجوب بـ Cloudflare. **آدم مش عايز إعلانات في التطبيق.** الموقع بيفتح popunder 1xBet عند الضغط على حلقة.
- **مسلسلات narto المرشحة من الكتالوج (featured — آدم لسه مختارش):** "عروس بديلة تغزو الأثرياء" (40 حلقة)، "ندمت الإمبراطورة على خسارتي" (51)، "أستاذهم العراب" (50)، "حصلت على ثلاث حبيبات من النظام" (30).

---

## 11. حصاد Sansekai API — مصدر المسلسلات الشغالة

- **إيه هو:** API عام مجاني لمسلسلات قصيرة على `https://api.sansekai.my.id` (الـ docs صفحة Swagger على `https://api.sansekai.my.id/`). **مفيش API key** — GET عادي. **Rate limit: 5 طلبات/دقيقة** (headers حية؛ الـ docs بتقول 10) — باعد المكالمات 12–15 ثانية. **ممنوع تشغيل مهمتين browser على Sansekai في نفس الوقت** (هيتجاوزوا الليمت مع بعض).
- **ملاحظة تشخيصية مهمة:** curl من الـ VM بيرجع 403 — دي حماية Cloudflare ضد الطلبات غير المتصفح، مش نقص مفتاح. **المتصفح الحقيقي بيشتغل** (Environment 2 أنجح). الـ endpoint بتاع الحلقات هو **`/dramabox/get-allepisode`** (مش `/allepisode`)، وبطيء (~40 ثانية لـ ~80 حلقة).
- **11 مزوّد:** DramaBox، ReelShort، ShortMax، GoodShort، NetShort، DramaNova، FlickReels، FreeReels، Melolo، MyDrama، PineDrama. (فيه كمان Komik/MovieBox/Viu — مش مسلسلات قصيرة.)
- **الحصاد batch 1 (2026-11-24 07:35–08:21 EET):** سجله الكامل في `~/workspace/your_files/cinereels/sansekai-harvest-batch1.md` — top-5 lists، endpoints، أسماء الحقول، والأحكام، وكل روابط ReelShort الـ 52.
- **الحصاد batch 2 (2026-11-24 08:24–09:41 EET):** سجله في `~/workspace/your_files/cinereels/sansekai-harvest-batch2.md` (الـ task الأول errored والـ recovery جاب Parts B/C/D كاملة وPart A جزئية — شوف "مش مكتمل" تحت).
- **⚠️ الـ API IP blacklist (واقف من 2026-11-24 الصبح):** Cloudflare 502 (07:16–07:20 UTC) → "Forbidden: bandwidth limit" (07:26) → رسالة إندونيسي "IP Anda telah diblacklist karena aktivitas mencurigakan" (07:31؛ اتعاد فحصه 07:41 UTC لسه محظور). الـ rate limit كان محترم طول الوقت (pacing 13 ثانية، max 5/دقيقة، مفيش 429). **متحاولش تتخطاه بـ proxies — ممنوع.** الحلقات الناقصة محتاجة IP مش محظور بعدين. الروابط الـ tokenized **متعمداً مش متخزنة** في ملفات الحصاد — بتخلص صلاحيتها؛ أعد الجلب وقت التشغيل.
- **`dramabox.sansekai.my.id` واقع:** كل الطلبات Cloudflare Error 522 "Connection timed out" (اتفحص 2026-11-24 07:22–08:20 EET). جرّب تاني بعدين — أولوية واطية؛ الـ harvest من `api.sansekai.my.id` هو الطريق الشغال.
- **أهم المسلسلات (lang=ar):**
  - DramaBox: "وداع بلا ندم (مدبلج)" `42000001128`، 65 حلقة.
  - ReelShort: "انتقام إله الأمواج" `6adabb702d149b359f09097c`، 52 حلقة (اتخبزت في v1.26 — 38/52 شغالة)؛ "أخوهم، قربان التنانين" `6adb1792e617791aa509e88f`، 50 حلقة؛ "لولو الإلهة الصغيرة" `6ad5e84ea0f7d495980630bf`، 61 حلقة؛ "متحدث التنانين بلا قيود" `6aca0e86879cac5ec505e33e`، 47 حلقة.
  - ShortMax: "[مدبلج]حياتي ليست لعبة" `59074`، 25 حلقة.
  - GoodShort: "المدبلج-نساء الزوج البطل" `31001928423`، 61 حلقة (metadata بس).
  - NetShort: "Ibu Rahasia Sang Pewaris Serigala" `2124348784462745602`، 36 حلقة.
- **ملحوظة:** عناوين إنجليزية مش بترجع للكتب دي — قوائم `lang=en` ترتيبات مختلفة مش ترجمات. الـ English harvest لسه متعملش (متأجل بعد شغل التشفير).
- **مش مكتمل من batch 2 (محتاج إعادة جلب من IP مش محظور):** PineDrama الحلقات 26–76، Melolo 2–72، MyDrama 2–90، FlickReels 2–80. FreeReels اتجابت 56/56 بس روابط الحلقات **موصلتش في الـ summary** — محتاجة إعادة جلب. PineDrama الحلقات 1–25 اتجابت بس روابطها برضه موصلتش.

---

## 12. التشفير والتشغيل — القصة الكاملة لكل مزوّد

> **ليه القسم ده موجود:** آدم قالها صراحة 2026-11-24 08:36 EET: "بس ركز في قصه التشفير وحلها بتعت الدرامه وبقيت المزودين" — قصة التشفير وحلها هي **الأولوية القصوى**. الأحكام دي من harvest batch 2, Part D (اتأكدت بالتجربة)، والمصدر الكامل: `~/workspace/your_files/cinereels/sansekai-harvest-batch2.md`.

### القاعدة الدائمة — NEVER bake tokenized/encrypted URLs
- **ممنوع خبز أي رابط tokenized أو مشفر في الـ manifest أبداً.** الروابط دي بتنتهي صلاحيتها؛ اللي يتخبز هو **الروابط المباشرة الثابتة بس** (ReelShort `-ld`، FreeReels، MyDrama).
- أي حاجة تانية = **جلب طازج وقت التشغيل** (fresh fetch per playback) من الـ API — التطبيق بيجيب الرابط الطازج وبعدين يشغّله، ومبيخزنش الرابط.
- الروابط الـ tokenized **متعمداً مش متخزنة** في ملفات الحصاد — بتخلص صلاحيتها؛ أعد الجلب وقت التشغيل.

### جدول الأحكام (الخلاصة)
| المزوّد | التشفير/التوكن | يتخبز في الـ manifest؟ | حل التشغيل |
|---|---|---|---|
| **ReelShort** | مفيش — مباشر ثابت | ✅ نعم (`-ld` بس) | شغّل `-ld` 540p H264 مباشرة |
| **FreeReels** | مفيش — مباشر ثابت | ✅ نعم (بعد إعادة الجلب) | شغّل مباشرة |
| **MyDrama** | مفيش — مباشر ثابت | ✅ نعم (بعد إعادة الجلب) | شغّل مباشرة |
| **DramaBox** | `.encrypt.mp4` مشفر + توقيع CloudFront | ❌ لأ | ابنِ رابط proxy الـ decrypt **أوفلاين** (0 مكالمات زيادة) — شوف التفاصيل |
| **NetShort** | tokenized mp4 (`playVoucher`) | ❌ لأ | جلب طازج كل تشغيل، شغّل مباشرة |
| **PineDrama** | tokenized MP4 | ❌ لأ | جلب طازج كل تشغيل |
| **FlickReels** | tokenized (`?verify=` + expiry) | ❌ لأ | جلب طازج كل تشغيل |
| **Melolo** | tokenized + مشفر | ❌ لأ | جلب طازج؛ محتاج proxy فك تشفير (مش محلول) |
| **ShortMax** | تشفير قطاعات مخصص | ❌ لأ — **ومش شغال أصلاً بمشغّل عادي** | محتاج proxy HLS من السيرفر أو ExoPlayer مخصص (Gradle متعطّل) |
| **GoodShort** | — (مفيش ستريمات أصلاً) | ❌ | متستخدمهوش للتشغيل |
| **DramaNova** | — (مش موجود في الـ API) | ❌ | مفيش calls ممكنة |

### DramaBox — ✅ PLAYABLE (مشفر، بس الحل شغال ومتأكد)
- **التشفير:** الملفات `.encrypt.mp4` مشفرة (CloudFront-signed)، الجودات 1080/720/540/360/144، الافتراضي 720p، و1080p VIP. الحقل `isM3u8 = 0` — دي ملفات mp4 مش playlists. المسارات في `cdnList[].videoPathList[].videoPath` (الـ CDN الافتراضي `hwztvideo.dramaboxdb.com`).
- **حل التشغيل (3 خطوات، متأكد بالتجربة):**
  1. **جلب طازج وقت التشغيل:** `GET /dramabox/get-allepisode?bookId=<id>&lang=ar` → خد `cdnList[].videoPathList[].videoPath` الطازج (الـ Expires/Signature بيتغيروا كل جلب؛ في الاختبار الـ Expires الطازج كان `1795582800`).
  2. **ابنِ رابط الـ proxy أوفلاين — 0 مكالمات API زيادة:** `https://api.sansekai.my.id/api/dramabox/get-decrypt-video?url=<URL-encoded videoPath>` — الرابط ده بيتبنى **من غير أي مكالمة** (بناء نصي بس). الـ endpoint التاني `GET /dramabox/decrypt-url-video?url=<same>` بيرجع **نفس الـ streamUrl حرفياً** — استدعاؤه اختياري للتحقق بس (مكالمة تانية بنفس الإدخال رجّعت نفس الـ streamUrl).
  3. **شغّل رابط الـ proxy في مشغّل عادي** — اتأكد: المتصفح شغّل فيديو مفكوك التشفير (فريمات + عنوان صيني + ترجمة عربية).
- **ممنوع تخزين رابط الـ proxy أو الـ videoPath** — بينتهي. ابنِه طازج كل مرة.
- **أهم مسلسل:** "وداع بلا ندم (مدبلج)" `42000001128`، 65 حلقة.

### NetShort — ✅ PLAYABLE (tokenized، بس مباشر بعد الجلب الطازج)
- **التشفير:** mp4 مباشر (`mime_type=video_mp4`) بس **tokenized** — `playVoucher` فيه `auth_key` + params (`br`/`bt`/`eid`/`l`/`rc`). مفيش تشفير محتوى — التوكن بس اللي بينتهي.
- **حل التشغيل (خطوتين، متأكد بالتجربة):**
  1. **جلب طازج وقت التشغيل:** `GET /netshort/get-episodes?shortPlayId=<id>&episodeNumber=N&lang=ar` → خد `playVoucher`.
  2. **شغّل رابط الـ MP4 مباشرة في مشغّل عادي** — اتأكد: إعادة الجلب رجّعت `playVoucher` **مطابق حرفياً** للقديم، والرابط القديم شغّل في المتصفح (3:27، مطابق لـ 207.875 ثانية). مفيش decrypt ولا proxy مطلوب.
- **ملاحظات:** `/netshort/foryou?lang=ar` و`/netshort/theaters?lang=ar` بيرجعوا `null` حرفياً — الـ top list جت من `lang=id` (عناوين إندونيسي). الترجمة webvtt **id_ID بس** في رد الحلقة 1 رغم `lang=ar`.
- **أهم مسلسل:** "Ibu Rahasia Sang Pewaris Serigala" `2124348784462745602`، 36 حلقة.

### ShortMax — ❌ NOT PLAYABLE by a stock player (تشفير قطاعات مخصص)
- **التشفير:** HLS تحت `/hls-encrypted/`، `needDecrypt: true`، و`auth_key` بيتجدد كل جلب (`episode.videoUrl.video_720` — وفيه video_1080/video_480). **الـ auth_key القديم بينتهي** — الرابط القديم مش بيحمل أبداً؛ والـ auth_key **الطازج** بيرجع "Unable to play media" في مشغّل عادي.
- **مفيش Sansekai decrypt endpoint** — الـ API فيه بس `/shortmax/foryou`، `/latest`، `/rekomendasi`، `/search`، `/detail`، `/get-episodes`. مفيش endpoint فك تشفير.
- **التشفير الحقيقي (من proxy الـ demo site):** كل مقطع `.ts` شايل **header 1040 بايت "shortmax"**، والمفتاح الـ 16 بايت AES **مضمّن فيه** (`keyPos` = عدد ASCII في البايتات 16–20، `keyOffset = keyPos − 24`)، و**أول 1024 بايت بس** متشفرة AES-128-CBC بـ IV `"shortmax00000000"`. الـ proxy بيعيد كتابة روابط الـ playlist من خلال نفسه وبيرجع `.ts` مفكوكة (`video/mp2t`).
- **الحل (اتنين، والاتنين مش جاهزين):**
  1. **استضافة/تكرار proxy الـ HLS من السيرفر** — الكود المرجعي: `https://raw.githubusercontent.com/Sansekai/SekaiDrama/refs/heads/main/src/app/api/shortmax/hls/route.ts` (لازم يتستضاف ويتكرر، مش مجرد قراءة).
  2. **فك التشفير داخل التطبيق** (مثلاً ExoPlayer custom DataSource) — و**ExoPlayer محتاج الـ Gradle build المتعطّل** (§15).
- **`#EXT-X-KEY` / key URI مش متشاف مباشرة** (view-source محجوب؛ الـ .m3u8 بيتعامل كـ media) — التشفير الحاسم هو صيغة المقطع المخصصة، مش key URI قياسي.
- **أهم مسلسل:** "[مدبلج]حياتي ليست لعبة" `59074`، 25 حلقة. **متحاولش تشغّل ShortMax بمشغّل عادي — مش هيشتغل.**

### ReelShort — ✅ مباشر/ثابت (مفيش تشفير)
- **الصيغة:** `videoList[].url` — مفيش token/expiry/توقيع. كل حلقة بترجع 3 مدخلات: 720 H265 `-video-sd.m3u8` (الـ token `38632476b0de7c8d75bff1df3712145a` **ثابت في كل الـ 52 حلقة**)، 540 H264 `-ld.m3u8` (**الـ token بيختلف كل حلقة**)، 0 H265 plain `.m3u8`.
- **استخدم روابط `-ld` 540p H264 بس** — الـ `-sd` 720p H265 = شاشة سوداء على موبايل آدم، والـ master playlist كل رندراته H265 (ملوش لازمة).
- **الـ token بتاع `-ld` مينفعش تشتقه من `-sd`** — لازم تجيب `videoList` الكامل لكل حلقة.
- **يتخبز في الـ manifest** — هو المزوّد الوحيد اللي اتخبز فعلاً (v1.26: "انتقام إله الأمواج" 52 حلقة — 38/52 شغالة، 14 ميتة 404: 18، 22، 23، 24، 26، 27، 29، 34، 38، 41، 44، 45، 46، 51 — محتاجة إعادة جلب `videoList` لما الـ blacklist يترفع).

### FreeReels — ✅ مباشر/ثابت (مفيش تشفير)
- **الصيغة:** `video-v6/v7/v81.mydramawave.com` h264/h265 `.m3u8`، مفيش token. الـ endpoints: `/freereels/foryou`، `/freereels/detailAndAllEpisode` (lang=en؛ ar مرفوض).
- **"My Ex Gave Me to the Coconut Mayor"**، id `hKpitmwIz8`، 56 حلقة — **اتجابت 56/56 كاملة**، بس **روابط الحلقات موصلتش في الـ summary** بتاع الـ recovery — **محتاجة إعادة جلب قبل الخبز**.

### MyDrama — ✅ مباشر/ثابت (مفيش تشفير)
- **الصيغة:** `cdn.my-drama.tv/<32-hex>/main.m3u8`، مفيش token. الـ endpoints: `/mydrama/populer`، `/mydrama/detail`، `/mydrama/episode` (lang=en؛ ar مرفوض).
- **"A Queen for the Mafia Kings"**، id `f6f1c462-87f3-4d92-8e26-4f22e4c0ece0`، 90 حلقة — **الحلقة 1 بس اللي اتجابت**؛ 2–90 لسه متجابتش. **ملاحظة غير محسومة:** parse رابط الحلقة 1 CloudFront طلع `"1_.m3u8"` مقابل `"1_m3u8"` في السكرين شوت — لسه متحلتش.

### PineDrama — ⚠️ tokenized (جلب طازج كل تشغيل)
- **الصيغة:** MP4 tokenized — الـ `best_url` حقل **top-level** (مثبت بالـ parse) وشايل `rc` token خاص بيه، مختلف عن `rc` بتاع مدخلات `indo_cdn_urls`. الحلقات 1–10 `HD_INDO`، 11–25 `SD_INDO`، والـ alt بقى `null` من الحلقة 11.
- **"رئيسي في العمل هو زوجي" / "زوجي السري هو رئيسي في العمل"**، id `7672538805677691911`، 76 حلقة — الحلقات 1–25 اتجابت بس **روابطها موصلتش في الـ summary**؛ 26–76 متجابتش (blacklist). الـ endpoints: `/pinedrama/foryou`، `/pinedrama/detail`، `/pinedrama/get-episode` (lang=ar).

### FlickReels — ⚠️ tokenized (جلب طازج كل تشغيل)
- **الصيغة:** tokenized/expiring (`?verify=`، `hls_timeout 1795504331`، `hls_time_left 2400`). الـ endpoints: `/flickreels/foryou`، `/flickreels/detail`، `/flickreels/get-episodes` (lang=ar).
- **"Dendam Seberat 200 Kilo"**، id `420`، 80 حلقة — **الحلقة 1 بس**؛ 2–80 لسه متجابتش.

### Melolo — ⚠️ tokenized + مشفر (مش محلول)
- **الصيغة:** tokenized/encrypted (decrypt-stream proxy، `key=`، `dy_q` expiry، `bytevc1`). الـ endpoints: `/melolo/foryou`، `/melolo/detail`، `/melolo/get-episode` (lang=id؛ ar مرفوض).
- **"Anak Angkat Penuh Hoki"**، id `7702657769018510389`، 72 حلقة — **الحلقة 1 بس**؛ 2–72 لسه متجابتش. ملاحظة: مدخل جودة سادس (720p) ظهر في سكرين شوت واحدة بس مش في الـ parse — مفيش رابط ليه. **مستبعد من الـ provider picker في v1.26.**

### GoodShort — ❌ مفيش ستريمات أصلاً
- **metadata بس** — الـ API مش بيرجع أي episode streams. متستخدمهوش للتشغيل من الـ API ده. **مستبعد من الـ provider picker.**

### DramaNova — ❓ مش موجود في الـ API
- **مش موجود أصلاً في docs الـ API** — مفيش section ولا endpoints ولا calls ممكنة. **مستبعد من الـ provider picker.**

### سياق الـ IP blacklist (ليه الجلب الطازج من الـ cloud browser واقف دلوقتي)
- من 2026-11-24 الصبح: Cloudflare 502 (07:16–07:20 UTC، اتعافى) → "Forbidden: bandwidth limit" (07:26) → "Forbidden: IP Anda telah diblacklist karena aktivitas mencurigakan" (07:31؛ اتعاد فحصه 07:41 UTC لسه محظور).
- الـ rate limit كان محترم طول الوقت (pacing 13 ثانية، max 5/دقيقة، مفيش 429 اتشاف).
- **متحاولش من الـ cloud browser env دلوقتي، ومتتخطاش بـ proxies.** الحلقات الناقصة محتاجة IP مش محظور (متصفح/موبايل آدم، أو انتظار رفع الحظر).
- **خطر إضافي معلّق:** مكالمات HTTP من موبايل آدم لـ Sansekai ممكن Cloudflare يحجبها برضه (الـ VM بيتجب 403؛ المتصفح الحقيقي شغال؛ موبايل على داتا لسه غير مؤكد — اختبار موبايل آدم هو التأكيد).

---

## 13. الدعم — لما آدم يبلّغ عن مشكلة

### 13.1 ترياج الدعم — cron شغال (LIVE من 2026-11-23)
- **الـ cron:** `cinereels-support-triage` — كل 15 دقيقة. بيفحص `adam2211dmdm@gmail.com` عن إيميلات `[CineReels Support]`، بيجهز ردود بلغة المستخدم، وبيسجل الـ bugs في `~/workspace/your_files/cinereels/support/bugs.md`.
- **الإرسال محتاج دوسة آدم.**

### 13.2 لما آدم يبلّغ عن مشكلة
1. اطلب سكرين شوت + وصف اللي حصل بالظبط (أي حلقة؟ أي زر؟).
2. شوف الصورة كويس: اللي باين فيها هو التشخيص (مثال: فيديو صغير فوق + سواد = فيديو أفقي في شاشة عمودية؛ شاشة سوداء أثناء التحميل = مفيش placeholder).
3. لو كراش عند الفتح: شوف الـ logcat — أول سطر FATAL هو السبب. (Appetize.io كان الطريق ده — **الـ free tier خلص لحد 1 ديسمبر 2026**، شوف §15.)
4. قبل ما تقول "اتصلح": ابنِ، اتأكد من §4، ويفضل جرّب على موبايل آدم أو استنى تأكيده.
5. **لا ترجع حاجة اتشالت بقرار آدم** (مثال: الترجمة المخترعة — اتشالت لسبب).

---

## 14. دروس صعبة / Gotchas — لا تعيد الغلط

1. **R8 بيشيل الـ constructors (الدرس القاتل):** قاعدة الـ ProGuard لازم تحافظ على `<init>();` لكل Activity، مش `onCreate` بس. غير كده التطبيق بيموت فور فتحه برسالة صامتة — حصل في v1.2 لحد v1.6. اتصلح في v1.7.
2. **ممنوع Lambda:** المشروع بيتبني على android.jar مباشرة — استخدم anonymous inner classes دايماً.
3. **Android 15 edge-to-edge:** targetSdk 35 بيرسم المحتوى تحت شريط الحالة — `BaseActivity` بيضيف padding حسب الـ insets.
4. **RTL بيقلب Gravity.START:** في العربي، `Gravity.START` بيروح **يمين** مش شمال. أي حاجة مثبتة على جهة فيزيائية لازم `Gravity.LEFT` المطلق (الدرس ده كلفنا v1.22 كاملة — الرقعة راحت يمين).
5. **`assets/videos.json` نسخة منفصلة:** الـ manifest المضمّن في الـ APK نسخة تانية غير `github-videos/videos.json` — **زامنها قبل كل build** وإلا الـ APK هيشحن كتالوج قديم.
6. **HMAC byte-exact (تاريخي):** الـ `fetchUrl` القديم كان بيضيف `\n` بعد كل سطر فالتوقيع كان بيفشل بصمت — ده كان سبب bug v1.13. **من v1.24 التوقيع اتلغى أصلاً** — بس لو رجّعته، القراءة لازم تكون بايتات دقيقة. ومفتاح HMAC (`cinereels-hmac.key`) **HEX-encoded** — اتأكد بـ `bytes.fromhex(...)` مش بايتات الملف الخام.
7. **Manifest cache version stamp:** `ManifestLoader.load()` بيفضّل الـ cache المخزن (`manifest_cache` في SharedPreferences) على الـ manifest المضمّن. من v1.22 الـ cache بيتختم بـ versionName التطبيق (`manifest_cache_version`) والـ cache اللي versionه مختلف بيتجاهل. لو حلقات جديدة مش ظاهرة بعد تحديث، ده أول مكان تبص عليه. `HomeActivity.refreshManifestFromGitHub()` بيحدّث الـ cache عند فتح Home.
8. **GitHub push approval cards + timeouts:** كل push بيطلع approval card لآدم ولازم يدوس عليها، والكارت ممكن يخلص وقته. لو push فشل بـ timeout، أعد المحاولة وبلّغ آدم. **ومتستخدمش GitHub App API لإنشاء repos — بيرفض 403؛ الـ repos بتتعمل من المتصفح.**
9. **Pages deploy lag:** GitHub Pages بيتأخر دقايق بعد الكوميت — 404 مؤقت طبيعي. أعد الفحص بعد ~75 ثانية قبل ما تقول إن الرفع فشل.
10. **`/tmp` صغير (512 MB tmpfs):** بيتملي بسرعة — حط ملفات الاختبار تحت الـ home مش /tmp.
11. **ReelShort H265 = شاشة سوداء:** أي رابط `-sd` (720p H265) أو master playlist على موبايل آدم بيطلع شاشة سوداء. استخدم **`-ld` 540p H264 بس**. والـ token بتاع `-ld` بيختلف كل حلقة — مينفعش تشتقه.
12. **Sansekai من الـ VM = 403 دايماً:** curl من الـ VM محجوب بـ Cloudflare — ده مش معناه إن الـ API واقع. المتصفح الحقيقي (Environment 2 أنجح) هو اللي بيشتغل.
13. **الـ `.sig` القديم مش مشكلة:** الـ `videos.json.sig` الحي stale من v1.24 — متوقع ومش مشكلة، متعيدش توقيعه.
14. **آدم بيعدّل الـ manifest من متصفحه أثناء الشغل** — قبل أي push لـ `videos.json` هات الـ head الحي وادمج عليه (§6).
15. **raw.githubusercontent ممكن يخدم نسخة قديمة من الـ CDN** بعد push — استنى شوية وأعد الفحص قبل ما تقول إن التحديث موصلش.
16. **MEMORY.md اتغيرت من عمليات خارجية قبل كده** (سطور اتشالت/اتبدلت) — اتأكد من الحقائق من الـ disk/dex/مصادر حية لما الموضوع مهم.
17. **الثمبنيلز:** picsum placeholders ممكن متفشلش على نت بطيء (آدم شاف 2 KB/s)؛ الثمبنيلز الحقيقية (stills سينمائية) في `thumbnails/` على GitHub. وGTV-bucket sample thumbnails بترجع 403.
18. **الترجمة المضمّنة fallback:** ملفات .vtt لازم تتحدث في 3 أماكن بنفس المحتوى (`github-videos/subtitles/drama/` + `github-videos/subtitles/` + `cinereels-apk/assets/subtitles/`) — لو نسيت التالتة، المستخدم على نت بطيء هيشوف الترجمة القديمة الغلط.
19. **الـ subtitles المضمّنة بتتسرب بين المسلسلات لو مش مربوطة بـ series:** من v1.21 الـ fallback المضمّن مقيّد بـ `last-message`/`second-chance` بس.
20. **الـ `videos.json.sig` والـ HMAC key مبيترفعوش أبداً** — المفتاح في `~/workspace/snake-colony-work/cinereels-hmac.key` بس.

---

## 15. قائمة DO NOT RETRY — حاجات متجربهاش تاني

| الحاجة | ليه ممنوع | البديل |
|---|---|---|
| **Real-AdMob / أي SDK إعلانات — custom Gradle build** | **BLOCKED هنا:** Gradle مبيقدرش ينزّل من Maven Central/Plugin Portal من ورا الـ egress proxy. اتجرب واتقفل 2026-11-22 ~19:04 EET بقرار صريح: **متكملش المهمة دي، متعيدش تفويضها، متعيدش صياغتها، ومتعملهاش من طريق تاني.** | الإعلانات المحاكاة (3 ثواني) في الـ APK الحالي؛ Monetag على صفحة التحميل (§9)؛ آدم يعمل الـ build الحقيقي بنفسه على جهازه لو حب. |
| **توليد الفيديو بالـ AI** | **403 دائم — قيود دولة/منطقة على الحساب ده** (5 محاولات فاشلة 2026-11-22). العيشة في أمريكا مش بتلغي الحظر لأنه مربوط بالـ account region (مصر من إعدادات AdMob). | صور ثابتة سينمائية + تجميع بـ ffmpeg (slow zoom/pan + voiceover + ترجمة) — العرض ده لسه آدم موافقش عليه ("كمّل بالصور" لسه معلّق، §16). |
| **Appetize.io emulator** | **الـ free tier خلص لحد 1 ديسمبر 2026.** مفيش تحقق emulator لحد التاريخ ده. | موبايل آدم هو جهاز الاختبار. |
| **Sansekai API IP blacklist — تخطي بـ proxies** | الـ IP محظور (Cloudflare 502 → "bandwidth limit" → "IP blacklisted"). **ممنوع تتخطاه بـ proxies.** | استنى لما الحظر يترفع، أو استخدم IP مش محظور (متصفح/موبايل آدم). |
| **`dramabox.sansekai.my.id`** | واقع (Cloudflare 522) من 2026-11-24. | الـ harvest من `api.sansekai.my.id` هو الطريق الشغال. |
| **إعادة إنشاء keystore** | فقدان/استبدال الـ keystore = مستحيل تحديث التطبيق. | استخدم نفس الـ keystore دايماً (§3). |
| **إرجاع الترجمة المخترعة / الفيديوهات التجريبية** | اتشالت لسبب (الترجمة مكانتش مطابقة للصوت الحقيقي؛ الفيديوهات التجريبية اتمسحت بقرار آدم). | ترجمة مفرّغة من الصوت الحقيقي بس. |
| **خبز روابط tokenized/مشفرة في الـ manifest** | بتنتهي صلاحيتها وبتكسر الحلقات. | جلب طازج وقت التشغيل (§12). |

---

## 16. أسئلة وقرارات معلّقة عند آدم

1. **v1.25/v1.26 على موبايله:** الـ blur مغطي حرف الـ R دلوقتي؟ وv1.26 شغالة والمسلسل الجديد ظاهر؟ والجلب من الموبايل شغال ولا Cloudflare بيحجبه؟ (اتطلب سكرين شوت 2026-11-24 07:26 و~08:30؛ رد "تمام" من غير إجابة.)
2. **الـ 14 حلقة الميتة** (18، 22، 23، 24، 26، 27، 29، 34، 38، 41، 44، 45، 46، 51) — إعادة جلب لما الـ Sansekai blacklist يترفع.
3. **اختيار مسلسلات narto جديدة** من الكتالوج (الـ 4 featured اتقترحت 2026-11-24 00:42 EET) + **إرسال مفتاح ReelShort gateway عبر رابط الـ secure capture** (اتبعت 00:42 EET — لسه مفيش رد). أولوية أقل بعد الـ pivot لـ Sansekai، بس لسه مفتوحة.
4. **اختيار شبكة إعلانات** (AppLovin MAX / Unity Ads / Meta) — أي SDK محتاج Gradle (متعطّل). آدم لسه مختارش — ومش عايز إعلانات داخل التطبيق أصلاً (§9).
5. **Play listing لسه ناقص منه:** privacy-policy URL، أيقونة 512px، feature graphic، استبيان content rating، نموذج Data Safety.
6. **English harvest + الترجمة** ("هات انجليزي والترجمه بتعته" — 2026-11-24 08:35 EET) — متأجلة بعد شغل التشفير؛ لسه متجابش حاجة.
7. **نتيجته لاختبار v1.18** (رفض الدخول الفاضي + صفحة التسجيل) — متبلغش بيها.
8. **هل الـ web demo (artifact `cinereels`) يقرا/يكتب GitHub `subscribers.json`؟** — سؤال مفتوح (الـ demo حالياً بيخزن الاشتراكات في قاعدة بياناته الخاصة مش GitHub).
9. **هل نرجع قصة المسلسل للـ outline القديم (العم/البيت/الفلوس)؟** — سؤال مفتوح (النسخة الحالية: ليلى + سارة).
10. **عرض "كمّل بالصور":** تجميع فيديوهات من الـ stills السينمائية + narration بـ ffmpeg — لسه موافقش.
11. **سطور الترجمة غير المؤكدة** (الحلقات 1/4/8/9 — §7) — آدم لسه مأكدهاش.
12. **إعادة فحص `dramabox.sansekai.my.id`** بعدين (واقع 522 من 2026-11-24).
13. **روابط حلقات FreeReels (56/56) وMyDrama (2–90) وPineDrama (26–76) وMelolo (2–72) وFlickReels (2–80)** — موصلتش في الـ summaries، محتاجة إعادة جلب من IP مش محظور.
14. **الـ ShortMax proxy:** هل نستضيف/نكرر proxy الـ HLS بتاع الـ demo site (§12)؟ — قرار معلّق (البديل ExoPlayer محتاج Gradle المتعطّل).

---

## 17. سياسة الأسرار

**القاعدة: لا قيمة سرّية في أي ملف عام أو أي شات — أبداً.**

- **ممنوع كتابته في أي مكان (ملفات، شات، GitHub، zips):** أي كلمة سر، أي API key، أي كلمة سر keystore، كلمة سر الأدمن، أكواد التحقق/الـ OTP، مفاتيح HMAC.
- **المسموح كتابته: مكان السر بس** (مثال: "كلمة سر الـ keystore في `.cinereels_pass.txt` جنب الـ keystore"، "مفتاح HMAC في `~/workspace/snake-colony-work/cinereels-hmac.key`").
- **دخول الأدمن في CineReels:** سري تماماً بين آدم وMuse. اكتب بس **"دخول أدمن موجود؛ اسأل آدم"** — لا اسم مستخدم ولا كلمة سر، ولا تلميح لوجوده في التطبيق.
- **مفاتيح narto gateway (dramabox/reelshort):** آدم بعتها في الشات باختياره، واستخدمت transient في curl بس، و**قيمها مش مسجلة في أي مكان**. متطلبهاش تاني منه؛ لو مفتاح اتحتاج، اعرض رابط الـ secure capture الأول (connector `custom.narto-drama`).
- **الـ keystore وكلمة سره:** مكانهم في §3. **متترفعش أبداً على GitHub ولا تدخل في أي zip للمصدر.** نسخة احتياطية من cinereels keystore موجودة في `~/workspace/your_files/cinereels-apk/` — نفس القاعدة.
- **ملفات كلمات السر chmod 600.** متبعتش محتواها في أي تقرير أو شات.
- **الـ OTP/أكواد الجهاز:** كود جهاز GitHub بيتبعت على الجيميل كل مرة — يتجاب من الإيميل وقت الحاجة بس، وميتسجلش.
- **الـ WhatsApp/Vodafone رقم 201080482372** رقم تواصل تجاري عام (موجود أصلاً في `subscribers.json` على GitHub) — مش سرّي.

---

## 18. دليل صناعة الفيديو — للـ AI اللي هيعمل الحلقات

> **لمن هذا القسم:** آدم هيبعت الدليل ده لـ AI تاني (خدمة مختلفة) عشان يصنع الحلقات الحقيقية. القسم ده بيحدد **المطلوب تسليمه بالظبط** — مش بيشرح إزاي خدمة التوليد بتشتغل.

### مواصفات الفيديو المطلوبة

| البند | المطلوب |
|---|---|
| الصيغة | MP4 — فيديو H.264 + صوت AAC |
| المقاس المفضّل | **عمودي 720×1280 (9:16)** — هو الشكل الطبيعي للفيد (full-screen) |
| مقاس مقبول | أفقي 1280×720 — المشغّل بيعمل cover-fit (بيملا الشاشة وبيقصّ من الجناب)، بس العمودي أفضل |
| المدة | **10–90 ثانية للحلقة** (حلقات آدم الحالية 60 ثانية؛ الحلقات الجديدة يفضل 60–90 ثانية) |
| الصوت | **حوار عربي** (محتوى آدم دراما عربية) — صوت واضح، كلام مسموع، من غير موسيقى تغطي على الحوار |
| المحتوى | أصلي فقط — محتوى آدم أو مرخّص. **ممنوع** كليبات من أفلام/مسلسلات موجودة |

### التسمية والأماكن

- ملف الفيديو: `videos/episodeN.mp4` في ريبو `cinereels-videos` (مثال: `videos/episode6.mp4`).
- الثمبنيل: `thumbnails/epN.webp` (أو `.jpg`) بمقاس **720×1280** — صورة من المشهد نفسه، واضحة وجذابة.
- الترجمة: `subtitles/drama/episodeN_ar.vtt` + `subtitles/drama/episodeN_en.vtt` (شوف خطوات الترجمة في §7).

### قصة المسلسل (Story bible)

- **"The Last Message / الرسالة الأخيرة"** — دراما عائلية. السيناريو الكامل في `drama-series/SCRIPT_AR_EN.md` (اقرأه قبل صناعة أي حلقة): الشخصيات **ليلى** (البطلة)، **سارة** (الأخت اللي ليلى ماكانتش تعرفها)، **عمر**، **خالد**. القصة: ليلى بتستقبل رسالة صوتية من أمها المتوفاة مجدولة من سنة، وبتكتشف أسرار العيلة حلقة ورا حلقة، والنهاية بتشوّق للموسم التاني ("ماما سابت رسالة أخيرة… لعمر").
- عناوين الحلقات الـ 25 موجودة في `videos.json` (الحلقات 1–15 معمولة، 16–25 `coming_soon` — بتتبدل بفيديو حقيقي واحدة واحدة، بنفس الـ `id` والعنوان).
- **"A Second Chance / فرصة ثانية"** — مسلسل رومانسي منفصل (3 حلقات): مايا بترجع بلدها بعد خطوبة فاشلة وبتلاقي حبيبها القديم بيدير المقهى اللي كانت بتحلم بيه.

### خطوات عمل الترجمة لأي حلقة جديدة (نفس خطوات §7)

```bash
# 1) استخرج الصوت 16kHz mono من الفيديو
ffmpeg -y -v error -i episodeN.mp4 -vn -ac 1 -ar 16000 episodeN_audio.wav
ffprobe -v error -show_entries format=duration -of csv=p=0 episodeN.mp4   # المدة الحقيقية
# 2) فرّغ الصوت (whisper-tiny، عربي) — السكربت جاهز:
OMP_NUM_THREADS=1 ~/workspace/whisper-venv/bin/python \
    ~/workspace/your_files/cinereels/transcripts/run_transcribe.py
# (النتيجة JSON في transcripts/episodeN.json — السكربت بيحمّل الـ WAV بـ wave+NumPy
#  مباشرة لأن PyAV المثبت مكسور مع faster-whisper — متحاولش تصلح PyAV)
# 3) صحّح الإملاء يدوياً (whisper-tiny بيغلط في العامية المصرية).
#    لو مقطع مش واضح، اكتب أقرب صياغة ودوّن إنه غير مؤكد.
# 4) اكتب ملفين WebVTT بنفس التوقيتات (صيغة HH:MM:SS.mmm، كل التوقيتات داخل مدة الفيديو):
#    episodeN_ar.vtt = الكلام العربي كما قيل فعلاً
#    episodeN_en.vtt = الترجمة الإنجليزية لنفس الكلام
# 5) حدّث 3 أماكن بنفس المحتوى:
#    github-videos/subtitles/drama/ + github-videos/subtitles/ + cinereels-apk/assets/subtitles/
# 6) لو غيّرت duration/language/subtitle_default في videos.json، ادفع (§6.1).
```

### خطوات رفع حلقة جديدة (بالترتيب)

1. **ارفع الـ mp4 من المتصفح** (Add file → Upload files) إلى مجلد `videos/` في ريبو `cinereels-videos` — الملفات الـ binary مينفعش تترفع بـ `push-files`، لازم واجهة الويب. خد رابط الـ raw: `https://raw.githubusercontent.com/adam2211dmdm-ux/cinereels-videos/main/videos/episodeN.mp4`.
2. **ارفع الثمبنيل** بنفس الطريقة إلى `thumbnails/`.
3. **ضيف/حدّث الـ entry في `videos.json`** (لو الحلقة `coming_soon`، غيّر `coming_soon` لـ `false` واملأ الحقول دي):

   | الحقل | القيمة |
   |---|---|
   | `id` | `lm-ep6` (نفس الـ id الموجود للحلقة) |
   | `series_id` | `last-message` (أو `second-chance`) |
   | `episode_number` | رقم الحلقة |
   | `title_en` / `title_ar` | العنوان (موجود أصلاً في الـ placeholder — سيبه زي ما هو إلا لو آدم غيّره) |
   | `description_en` / `description_ar` | وصف قصير للحلقة |
   | `category` | `drama` (أو `romance` للمسلسل التاني) |
   | `duration_sec` | **المدة الحقيقية من `ffprobe`** — مش تقدير |
   | `language` | `"en"` (الصوت إنجليزي لحلقات The Last Message) أو `"ar"` |
   | `subtitle_default` | `"ar"` (العربي هي الترجمة المعروضة افتراضياً) |
   | `video_url` / `thumbnail_url` | روابط الـ raw اللي من الخطوتين 1 و2 |
   | `subtitles_ar_url` / `subtitles_en_url` | `.../main/subtitles/drama/episodeN_ar.vtt` (نفس النمط) |
   | `views` / `likes_count` | 0 لحلقة جديدة |
   | `is_published` | `true` — `coming_soon` → `false` |

4. **ادفع `videos.json` + ملفات الـ `.vtt`** بـ `github push-files` (§6.1 — ملفات نصية بس).
5. **اتأكد بـ curl** إن الـ manifest الحي اتغير (§6.1).
6. **حدّث الـ APK المضمّن لو لزم:** انسخ `videos.json` الجديد إلى `cinereels-apk/assets/videos.json` + الترجمات إلى `assets/subtitles/`، ابنِ من جديد (`./build.sh` — نفس رقم النسخة لو مفيش تغيير كود)، وارفع الـ APK لصفحة التحميل (§5).

### تنبيه مهم عن توليد الفيديو

- **توليد الفيديو بالـ AI محظور على حساب آدم الحالي في Muse** (403 — قيود دولة/منطقة، دائم، 5 محاولات فاشلة 2026-11-22) — **لا تحاول من الحساب ده بأي طريقة.**
- الـ AI اللي هيصنع الحلقات ده **خدمة تانية مختلفة** — الدليل ده بيحدد المطلوب تسليمه (المواصفات + القصة + التسمية + الرفع)، مش بيشرح إزاي خدمة التوليد دي بتشتغل.

---

## 19. أوامر سريعة (Cheat sheet)

```bash
# بناء
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
- **حدّث هذا الملف** كل ما حالة المشروع تتغير (نسخة جديدة، عيب جديد، قرار جديد من آدم) — هو دليل حي، مش أرشيف.

*آخر تحديث: 2026-11-24 ~11:00 EET — CineReels فقط (بطلب آدم). v1.26 DELIVERED والرابط اتبعت لآدم 10:45 EET (HTTP 200، 1,300,586 بايت، MD5 `193bae916eb49fba07274300ff3d9ba3`، manifest commit `3ed4f7b`، APK commit `e41ef07`)، manifest حي 198 فيديو / 5 مسلسلات، عيب 38/52 معروف ومبلّغ بيه، قسم التشفير الكامل مضاف (§12).*
