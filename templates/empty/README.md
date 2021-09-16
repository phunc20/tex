
- `tikz.tex` has to be "compiled" by `pdflatex`; `pdftex` cannot.
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


