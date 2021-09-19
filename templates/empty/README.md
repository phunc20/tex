
- <s>`tikz.tex` has to be "compiled" by `pdflatex`; `pdftex` cannot</s>.
- `tikz_LaTeX.tex` should be "compiled" by `pdflatex`
  - Alternatively, one can
    ```bash
    latex tikz_LaTeX.tex
    dvips tikz_LaTeX.dvi
    ps tikz_LaTeX.ps
    ```
- `tikz_TeX.tex` should be "compiled" by `pdftex`
- `vn.tex`: To type Vietnamese by typing, say, VNI, directly inside `.tex` file
  - The one-liner **`\usepackage[utf8]{vietnam}`** works for me (Arch Linux using `pdflatex`)
  - whereas the two-liner **no**
    ```tex
    \usepackage[utf8]{inputenc}
    \usepackage[vietnam]{babel}
    ```
  - You might encounter error messages saying sth like **`vietnam.sty not found`**, a error that you may
    overcome, if you are using Arch Linux, by `pacman -S texlive-langextra`. Other Linux distros probably
    could solve similarly by installing the corresponding package with a similar name.


