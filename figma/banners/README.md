# 大厅 Banner 图片目录

原型 HTML 点击赌厅 Tab 时会**自动切换 Banner 图片**（非自动轮播）。逻辑：`pickTab()` → `#banner-img.src = 'figma/banners/<file>.png'`。

## 需要放的图片

按下表把 Banner 图片按**精确文件名**放到本目录：

| 对应 Tab | 文件名 | 图片来源 |
|---|---|---|
| 全部赌场（默认） | `banner-all.png` | 可以用 Newport 或 4 家合成图 |
| Newport | `banner-newport.png` | Newport World Resorts 狮子喷水城市夜景 |
| ONEKEY | `banner-onekey.png` | Casino ONEKEY Banner |
| CAGAYAN | `banner-cagayan.png` | Cagayan Holiday & Leisure Resort |
| Solaire | `banner-solaire.png` | Solaire Resort Entertainment |

## 尺寸建议

- 宽高比 **≈ 374×97**（大厅 Banner 容器尺寸）
- 2x 导出即 **748×194**（保证 Retina 清晰）
- PNG 或 JPG 都可（代码里默认 `.png`）

## Fallback 行为

若图片不存在（404），img 自动 `.hide` 类 + 背景渐变露出 + 显示文字 fallback：如"NEWPORT WORLD RESORTS · 广告位"。

## 文件名匹配规则（在 HTML `bannerMap` 里）

```javascript
const bannerMap = {
  '全部赌场': { file:'banner-all.png',      text:'...' },
  'Newport':  { file:'banner-newport.png',  text:'...' },
  'ONEKEY':   { file:'banner-onekey.png',   text:'...' },
  'CAGAYAN':  { file:'banner-cagayan.png',  text:'...' },
  'Solaire':  { file:'banner-solaire.png',  text:'...' },
};
```

如果要改映射或文件名，改 `VIP电投_原型_v0.html` 里的 `bannerMap`。
