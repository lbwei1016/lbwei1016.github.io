---
layout: page
title: Github Page
tag: Github page
---

> Environment：Windows 10 with WSL (Ubuntu 20.04 LTS)<br>
> Theme: [lanyon](https://github.com/poole/lanyon) 

## Step I: Setup

1. `sudo apt install ruby ruby2.7-dev`

2. `gem install jekyll jekyll-gist jekyll-sitemap jekyll-seo-tag` 

   > [doc](https://github.com/poole/poole#usage)
3. `git clone git@github.com:lbwei1016/lanyon.git` 

4. `git remote add github.io [github.io repo url]` 

5. `git add . && git commit -m "init"` 

6. `git checkout gh-pages` 

7. `git branch --set-upstream-to=github.io gh-pages` 

8. `git push -u github.io gh-pages` 

## Step II: Deploy

1. 到 *github.io* repo，按下 Settings。![](../img/github.io.setting.png)

2. 右方選擇 *Pages*，然後變更 source 為 *gh-pages*。完成！![](../img/github.io.page.png)

## Step III: Play

> **Github** 部署網頁需要花一些時間，所以只有本地才能即時看到變更。
>
> * `jekyll serve`: run at `localhost:4000` 

1. 官方文件：[Jekyll setup](https://jekyllrb.com/docs/step-by-step/01-setup/) 

2. **Liquid** 

   * *Liquid* 語法不論在 `.html` 或 `.md` 都可以使用

3. **Layout / include**：事先定義模板方便重複使用

   * 兩者層級不同

4. **Post / Blogging**

   * 檔名必須為 *2022-06-21-example.md* 此格式

   * 可改為使用自定義 **Collections** 

     > *posts* 是預設的 collection

5. **Collections** 

   * 將頁面分類

   * e.g. 

     ```yaml
     # 指定 collections 路徑
     collections_dir: my_collections 
     collections:
         math:
            label: math
            # true，這個 collection 的 pages 才會存放至 _site/ 內
            output: true
         misc:
            label: misc
            output: true
     ```
   > * 指定路徑後，`_posts` 也必須移至該目錄下
   > * `_site/` 內的檔案就是實際在網頁上能看到的
   >   * [Jekyll: the _site folder](https://www.youtube.com/watch?v=C6H2U_ZA99o ) 

6. **Variables**

   * [Variables](https://jekyllrb.com/docs/variables/)

7. **MathJax**

   * [MathJax](https://alanduan.me/random/mathjax/)
