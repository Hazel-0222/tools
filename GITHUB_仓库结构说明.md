# GitHub 仓库结构说明

> 此文档记录 Hazel-0222 的 GitHub 账号、仓库结构及上传操作，避免后续重复查询确认。

---

## 一、GitHub 账号

| 项目 | 值 |
|------|-----|
| 用户名 | Hazel-0222 |
| 主页 | https://github.com/Hazel-0222 |
| Pages 地址 | https://hazel-0222.github.io |

---

## 二、仓库列表

| 仓库 | 本地路径 | 用途 |
|------|----------|------|
| `tools` | `F:\1-Projects\python工具合集` | 在线工具合集（GitHub Pages 子路径） |
| `hazel-0222.github.io` | `D:\Users\BBGame\Desktop\hazel-0222.github.io` | 个人主页 + 博客 |

---

## 三、tools 仓库结构

```
tools/
├── index.html              ← 工具合集首页
├── README.md               ← 项目说明
├── .gitignore              ← 忽略规则
├── word/
│   ├── word-extract-images/
│   │   └── index.html      ← Word 图片提取
│   └── word-diff/
│       └── index.html      ← Word 差异对比
├── excel/
│   ├── excel-add-toc/
│   │   └── index.html      ← Excel 目录生成
│   └── excel-diff/
│       └── index.html      ← Excel 差异对比
└── image/
    └── image-stitch/
        └── index.html      ← 图片拼接
```

### 线上访问地址

| 页面 | URL |
|------|-----|
| 工具合集首页 | https://hazel-0222.github.io/tools/ |
| Word 图片提取 | https://hazel-0222.github.io/tools/word/word-extract-images/ |
| Word 差异对比 | https://hazel-0222.github.io/tools/word/word-diff/ |
| Excel 目录生成 | https://hazel-0222.github.io/tools/excel/excel-add-toc/ |
| Excel 差异对比 | https://hazel-0222.github.io/tools/excel/excel-diff/ |
| 图片拼接 | https://hazel-0222.github.io/tools/image/image-stitch/ |

---

## 四、hazel-0222.github.io 仓库结构

```
hazel-0222.github.io/
├── index.html             ← 个人主页（工具、文章、关于）
├── post.html              ← 文章详情页（Markdown 渲染）
├── posts.json             ← 文章元数据列表
└── posts/
    └── hello-world.md     ← 示例文章
```

### 线上访问地址

| 页面 | URL |
|------|-----|
| 个人主页 | https://hazel-0222.github.io |
| 文章详情 | https://hazel-0222.github.io/post.html?slug=hello-world |

---

## 五、提交和推送命令

### tools 仓库

```powershell
cd "F:\1-Projects\python工具合集"
git status
git add <文件或文件夹>
git commit -m "提交说明"
git push origin main
```

### 主页仓库

```powershell
cd "D:\Users\BBGame\Desktop\hazel-0222.github.io"
git status
git add <文件或文件夹>
git commit -m "提交说明"
git push origin main
```

---

## 六、已删除的旧仓库

以下仓库已合并到 `tools`，不再单独维护：

| 旧仓库 | 内容 | 去向 |
|--------|------|------|
| `word-tools` | Word 图片提取 | → `tools/word/word-extract-images/` |
| `image-stitch` | 图片拼接 | → `tools/image/image-stitch/` |

---

## 七、文件命名规范（参考 UI 规范）

### 对比工具导出命名

```
{YYYYMMDD}_{新文件名}_Diff.docx
```

| 示例 | 说明 |
|------|------|
| `20260810_策划案v2.0_Diff.docx` | 策划案 v1.0 vs v2.0 |

### 其他规范

详见 `UI规范_tkinterdnd2界面偏好.md` 第十二节。

---

## 八、技术栈

- 纯静态 HTML，GitHub Pages 托管
- JSZip：解析/生成 .docx 和 .xlsx
- SheetJS (xlsx)：Excel 解析
- diff：文本差异对比
- marked.js：Markdown 渲染
- GitHub API：头像动态获取
- 明暗主题：CSS `prefers-color-scheme` 自动切换