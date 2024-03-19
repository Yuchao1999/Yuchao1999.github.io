+++
title = "Hugo notes"
description = "Hugo manual."
tags = [
    "Hugo",
    "Basic Command",
    "Development",
]
date = "2024-02-25"
categories = [
    "Hugo",
]

+++


**[Hugo official website](https://gohugo.io/)**

Hugo, written in `Go`,  is a kind of static site generator which is fast and user-friendly. Websites built with Hugo are extremely fast and secure.



## Before Hugo

1. Create a new repository in your github. 

   {{<hint info>}}

   Repository name mast be the <u>\[username\].github.io</u>

   {{</hint>}}

2. Config your github pages.



## Hugo directory structrue

```markdown
-->yourBlogRoot/ (Blog Root)
    -->archetypes/
    -->assets/
    -->content/	# markdown files get turned into online pages, posts, etc
    -->data/
    -->i18n/
    -->layouts/	# html templates provide structure
    -->public/
    -->resources/
    -->static/	# images, css, js files available at site root
    -->themes/	# downloaded themes
    -->config.toml	# hugo configuration settings
```



## Hugo basic commands

1. Create a hugo directory to store all the source files and configurations , then get into the root directory:

   ```markdown
   hugo new site myBlog
   cd myBlog
   ```

2. Create your contents. To build your site, run the following code:

   ```markdown
   hugo
   ```

​		The pubilc directory will be generated when  you run this command.

3. To view your site while developing layouts or creating contents, get into your root directory and run:

   ```markdown
   hugo server (use "hugo server --help" to see more operations)
   ```

4. Comparison with Hexo(other site generator), Hugo can't submit new contents to  `GitHub Pages` automatically. So that's our job.

   If you are the first time to develop Hugo using  `GitHub Pages`, run the following code:

   ```markdown 
   git init
   git remote add origin https://github.com/[GitHub username]/[GitHub username].github.io.git
   git add -A
   git commit -m "whaterver you want to introduce your repo"
   git push -u origin master
   ```

   If not, run the following code when you need to upload new contents:

   ```markdown
   git add -A
   git commit -m "Introduce this change"
   git push -u origin master
   ```

