# 计数器

受 [当然我在扯淡](https://www.yinwang.org/) 风格启发的简明 Hugo 主题。

[English translation](https://github.com/tokenicrat/hugo-theme-counter/blob/main/README_en.md)

## 快速开始

在已有的 Hugo 站点下执行：

```bash
git clone https://github.com/tokenicrat/hugo-theme-counter.git themes/counter
```

然后在 `hugo.yaml` 修改：

```yaml
theme: counter
```

## 配置

在 `hugo.yaml` 中添加：

```yaml
taxonomies:
  topic: topics # 相当于 tag

params:
  titleImage: "/title.png" # 左上角标题图片，建议背景透明
  favicon: "/favicon.png" # 网站图标
  menu: # 菜单
    - name: "❓ 关于"
      url: "/about"
    - name: "🚏 话题"
      url: "/topics"
    - name: "🔭 总览"
      url: "/archives"
  footer: true # 是否显示页脚
```

### 内容组织

本主题采用比较特殊的内容组织形式：

- 首页显示分组（博客组），也就是在 `content` 下各目录：
  
  ```
  content
  |- books
     |- _index.md # 在此设置博客组标题
  |- movies
     |- _index.md
     |- forrest_gump.md
  ```
  
  在 `_index.md` 中可以自定义标题、总结文本和分类页面正文：

  ```markdown
  ---
  title: 书籍
  summary: 我喜欢的书籍
  ---

  本分类的一些介绍。
  ```
- 按时间排序的档案（总览）在 `/archives`，同样可以在 `content/archives/_index.md` 中自定义
- 标签（话题）在 `/topics`，在 `content/topics/<TOPIC_NAME>/_index.md` 自定义

此外，首页信息在 `content/_index.md` 自定义。

### 额外配置

本主题比较粗糙，某些设置需要您进入主题目录自行修改。

- `themes/counter/layouts/partials/comment.html`：评论插件，将 HTML 直接粘贴即可
- `.../footer.html`：页脚
- `.../head.html`：KaTeX 支持，不需要可以删除
  如果希望在某则博客中使用，在 front matter 中添加 `katex: true`

由于作者 CSS 不好，写得很短，很多地方沿用默认值，颜色可能选得也比较丑，请自行修改。

## 排错

如果在构建站点时，Hugo 提示您版本过低，那是因为作者懒，在 `theme.toml` 里把最小版本设成了 `0.148.1`。大概率您的旧版本 Hugo 也能用，直接改掉就好。

## 协议

The Unlicense
