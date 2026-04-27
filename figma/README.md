# Figma UI 稿对照图片目录

原型 HTML（`../VIP电投_原型_v0.html`）右下角 **📐 对照 UI 稿** 按钮打开后，会读取这个目录下的 PNG，跟随当前页面自动切换。

## 怎么用

1. 在 Figma Dev Mode 里选中一个 frame
2. 右键 → Copy/Paste as → Copy as PNG（或 Export → PNG 2x）
3. 按下表的文件名保存到这个目录
4. 刷新原型 HTML，点开对照面板即可看到

## 文件名映射（**必须精确匹配**，否则显示空态提示）

| 原型模块 | 文件名 | 对应变更清单 |
|---|---|---|
| G4 首屏加载页 | `g4-loading.png` | §G4 |
| M1 登录页 | `m1-login.png` | L1–L12 |
| M3 游戏大厅 | `m3-hall.png` | H1–H14 |
| M4 单桌投注 | `m4-bet.png` | B1–B16、MB1–MB10 |
| M5 多桌投注 | `m5-multi.png` | 参见 M5 章节 |
| B16 系统设置抽屉 | `b16-settings.png` | C1–C12 |
| C7 筹码选择器（抽屉内 → dialog） | `c7-chip.png` | C7 |
| C9 音乐设置（抽屉内 → dialog） | `c9-music.png` | C9 |
| C12 好路推荐设置（抽屉内 → dialog） | `c12-road.png` | C12 |
| B16.3 轮播广告设置（二级页） | `b16.3-ad.png` | B16.3 |
| B16.7 安全中心（二级页） | `b16.7-security.png` | B16.7 |

## 命名原则

- 全小写
- 模块号开头（m1/m3/m4/m5/b16/c7/c9/c12/b16.3/b16.7）
- 横杠分隔（如 `b16.3-ad.png`）
- 扩展名 `.png`（也支持 `.jpg` / `.webp`，但代码里默认取 `.png`，用别的格式记得改 `figmaMap[key].file`）

## 缓存处理

HTML 会在图片 URL 后拼 `?t=<timestamp>`，每次打开面板都会强制重载；所以**替换图片后刷新一次就生效**，不用清缓存。

## 尺寸建议

面板宽度 500px（内容区约 476px）。UI 稿导出建议 2x（宽度 780px 或原稿 390px 的 2 倍），显示清晰且文件不会太大。
