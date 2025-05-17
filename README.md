## PaperModAlpha

PaperModAlpha is a [Hugo](https://gohugo.io/) theme based on theme [hugo-PaperMod](https://github.com/adityatelange/hugo-PaperMod). I wanted to add more features and customization to the original theme as required for my personal site, I decided to maintain my own fork (I didn't want to keep overwriting a bunch of files as a fork workflow is much cleaner).

---

### Custom changes with PaperModAlpha 🚀

- Support to float Table of Content box to right or left (it only shows on the side when minimum screen size is 1440px)

  ```yaml
  params:
    TocSide: "right" # or 'left'
  ```

- Option to disable social icons in home info section

  ```yaml
  params:
    homeInfoParams:
      showSocialIcons: false # or 'true'
  ```

- Option to show list of dynamic tags/ topics in home info section

  ```yaml
  params:
    homeInfoParams:
      showTags: true # or 'false'
      tagsTitle: | # Optional, show any custom title if showTags is set to true
        example: `You can find blogs about:`
  ```

- Option to add animated wave icon in home info section title
  <img src="images/wave.svg" alt="wave">

  ```yaml
  params:
    homeInfoParams:
      showWaveIcon: true # or 'false'
  ```

- Option to show terminal window in home info section with support for custom query and response

  ```yaml
  params:
    homeInfoParams:
      showTerminalWindow: true # or 'false'
      terminalQuery: whoami # require showTerminalWindow to true
      terminalResponse: | # require showTerminalWindow to true
        Curious, Full Stack Developer
  ```

  <img src="images/terminal.svg" height=300 width=500 alt="terminal">

- Option to configure about page via config yaml

  ```yaml
  params:
    about:
      aboutInfo: |
        Hello, I’m Yogesh Jain 👋
      imageUrl: "images/profile.png" # optional
      imageTitle: Yogesh Jain # set's image title if imageUrl is set
      imageWidth: 250 # set's image width if imageUrl is set
      imageHeight: 250 # set's image width if imageUrl is set
      imageCaption: "Captured by [NA](#)" # set's image caption if imageUrl is set
      aboutInfo: |
        Hello, I’m Yogesh Jain 👋
      contactInfo: |
        You can reach out to me via email `contactemail[at]gmail[dot]com`
      showSocialIcons: true # or 'false'
  ```

  Configure the `layout` to `about` in markdown page

  ```shell
  ---
  title: "About Me"
  layout: "about"
  summary: "about page"
  ---
  ```

- Add support for timeline

  ```yaml
  params:
    timeline:
      - year: "2024"
        events:
          - |
            ### Experience
            Write Something!
      - year: "2018"
        events:
          - |
            #### Education
            `tag1` `tag2` `tag3`
            This is the first multi-line text entry.
            It spans multiple lines and supports markdown

            🔗[link-text](https://curiousone.in)
          - |
            #### Another Achivement
            And here is the another entry with
            additional lines.
            - abc
            - xyz
  ```

  Configure the `layout` to `timeline` in markdown page

  ```shell
  ---
  title: "My Timeline"
  layout: "timeline"
  summary: "My timeline page"
  ---
  ```

- Implemented a Sticky Horizontal Bar on the blog content page, positioned at the top during scrolling - This feature serves to visually represent the reader's progress, offering a dynamic indicator of how much content has been consumed

- Add support for automatic switching of image sources between light and dark modes by adding a class `toggleDarkMode` to image tags. JavaScript will append the `-dark` suffix to the image filename for dark mode and remove it for light mode. Ensure that dark mode images are named with the -dark suffix in the source path

  Example:

  ```html
  <!-- Light mode -->
  <img class="toggleDarkMode" src="my-image-path.jpg"/>
  ```

  ```html
  <!-- Dark mode -->
  <!-- Suffixed '-dark' to image name -->
  <img class="toggleDarkMode" src="my-image-path-dark.jpg"/>
  ```

- Add support for Image Slider using swiper.js

  Example:

  ```
  {{< slider >}}
  /images/your-image-dir/image-1.png|Image 1 Caption goes here
  /images/your-image-dir/image-2.png|Image 2 Caption goes here
  /images/your-image-dir/image-3.png|Image 3 Caption goes here
  /images/your-image-dir/image-4.png|Image 4 Caption goes here
  /images/your-image-dir/image-5.png|Image 5 Caption goes here
  {{< /slider >}}
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

[![hugo-papermod](https://img.shields.io/badge/Hugo--Themes-@PaperMod-blue)](https://themes.gohugo.io/themes/hugo-papermod/)
[![Minimum Hugo Version](https://img.shields.io/static/v1?label=min-HUGO-version&message=>=v0.146.0&color=blue&logo=hugo)](https://github.com/gohugoio/hugo/releases/tag/v0.146.0)
[![Discord](https://img.shields.io/discord/971046860317921340?label=Discord&logo=discord)](https://discord.gg/ahpmTvhVmp)
[![GitHub](https://img.shields.io/github/license/adityatelange/hugo-PaperMod)](https://github.com/adityatelange/hugo-PaperMod/blob/master/LICENSE)
![code-size](https://img.shields.io/github/languages/code-size/adityatelange/hugo-PaperMod)
[![X (formerly Twitter) URL](https://img.shields.io/badge/-Share%20on%20X-gray?style=flat&logo=x)](https://x.com/intent/tweet/?text=Checkout%20Hugo%20PaperMod%20%E2%9C%A8%0AA%20fast,%20clean,%20responsive%20Hugo%20theme.&url=https://github.com/adityatelange/hugo-PaperMod&hashtags=Hugo,PaperMod)

```yaml
theme: ["PaperModAlpha"]
```

#### Next - Customizing PaperModAlpha to suit your preferences

As PaperModAlpha is a custom version of PaperMod theme, existing doc version is still valid.
Documentation of PaperMod theme can be found here: [**📚 Wiki**](https://github.com/adityatelange/hugo-PaperMod/wiki)

Aditionally, following configs are also supported

```yaml
# theme: ["PaperModAlpha"]
params:
  TocSide: 'right'  # or 'left'
  homeInfoParams:
    showSocialIcons: false  # or 'true'
      showTags: true # or 'false'
      tagsTitle: | # Optional, show any custom title if showTags is set to true
        example: `You can find blogs about:`
      showWaveIcon: true # or 'false'
      showTerminalWindow: true # or 'false'
      terminalQuery: whoami # require showTerminalWindow to be true
      terminalResponse: | # require showTerminalWindow to be true
        Yogesh Jain
  about:
    aboutInfo: |
      Hello, I’m Yogesh Jain 👋
    imageUrl: "images/profile.png" # optional
    imageTitle: Yogesh Jain # set's image title if imageUrl is set
    imageWidth: 250 # set's image width if imageUrl is set
    imageHeight: 250 # set's image width if imageUrl is set
    imageCaption: "Captured by [NA](#)" # set's image caption if imageUrl is set
    aboutInfo: |
      Hello, I’m Yogesh Jain 👋
    contactInfo: |
      You can reach out to me via email `contactemail[at]gmail[dot]com`
    showSocialIcons: true # or 'false'
  timeline:
      - year: "2021"
        events:
        - |
          ### Experience
          Write Something!
      - year: "2022"
        events:
        - |
          #### Achivement
          `tag1` `tag2` `tag3`

          This is the first multi-line text entry.
          It spans multiple lines and supports markdown

          🔗[link-text](https://curiousone.in)

        - |
          #### Another Achivement

          And here is the another entry with
          additional lines.
          - abc
          - xyz
```

## [Pagespeed Insights](https://pagespeed.web.dev/report?url=https://curiousone.in) 👀

---

### Support 🫶

- Star 🌟 this repository.
- Help spread the word about PaperModAlpha by sharing it on social media and recommending it to your friends.

---
