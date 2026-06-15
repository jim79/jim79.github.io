---
title: Resolve WileyNJDv5 LaTeX template compilation errors
permalink: /wileynjdv5-resolve-errors/
layout: single
---

# TeX Live 2022 + WileyNJDv5 on Debian: Getting it to actually compile

The `WileyNJDv5` document class assumes a fairly old LaTeX environment, and modern Debian packages fight it in a few specific ways. The fix that worked reliably: pin to TeX Live 2022 from TUG's historic archive, install the handful of missing packages, and delete the broken `listings.sty` that ships inside the Wiley zip. This guide walks through each step.

---

## Installing TeX Live 2022

Debian's repos pull in whatever the current TeX Live release is, so you need to go around them and grab the 2022 installer directly from TUG's frozen archive.

```bash
cd /tmp
wget https://ftp.math.utah.edu/pub/tex/historic/systems/texlive/2022/install-tl-unx.tar.gz
tar -xzf install-tl-unx.tar.gz
cd install-tl-2022*
sudo ./install-tl -repository https://ftp.math.utah.edu/pub/tex/historic/systems/texlive/2022/tlnet-final
```

When the text installer menu appears, press **S** to choose a scheme, then **c** for the Medium scheme, then **R** to go back, then **I** to start. The Medium scheme is around 600 MB and has enough to work with — you'll add the Wiley-specific packages separately.

Binaries land at `/usr/local/texlive/2022/bin/x86_64-linux/`.

---

## Pointing TeXstudio at the right compiler

By default TeXstudio picks up whatever's on your system path, which is probably not the 2022 install. Fix it manually:

**Options → Configure TeXstudio → Commands**

Change the XeLaTeX entry to the full path:

```
/usr/local/texlive/2022/bin/x86_64-linux/xelatex -synctex=1 -interaction=nonstopmode %.tex
```

---

## Installing the missing packages

The Medium scheme skips a number of packages that `WileyNJDv5.cls` expects. Since the 2022 release is frozen, `tlmgr` needs the repository pointed explicitly at the historic archive:

```bash
sudo /usr/local/texlive/2022/bin/x86_64-linux/tlmgr \
  --repository https://ftp.math.utah.edu/pub/tex/historic/systems/texlive/2022/tlnet-final \
  install multirow sttools changepage dblfloatfix soul varwidth mathastext boites algorithmicx wrapfig
```

A few of these map to non-obvious filenames — `sttools` is what provides `cuted.sty`, and `algorithmicx` covers `algpseudocode.sty`. The rest (`wrapfig`, `varwidth`, `mathastext`, `boites`, `soul`, `dblfloatfix`, `changepage`, `multirow`) are standard formatting dependencies the template pulls in.

---

## Removing the bundled `listings.sty`

The Wiley zip includes its own copy of `listings.sty` in the project folder. It's outdated and causes syntax errors at compile time. Just delete it (or rename it to something like `listings__.sty` if you want to keep it around):

```
<your project folder>/listings.sty  ← delete this
```

Once it's gone, LaTeX falls back to the `listings` package from the TeX Live 2022 installation, which compiles cleanly.

---

## Checking that it worked

Compile with **F5** in TeXstudio, then open **Tools → View Log**. The first line should read something like:

```
This is XeTeX, Version ... (TeX Live 2022)
```

If it doesn't, TeXstudio is still pointing at a different installation — double-check the Commands path from the configuration step above.