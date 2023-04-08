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
