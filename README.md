# كيف الضيافة — أرشيف الميديا / Keif Al-Diyafa Media Archive

أرشيف ميديا مشروع **كيف الضيافة**، مصدَّر من قروب تيليجرام `🏛️ كيف الضيافة — الأرشيف`.

## 📊 الإحصائيات / Stats

| البند | العدد |
|---|---|
| إجمالي الملفات | **148** |
| فيديو | **137** |
| صور | **8** |
| صوتيات | **3** |
| الحجم الكلي | **294 MB** |
| مدة الفيديو الكلية | **17 دقيقة** (1025 ثانية) |

## 📂 البنية / Structure

```
videos/        134 مقطع من موضوع "فديوهات ومحتوى ميديا"
photos/          6 صور من نفس الموضوع
client-notes/    8 ملفات من موضوع "ملاحظات العميل"
                 (3 صوتيات + 3 فيديو + 2 صور)
index.json     فهرس كامل بروابط مباشرة + بيانات وصفية
```

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
  "totals": { "files": 148, "videos": 137, "photos": 8, "audio": 3,
              "total_mb": 293.8, "total_video_seconds": 1025 },
  "files": [
    {
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
    }
  ]
}
```

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

**الصور:** `image/jpeg`

## ⚠️ ملاحظة / Note

المقاطع في `videos/` **بدون أوصاف نصية** — أرشيف خام مرفوع بألبومات. الترتيب حسب رقم الرسالة يوافق ترتيب الرفع الأصلي.

---

*مُصدَّر آلياً من تيليجرام عبر MTProto — 2026-07-26*
