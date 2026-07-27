# كيف الضيافة — أرشيف الميديا / Keif Al-Diyafa Media Archive

أرشيف ميديا مشروع **كيف الضيافة** — من مصدرين: قروب تيليجرام `🏛️ كيف الضيافة — الأرشيف` + صور موقع المشروع (`kaif-v3`).

## 📊 الإحصائيات / Stats

| البند | العدد |
|---|---|
| **إجمالي الملفات** | **541** |
| فيديو | 137 |
| صور موقع (webp/svg/png) | **393** |
| صور تيليجرام | 8 |
| صوتيات | 3 |
| الحجم الكلي | **327 MB** |
| مدة الفيديو الكلية | **17 دقيقة** (1025 ثانية) |

## 📂 البنية / Structure

```
videos/        134 مقطع من موضوع "فديوهات ومحتوى ميديا"
photos/          6 صور من نفس الموضوع
client-notes/    8 ملفات من موضوع "ملاحظات العميل"
                 (3 صوتيات + 3 فيديو + 2 صور)
site-images/   393 صورة من موقع كيف الضيافة، مرتّبة بفئات:
                 events/ partners/ equipment/ weddings/ sweets/
                 dates/ nuts/ fruits/ snacks/ hot-drinks/ cold-drinks/
                 sandwiches/ pastry/ serving-equipment/ distributions/
                 hero/ badges/ watermarks/ services/…
index.json     فهرس كامل بروابط مباشرة + بيانات وصفية
```

### فئات صور الموقع الكبرى

| الفئة | العدد |
|---|---|
| `events/` | 82 |
| `partners/` | 67 |
| `equipment/` | 28 |
| `weddings/` | 18 |
| `sweets/` | 14 |
| `dates/` | 12 |
| `services/**` | ~90 (رجالية/نسائية/فنية) |

## 🏷️ التسمية / Naming

`{رقم_الموضوع}_{رقم_الرسالة}.{الامتداد}` — مثال: `20_0021.mp4`

- `20_` = موضوع "فديوهات ومحتوى ميديا"
- `02_` = موضوع "ملاحظات العميل"

## 🤖 للوكلاء الآليين / For AI Agents

ابدأ من ملف الفهرس الواحد — فيه كل شيء:

```
https://raw.githubusercontent.com/moain2026/keif-aldiyafa-media/main/index.json
```

### شكل الفهرس / Index schema

```json
{
  "project": "كيف الضيافة — أرشيف الميديا",
  "base_url": "https://raw.githubusercontent.com/moain2026/keif-aldiyafa-media/main/",
  "totals": { "files": 541, "videos": 137, "photos": 8, "audio": 3,
              "site_images": 393, "total_mb": 326.9,
              "total_video_seconds": 1025 },
  "sources": { "telegram": "...", "website": "..." },
  "site_image_categories": { "events": 82, "partners": 67, "...": 0 },
  "files": [
    {
      "source": "telegram",
      "topic": 20,
      "telegram_topic": "فديوهات ومحتوى ميديا",
      "msg_id": 21,
      "file": "videos/20_0021.mp4",
      "url": "https://raw.githubusercontent.com/.../videos/20_0021.mp4",
      "kind": "video",
      "duration": 6.7,
      "res": "1280x720",
      "bytes": 2415003,
      "date": "2026-07-27T00:01:47+00:00"
    },
    {
      "source": "website",
      "category": "events",
      "file": "site-images/events/xxx.webp",
      "url": "https://raw.githubusercontent.com/.../site-images/events/xxx.webp",
      "kind": "image",
      "ext": "webp",
      "bytes": 84213
    }
  ]
}
```

فلترة بالمصدر: `source == "telegram"` أو `source == "website"`.
فلترة صور الموقع بالفئة: `category == "events"`.

كل ملف فيه `url` مباشر — لا يحتاج مصادقة، حمّله بـ `curl`/`wget` مباشرة.

### مثال / Example

```bash
curl -s https://raw.githubusercontent.com/moain2026/keif-aldiyafa-media/main/index.json \
  | python3 -c "import json,sys; d=json.load(sys.stdin); print(len(d['files']))"
```

## 📐 المواصفات التقنية / Specs

**الفيديو:** `video/mp4`
- 99 مقطع أفقي `1280x720`
- 34 مقطع عمودي `480x848` (ريلز/شورتس)
- ملاحظات العميل عمودية `576x1024`
- المدد: 0.8 – 60 ثانية (المتوسط ~5.7 ث)
- أكبر ملف: 9.8 MB

**الصوت:** `audio/ogg` (رسائل صوتية: 16 / 30 / 40 ثانية)

**الصور:** تيليجرام `image/jpeg` · الموقع 388 `webp` + 11 `svg` + 6 `png` + 2 `jpg`

## ⚠️ ملاحظة / Note

المقاطع في `videos/` **بدون أوصاف نصية** — أرشيف خام مرفوع بألبومات. الترتيب حسب رقم الرسالة يوافق ترتيب الرفع الأصلي.

---

*مُصدَّر آلياً من تيليجرام عبر MTProto — 2026-07-26*
