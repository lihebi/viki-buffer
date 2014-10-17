#latex

#basic framework
'' \documentclass{a4paper}{article}
'' \usepackage{xxx}
''
'' \title{TITLE}
'' \author{Me}
'' \date{\today}
''
'' \begin{document}
'' \maketitle
'' \begin{abstract}
'' ABSTRACT
'' \end{abstract}
''
'' \section{Introduction}
'' …
'' \end{document}

#list
''\begin{enumerate}
''\item Like this,
''\item and like this.
''\end{enumerate}

''\begin{itemize}
''\item Like this,
''\item and like this.
''\end{itemize}

''\begin{description}
''\item[Word] Definition
''\item[Concept] Explanation
''\item[Idea] Text
''\end{description}

#formula

''$X_1, X_2, \ldots, X_n$
'' $\text{E}[X_i] = \mu$
'' $\text{Var}[X_i] = \sigma^2 < \infty$
'' $$S_n = \frac{X_1 + X_2 + \cdots + X_n}{n}
''       = \frac{1}{n}\sum_{i}^{n} X_i$$
'' $\sqrt{n}(S_n - \mu)$
'' $\mathcal{N}(0, \sigma^2)$
'' \: media space
'' \in 属于

#table
''\begin{table}
'' \centering
'' \begin{tabular}{l|r}
'' Item & Quantity \\\hline
'' Widgets & 42 \\
'' Gadgets & 13
'' \end{tabular}
'' \caption{\label{tab:widgets}An example table.}
'' \end{table}

#label
''\label{xxx}
''
'' \ref{xxx}
''
'' \label{xx:yy}
'' \ref{xx:yy}

#figure
'' \begin{figure}
'' \centering
'' \includegraphics[width=0.3\textwidth]{frog.jpg}
'' \caption{\label{fig:frog}This frog was uploaded to writeLaTeX via the project menu.}
'' \end{figure}

`figure*` can make the figure two column

#in-pdf comment
Comments can be added to the margins of the document using the `\todo{Here's a comment in the margin!}` todo command, as shown in the example on the right. You can also add inline comments:

`\todo[inline, color=green!40]{This is an inline comment.}`
