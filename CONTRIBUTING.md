# Contributing to GRASS tutorials

We welcome various contributions — fixing a typo, improving clarity, or adding a new tutorial.  
Not sure where to begin? [Open an issue](https://github.com/OSGeo/grass-tutorials/issues) to start a conversation.

---

## Getting started

1. **Fork and clone** the repository. Then follow the
[GitHub guide](https://grass.osgeo.org/grass-devel/manuals/github_guide.html) for the GRASS repository and adjust the workflow for this repository.

2. **Install Quarto** (if you haven’t already), see <https://quarto.org/docs/get-started/>

3. **Preview the site locally:**

    ```sh
    quarto preview
    ```

    This launches a local server and opens a live preview in your browser.

4. **Create or edit tutorials:**

    Tutorials are written in Markdown (.qmd) with YAML front matter.

    Add your tutorial to the appropriate section (e.g., ./content/tutorials/mytutorials).

## Writing a tutorial

Give your audience some context, for example include what topics does
the tutorial cover, what are the prerequisites, and so on.

Use Quarto's [guide](https://quarto.org/docs/guide/) to learn how to write
Quarto documents and learn [Markdown syntax](https://quarto.org/docs/authoring/markdown-basics.html).

For example, include GRASS commands in fenced code blocks:

```` markdown
```{python}
gs.run_command("g.region", raster="elevation")
```
````

You can use [tabsets](https://quarto.org/docs/output-formats/html-basics.html#tabsets)
to show how to run GRASS commands in command line and in Python:

```` markdown
::: {.panel-tabset group="language"}

## Command line

```{bash}
g.region raster=elevation
```

## Python

```{python}
gs.run_command("g.region", raster="elevation")
```

:::
````

Display notes:

``` markdown
::: {.callout-note title="Setup"}  
To run this tutorial locally ...  
:::
```

## YAML metadata example

Each tutorial must begin with YAML metadata like this:

```` yaml
---
title: "Computing slope from elevation data in Python"
author: "Your Name"
date: "2025-05-15"
description: "Learn how to derive slope from elevation data in GRASS in a Jupyter Notebook."
categories: ["beginner", "geomorphometry", Python]
thumbnail: slope_thumbnail.webp
format:
  ipynb: default
  html:
    toc: true
    code-tools: true
    code-copy: true
    code-fold: false
engine: jupyter
execute:
  eval: false
jupyter: python3
---

````

Notes:

- Use appropriate categories (tags), include whether the tutorial is for *beginner*, *intermediate*, or *advanced* users.

- Use `eval: false` so that Quarto doesn't run the code during building of the website.

- Specifying format `ipynb: default` will create a Jupyter notebook during the build process and link it from the tutorial page.

## Images

Beautiful images and graphics make tutorials stand out!
Make sure the images have *sufficient resolution*.
At the same time, their size should not be too big to load quickly, try to keep it under 200 KB or so. We recommend using *webp* format.

``` markdown
![Slope map](slope.webp)
```

Each tutorial needs to have at least one image that can be used on the main page as a thumbnail.
You can either specify it in the YAML header (`thumbnail: image.webp`) or add `{.preview-image}` to the image.

``` markdown
![Slope map](slope.webp){.preview-image}
```

## Submitting your contribution

Check your markdown with a [linter](https://dlaa.me/markdownlint/) and fix as many issues as you can. This will help keeping the tutorials consistent.

Follow the [GitHub guide](https://grass.osgeo.org/grass-devel/manuals/github_guide.html)
(adapt it to this repo) to submit your tutorial.
You should **only commit the .qmd file and images**. 
Once you sumbmit a PR, the CI pipeline will build your
tutorial, so you and a reviewer can check if everything is ok.
When a reviewer approves, your PR will be merged soon.

---
Thanks for helping us build better educational resources for the GRASS community!
