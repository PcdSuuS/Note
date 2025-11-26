# 博客网站模板 note-template

## 功能 Features

- ✅ markdown
- ✅ katex & asciimath

## 使用 Usage

1. 编辑 `index.html`, 搜索双重花括号 `{{}}`，替换为实际内容
```html
<meta name="keywords" content="{{关键字}}">
<meta name="description" content="{{描述}}">
<meta name="author" content="{{作者}}">
<title>{{标题}}</title>

...

<div class="note-about">
  <div class="note-about-img g-flex-center">
    <img src="img/pikachu.png" alt="头像">
  </div>
  <div>{{作者}}</div>
  <div class="note-about-links">
    <a href="{{mailto:author@example.com}}" target="_blank">邮箱</a>・<a href="{{https://github.com}}" target="_blank">github</a>
  </div>
  <hr>
  <div class="note-about-links">
    友情链接:
    <ul>
      <li>{{朋友}} <a href="{{https://github.com}}" target="_blank">github</a>・<a href="{{https://bilibili.com}}" target="_blank">bilibili</a></li>
    </ul>
  </div>
  <div class="note-about-back"></div>
</div>
```
2. 打开 `math/` 或 `misc/` 目录, 编辑文章内容. 你也可以新建目录和文件.
   本框架采用 book - group - article 三级结构:
   - book: 一级目录, 如 `math/`, `misc/` 等;
   - group: 二级目录, 如 `analysis/`, `algebra/` 等;
   - article: markdown 文件, 如 `1.md`, `2.md` 等.

   > **⚠ 你的文章 (即 `.md` 文件) 必须放在二级目录中.**

3. 编辑 `js/toc.js`, 替换为实际内容. 注意 value 应该填写文件名, 但要省略 `.md` 后缀.
```js
export const toc = [
  {
    "value": "math",
    "label": "数学",
    "children": [
      {
        "value": "analysis",
        "label": "分析学",
        "children": [
          { "value": "1", "label": "数列极限", "date": "2025-09-16" },
          { "value": "2", "label": "函数极限", "date": "2025-10-28" },
        ],
      },
      {
        "value": "algebra",
        "label": "代数学",
        "children": [
          { "value": "1", "label": "矩阵", "date": "2025-09-16" },
          { "value": "2", "label": "行列式", "date": "2025-11-16" },
        ],
      },
    ],
  },
  {
    "value": "misc",
    "label": "杂谈",
    "children": [
      {
        "value": "life",
        "label": "生活",
        "children": [
          { "value": "1", "label": "2025年", "date": "2025-09-16" },
        ],
      },
    ],
  },
]
```