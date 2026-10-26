# 菲欧妮攻略手册 · Phoenix Guide

《绝区零》3.3「重返天空的旅程」S 级火属性异常代理人 **菲欧妮·蕾法爱菈（Phoenix）** 的攻略站。

**线上地址** → https://kbybbb0721.github.io/fioni-guide/

---

## 内容

12 个页面，纯静态（无框架、无构建、无后端）：

| 页面 | 内容 |
| --- | --- |
| 首页速览 | 30 秒结论、核心机制三件事 |
| 一图流速查 | 音擎 / 驱动 / 词条 / 面板 / 配队 / 循环，一屏看完 |
| 技能与机制 | 涅槃、灼蚀、燔焰、升变、生竭、重明 |
| 音擎 / 驱动盘 / 养成与抽取 | 配置与材料 |
| 配队方案 | 丹欧维 / 欧维柚 / 无蕾米低配 |
| **连招教学** | 手残三层：LV1 保底 EAA、LV2 升变合轴、LV3 失衡爆发 |
| 视频合集 | B站播放器内嵌 + 原链接兜底 |
| 角色与剧情 | 人设与设定，不含主线剧透 |
| 常见问题 / 更新日志 | — |

## 部署结构

```
.github/workflows/deploy.yml   部署流水线（Actions → Pages）
fioni-guide-pages.zip          站点包（唯一需要替换的文件）
README.md
```

Pages 的 Source 是 **GitHub Actions**：流水线解压 zip → 上传 artifact → `actions/deploy-pages` 发布。

## 怎么更新

1. 替换根目录的 `fioni-guide-pages.zip`（网页 Upload files 覆盖，或本地 push）；
2. 提交后自动触发部署，也可在 `Actions → Deploy static site to GitHub Pages → Run workflow` 手动跑；
3. 改了页面内容，记得把 zip 里 `sw.js` 的 `CACHE` 版本号 +1，否则 Service Worker 会让老访客看到旧缓存。

流水线的 `cache` 任务会在仓库缺少 zip 时自动下载一份并提交回来，保证仓库自包含。

## 技术要点

- PWA：`manifest.webmanifest` + `sw.js`，预缓存全部页面与图片，可安装、可离线
- 版本提示：`version.json` 与页面内 `CURRENT_VERSION` 比对，同时监听 Service Worker 更新
- 无第三方脚本、无追踪；首页「阅读进度」只写 localStorage

## 来源

米游社 Asgater 系列（技能 / 音擎 / 驱动盘 / 配队 / 影画）、3DM 与 4399 整理转载、好游网操作讲解、B站 wiki 角色页、B站 UP 主手法视频、官方角色档案与物料。整理于 2026-10-26，对应 3.3 正式服。

## 版权

攻略内容为个人整理，欢迎参考。角色立绘与游戏画面版权归 miHoYo / HoYoverse；视频封面与视频版权归各 UP 主。公开传播或商用请自行确认授权。
