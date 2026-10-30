# 个人学术主页（academic-homepage）

基于 [luost26/academic-homepage](https://github.com/luost26/academic-homepage) 模板搭建的 Jekyll 个人学术主页，严格按照官方模板（https://luost.me/academic-homepage/ ）的结构制作，内容为蔺庆海（Qinghai Lin）老师的个人资料。

## 目录结构

```
.
├── _config.yml              # 站点配置（baseurl、collections）
├── _data/
│   ├── profile.yml          # 个人资料：姓名、单位、简介、教育/工作经历、荣誉、科研项目、专利、学术服务
│   ├── authors.yml          # 论文作者（需要加粗/加链接的作者才列在这里）
│   ├── navigation.yml       # 导航栏（Home / Layout2 / Publications / Blog / Showcase）
│   └── display.yml          # 首页各模块开关、页脚文案
├── _publications/           # 论文（按年份分目录，每篇一个 .md）
├── _news/                   # 新闻/动态
├── _posts/                  # 博客文章（模板自带示例，可删除）
├── _showcase/               # 展示页卡片（模板自带示例，可删除）
├── _includes/               # 页面组件
├── _layouts/                # 页面布局
├── assets/                  # 样式、脚本、图片（头像在 assets/images/photos/portrait.jpg）
├── index.html               # 首页
├── index_layout2.html       # 首页第二种布局（模板自带）
├── publications.html        # 论文列表页
├── blog.html                # 博客页（模板自带）
├── showcase.html            # 展示页（模板自带）
└── 404.html                 # 404 页面
```

## 本地运行

1. 安装 Ruby 与 Jekyll（参考 https://jekyllrb.com/docs/installation/）。
2. 在项目根目录执行：

```bash
bundle install
bundle exec jekyll serve
```

3. 浏览器打开终端显示的地址（默认 http://127.0.0.1:4000）即可预览。

> 也可以直接双击项目根目录的 `preview.html` 快速查看首页效果（无需安装任何东西，但仅用于预览、需联网加载样式）。

## 如何改成你自己的内容

- **姓名 / 单位 / 邮箱 / 简介 / 教育 / 工作 / 荣誉 / 科研项目 / 专利 / 学术服务**：改 `_data/profile.yml`。
- **头像**：替换 `assets/images/photos/portrait.jpg`。
- **论文**：在 `_publications/` 下按年份新建 `.md` 文件，front matter 参考现有论文。
  - 作者标记：名字后加 `*` = 共同一作，加 `#` = 通讯作者，`*#` = 两者皆是。
- **新闻**：在 `_news/` 下新建 `.md` 文件。
- **页脚 / 首页模块开关**：改 `_data/display.yml`。
- **导航栏**：改 `_data/navigation.yml`（`name` 需与页面 front matter 的 `navbar_title` 一致）。

> 说明：首页在模板原有板块（About / Education / Experience / Honors & Awards / News / Selected Publications）之外，额外加了「主要科研项目 / 专利与著作 / 学术兼职与社会服务」三个自定义卡片（`_includes/widgets/list_card.html` 渲染），数据来自 `profile.yml` 的 `research_projects` / `patents` / `services`。不想要的话，删掉 `index.html` 里对应的三行 `{% include widgets/list_card.html ... %}` 即可。

## 部署到 GitHub Pages

1. 新建仓库，命名为 `<你的GitHub用户名>.github.io`，把本目录内容推上去。
2. 仓库 `Settings → Pages` 中，`Source` 选择 **GitHub Actions**。
3. 推送后，`.github/workflows/pages.yml` 会自动构建并部署，访问 `https://<你的GitHub用户名>.github.io` 即可看到网站。

> 说明：`_config.yml` 中 `baseurl` 已设为空，适配 `<用户名>.github.io` 这种根目录部署；若部署到项目仓库子路径，请改成对应的 `/仓库名`。

## 致谢

模板来自 [luost26/academic-homepage](https://github.com/luost26/academic-homepage)，特此感谢。
