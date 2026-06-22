# Lingkai Zhang Academic Homepage

This is a static personal academic homepage for Lingkai (Lyncai) Zhang 张凌恺. It is designed for GitHub Pages and does not require a frontend build step.

中文维护说明见 [`维护说明书.md`](维护说明书.md)。

## Files

- `index.html`: page structure.
- `styles.css`: layout, visual style, responsive rules, and font settings.
- `script.js`: bilingual content, news, timeline entries, research interests, publications, working papers, note entries, and the animated background.
- `assets/avatar.jpg`: profile photo.
- `assets/wechat-qrcode.jpg`: WeChat public account QR code.
- `assets/papers/`: PDF files linked from the publication cards.
- `assets/paper-thumbs/`: publication thumbnail images shown on the left side of each publication card.

## Content Editing

Most editable content is in `script.js`:

- `content.en` and `content.zh`: navigation, profile, hero text, section headings, and contact text.
- `data.en.status` and `data.zh.status`: doctoral progress and training status.
- `data.en.news` and `data.zh.news`: recent updates. The homepage shows the first three by default.
- `data.en.topics` and `data.zh.topics`: research interests.
- `data.en.publications` and `data.zh.publications`: publication cards, contribution statements, and PDF links.
- `data.en.workingPapers` and `data.zh.workingPapers`: ongoing working paper titles.
- `data.en.posts` and `data.zh.posts`: research note placeholders.

The page defaults to English and provides a Chinese switch. Chinese names and Chinese publication titles are preserved for accurate identification.

## Replacing Publication Images

Each publication card shows a thumbnail from `assets/paper-thumbs/`. By default, the thumbnail file name matches the PDF file name:

```text
assets/papers/2026-basic-research-high-quality-patents.pdf
assets/paper-thumbs/2026-basic-research-high-quality-patents.jpg
```

To replace a publication image, export or prepare a new `.jpg` image and overwrite the matching file in `assets/paper-thumbs/`.

If you want one paper to use a completely different image path, add an `image` field to that publication item in `script.js`, then update `publicationThumb()` to read that field first.

## Fonts

The site forces English text to use Times New Roman. Chinese text attempts to use local Tencent font names first:

```css
--font-en: "Times New Roman", Times, serif;
--font-zh: "TencentSans", "Tencent Sans", "TencentFont", "Tencent Font", "腾讯体",
  "Microsoft YaHei", "PingFang SC", "Noto Sans SC", sans-serif;
```

If a Tencent font is not installed on the viewer's device, the browser falls back to common Chinese system fonts.

## Local Preview

```powershell
cd D:\codex_page
python -m http.server 8000
```

Open:

```text
http://127.0.0.1:8000
```

## GitHub Pages Deployment

Create a public GitHub repository named:

```text
LyncaiZhang.github.io
```

Upload all files in this folder to the repository root. Then open GitHub:

```text
Settings -> Pages -> Deploy from a branch -> main / root
```

The homepage will be available at:

```text
https://LyncaiZhang.github.io
```

No custom domain is required at this stage. A custom domain can be added later after the site content stabilizes.
