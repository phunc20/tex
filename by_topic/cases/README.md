

$$
D[i, j] = \min \begin{cases}
    D[i-1, j] + \texttt{del}(X[i]) \\
    D[i, j-1] + \texttt{ins}(Y[j]) \\
    D[i-1, j-1] + \texttt{sub}(X[i], Y[j])
\end{cases}
$$
