# Blog

## Setup

Create a new blog from the terminal:

```shell
quarto create project blog .
```

This will create the scaffolding for a simple blog in the working directory.

Render and preview the blog:

```shell
quarto preview .
```

The blog preview will open in a new web browser. When files are edited and saved the preview is automatically updated.

The key files:

File                 | Description          |
---------------------|----------------------|
`_quarto.yml`        | Quarto project file  |
`index.qmd`          | Blog home page       |
`about.qmd`          | Blog about page      |
`posts/`             | Dir containing posts |
`posts/_metadata.yml`| Shared options       |
`styles.css`         | Custom CSS           |


Add `.gitignore`:

```
/.quarto/
/_site/
```

Commit: 

```
git add .
git commit -m "Initial commit"
```

Create `gh-pages` branch:

```
git checkout --orphan gh-pages
git reset --hard
git commit --allow-empty -m "Initialising gh-pages branch"
git push origin gh-pages
```

Modify the **Source** branch for the repository to `gh-pages`.

## Post

The header of a post could look like this:

```quarto
draft: true
freeze: true
title: "Post With Code"
description: "Post description"
author: "Fizz McPhee"
date: "5/22/2021"
date-modified: "5/23/2021"
categories:
    - news
    - code
    - analysis
---
```

Name it `index.qmd` and add it to a subdirecotry `XX_short-title` in `posts`. Drafts will only appear in preview. Posts with computational output should be freezed to avoid re-computation.


When ready run:
```shell
quarto publish gh-pages
```

Make sure that you are in main branch.


