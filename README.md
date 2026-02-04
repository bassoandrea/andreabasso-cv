<div align="center">
<h1>andreabasso-cv</h1>

_The source behind my CV_

[![RenderCV](https://img.shields.io/badge/RenderCV-GitHub-blue?style=flat&logo=github)](https://github.com/rendercv/rendercv)
</div>

This repository contains the source files for my **Curriculum Vitae (CV)** in YAML format.

The idea is to manage the CV as code: edit the YAML data, generate PDFs, and customize themes in a reproducible and automated way.

---

## Enviroment

*RenderCV* can be used in two main ways:

1. **Docker (recommended for isolation)**

    Run *RenderCV* directly with:

    ```bash
    docker run --rm -v "$PWD":/work -w /work ghcr.io/rendercv/rendercv new "Your Name"
    ```
2. **Python/Pip**

    Install with:

    ```bash
    pip install "rendercv[full]"
    ```

    After installation, use the `rendercv` command from your terminal:

    ```bash
    rendercv new "Your Name"
    ```
---

## PowerShell Alias for *RenderCV*

To avoid typing the long `docker run ...` command each time, you can define a function alias:

```powershell
function rendercv {
    docker run --rm -v "${PWD}:/work" -w /work ghcr.io/rendercv/rendercv:v2.6 @args
}
```
> Note: Add this function to your PowerShell profile (`notepad $PROFILE`) to have it available in every session.

---

## Main Commands

- create a new CV
    ```powershell
    rendercv new "Your Name"
    ```
    Generates an initial YAML file for the CV in the current folder.

- render a CV
    ```powershell
    rendercv render "Your_Name_CV.yaml" -nomd -nohtml -nopng --watch
    ```
    Generates a PDF file of the CV from the YAML file.

- create a custom theme
    ```powershell
    rendercv create-theme customtheme
    ```
    Creates a folder with Typst templates to customize the CV theme.

---

