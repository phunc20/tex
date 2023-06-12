## Tips
1. [Start an enumeration not from 1](https://tex.stackexchange.com/questions/142/how-can-i-make-an-enumerate-list-start-at-something-other-than-1)  
   For example,
   ```latex
   \begin{enumerate}
     \setcounter{enumi}{4}
     \item fifth element
   \end{enumerate}
   ```
   (If you have lists at deeper levels of nesting, the relevant counters are `enumii`, `enumiii` and `enumiv`.)
1. (`beamer`)
    - Gradually display items slide after slide, e.g.
      ```tex
      \begin{enumerate}
        \item<1-> Shown since slide 1
          \begin{itemize}
            \item<2> Shown only on slide 2 (i.e. empty on slide != 2)
            \item<2-> Shown since slide 2
          \end{itemize}
        \item<3-> Shown since slide 3
      \end{enumerate}
      ```
