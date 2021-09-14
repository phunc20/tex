
- `tikz.tex` has to be "compiled" by `pdflatex`; `pdftex` cannot.
- `vn.tex`: To type Vietnamese by typing, say, VNI, directly inside `.tex` file
  - The one-liner **`\usepackage[utf8]{vietnam}`** works for me (Arch Linux using `pdflatex`)
  - whereas the two-liner **no**
    ```tex
    \usepackage[utf8]{inputenc}
    \usepackage[vietnam]{babel}
    ```


