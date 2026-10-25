# LiteCrop · 图片裁剪

**单文件 · 零依赖 · 纯浏览器本地处理** 的图片裁剪工具。双击 `index.html` 即用，图片永远不会被上传到任何服务器。

[中文文档](README.zh-CN.md) | Live demo: open `index.html` in any modern browser.

## ✨ Features

- **Aspect ratio presets** — Free, 16:9, 16:10, 4:3, 3:4, 9:16, 1:1. Lock a ratio and every handle keeps it.
- **Precise control** — 8 resize handles (corners + edges), drag inside the box to move, drag outside to pan, wheel/slider zoom anchored at the cursor, rule-of-thirds guides, live output size badge.
- **Full-resolution export** — cropping samples from the **original image**, so preview zoom never affects output quality.
- **PNG / JPG** — lossless PNG with transparency, or JPG with an adjustable quality slider (50–100%).
- **Input** — click to pick, drag & drop, or paste (Ctrl+V).
- **Zero upload, zero dependency** — one HTML file, no build step, no CDN, works offline. Automatic dark mode via `prefers-color-scheme`.

## 🚀 Usage

No installation. Three ways to run:

1. **Double-click** `index.html` — that's it.
2. Serve it locally: `npx serve .` or `python -m http.server`
3. Drop the file on any static host (GitHub Pages / Gitee Pages / your server).

## 🧠 How it works

The crop box is stored in **image natural coordinates** (`x/y/w/h`); the display transform is simply `natural × scale + pan`. On export, the region is sampled from the source image with `drawImage`, so a 4000px-wide photo exports at full resolution even if the preview is zoomed out.

Pointer events are batched with `requestAnimationFrame` (capped at display refresh) and flushed on `pointerup`, so even 1000Hz-gaming-mice drags stay smooth — no jank, no lost tail.

## 📁 Project

```
lite-crop/
├── index.html       # the entire app (HTML + CSS + JS, ~0 dependency)
├── README.md        # English doc
├── README.zh-CN.md  # 中文文档
└── LICENSE          # MIT
```

## 📄 License

[MIT](LICENSE) — free for personal and commercial use.
