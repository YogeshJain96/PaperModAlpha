## PaperModAlpha

PaperModAlpha is a [Hugo](https://gohugo.io/) theme based on theme [hugo-PaperMod](https://github.com/adityatelange/hugo-PaperMod). I wanted to add more features and customization to the original theme as required for my personal site, I decided to maintain my own fork (I didn't want to keep overwriting a bunch of files as a fork workflow is much cleaner).

---

### Custom changes with PaperModAlpha 🚀

- Support to float Table of Content box to right or left (it only shows on the side when minimum screen size is 1440px)

```yaml
params:
  TocSide: 'right'  # or 'left'
```

---

### Getting Started 🚀

1. Follow **[Hugo Docs's - Quick Start](https://gohugo.io/getting-started/quick-start/)** guide to install Hugo.
   <br>(Make sure you install **Hugo >= v0.112.4**)

2. Create a new Hugo site
   ```sh
   hugo new site MyNewSite --format yaml
   # replace MyNewSite with name of your website
   ```
   Note:
   - Older versions of Hugo may not support `--format yaml`
   - Read more here about [Hugo Docs's - hugo new site command](https://gohugo.io/commands/hugo_new_site/#synopsis)

After you have created a new site, follow the below steps to add **PaperModAlpha**

#### Installing/Updating PaperModAlpha

- Themes reside in `MyNewSite/themes` directory.
- PaperMod will be installed in `MyNewSite/themes/PaperModAlpha`

> <details>
> <summary><b>Expand Method 1 - Git Clone</b></summary>
>
> **INSTALL** : Inside the folder of your Hugo site `MyNewSite`, run:
>
> ```bash
> git clone https://github.com/yogeshjain96/PaperModAlpha themes/PaperModAlpha --depth=1
> ```
>
> **UPDATE**: Inside the folder of your Hugo site `MyNewSite`, run:
>
> ```bash
> cd themes/PaperMod
> git pull
> ```
>
> </details>

<br>

> <details>
> <summary><b>Expand Method 2 - Git Submodule (recomended)</b></summary>
>
> **INSTALL** : Inside the folder of your Hugo site `MyNewSite`, run:
>
> ```bash
> git submodule add --depth=1 https://github.com/yogeshjain96/PaperModAlpha.git themes/PaperModAlpha
> git submodule update --init --recursive # needed when you reclone your repo (submodules may not get cloned automatically)
> ```
>
> You may use ` --branch v7.0` to end of above command if you want to stick to specific release.
> Read more about git submodules [here](https://www.atlassian.com/git/tutorials/git-submodule).
>
> **UPDATE**: Inside the folder of your Hugo site `MyNewSite`, run:
>
> ```bash
> git submodule update --remote --merge
> ```
>
> </details>

<br>

#### Finally set theme as PaperModAlpha in your site config

In `config.yml` add:

```yml {linenos=true}
theme: ["PaperModAlpha"]
```

#### Next up - Customizing PaperMod to suit your preferences.

As PaperModAlpha is a custom version of PaperMod theme, existing doc version is still valid.
Documentation of PaperMod theme can be found here: [**📚 Wiki**](https://github.com/adityatelange/hugo-PaperMod/wiki)

## [Pagespeed Insights](https://pagespeed.web.dev/report?url=https://curiousone.in) 👀

---

### Support 🫶

-   Star 🌟 this repository.
-   Help spread the word about PaperModAlpha by sharing it on social media and recommending it to your friends. 🗣️

---
