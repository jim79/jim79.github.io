---
title: Resolve WileyNJDv5 LaTeX template compilation errors
permalink: /wileynjdv5-resolve-errors/
layout: single
---

# Configuration Guide: TeX Live 2022 & Wiley NJD v5 Template on Debian

This document outlines the step-by-step process of installing a manual, frozen version of **TeX Live 2022 (Medium Scheme)** on Debian, configuring **TeXstudio** to use it, and resolving template-specific dependency conflicts for the **WileyNJDv5** journal template.

---

## Part 1: Installing TeX Live 2022 (Medium Scheme)

Because Debian's default repositories install newer, active packages, TeX Live 2022 must be manually installed using the frozen historic archive from the TeX Users Group (TUG).

1. **Download and extract the 2022 historic installer:**
   ```bash
   cd /tmp
   wget https://ftp.math.utah.edu/pub/tex/historic/systems/texlive/2022/install-tl-unx.tar.gz
   tar -xzf install-tl-unx.tar.gz
   cd install-tl-2022*
   ```

2. **Run the installer pointing to the frozen 2022 repository:**
   ```bash
   sudo ./install-tl -repository https://ftp.math.utah.edu/pub/tex/historic/systems/texlive/2022/tlnet-final
   ```

3. **Select the Medium Installation (Option `c`):**
   * Once the text-based installer menu loads, press **`S`** (Select Scheme).
   * From the schemes list, choose **`c`** for the **Medium Scheme** (this installs a lightweight but functional LaTeX setup of approximately 600 MB).
   * Press **`R`** to return to the main menu.
   * Press **`I`** to start the installation.

4. **Verify the installation path:**
   Once completed, the binaries will be located at:
   `/usr/local/texlive/2022/bin/x86_64-linux/`

---

## Part 2: Configuring TeXstudio for TeX Live 2022

To bypass any global Debian system-default paths and force TeXstudio to use the newly installed TeX Live 2022 compiler:

1. Open **TeXstudio**.
2. Go to **Options** -> **Configure TeXstudio...**
3. Select the **Commands** tab on the left.
4. Modify the executable path for the compilers you use by prepending the absolute path:
   * **XeLaTeX**: Change to:
     ```text
     /usr/local/texlive/2022/bin/x86_64-linux/xelatex -synctex=1 -interaction=nonstopmode %.tex
     ```
5. Click **OK** to save and apply.

---

## Part 3: Installing Wiley Template Dependencies

The "Medium Scheme" installation lacks several packages required by the Wiley journal template (`WileyNJDv5.cls`). 

Since the 2022 release is frozen, you must explicitly route the package manager to the historic repository to download them. Run the following single command to install all required dependencies at once:

```bash
sudo /usr/local/texlive/2022/bin/x86_64-linux/tlmgr --repository https://ftp.math.utah.edu/pub/tex/historic/systems/texlive/2022/tlnet-final install multirow sttools changepage dblfloatfix soul varwidth mathastext boites algorithmicx wrapfig
```

### Installed Package Map:
* **`sttools`**: Resolves the missing `cuted.sty` dependency.
* **`algorithmicx`**: Resolves the missing `algpseudocode.sty` dependency.
* **`wrapfig`**: Resolves the missing `wrapfig.sty` dependency.
* **`varwidth`**, **`mathastext`**, **`boites`**, **`soul`**, **`dblfloatfix`**, **`changepage`**, **`multirow`**: Required formatting and structural packages.

---

## Part 4: Resolving the Local `listings.sty` Conflict

The Wiley NJD v5 template distribution zip file contains its own local, outdated copy of `listings.sty` in the project folder. This local file is broken and causes compile-time syntax errors in modern environments.

To fix this:
1. Open your local project folder (where `document.tex` is located).
2. Locate the file named **`listings.sty`** inside this directory.
3. **Delete** this file, or rename it to **`listings__.sty`**.

Removing this file forces LaTeX to use the official, updated, and bug-free `listings` package from your TeX Live 2022 installation instead.

---

## Part 5: Verification

To verify that your setup is working correctly:
1. Compile your document in TeXstudio (**F5**).
2. Go to **Tools** -> **View Log**.
3. Confirm that the very first line of the log outputs:
   `This is XeTeX, Version ... (TeX Live 2022)`
```
