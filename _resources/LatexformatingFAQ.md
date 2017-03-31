---
title: LaTeX formatting FAQ
---

# FAQ on LaTeX formatting for UMM CSci senior seminar

Feel free to add questions and answers and improve the current answers. 

- [A $ in my verbatim breaks TexMaker](#dollar)
- [How do I format a url in a paper?](#url)
- [How do I add a url to a bibliography item?](#bib)
- [How do I balance the last two columns if \balancecolumns has no effect?](#balance)
- [How do I check if my paper uses A4 or Letter Paper?](#a4)
- [How do change my page size from A4 to Letter Paper?](#a4change)
- [How do I preserve capitalization in titles in my bibliography?](#capital)
- [How do I get rid of the navigation icons in Beamer?](#nav_icons)

#### <a name="dollar"><a/>A $ in my verbatim breaks TexMaker

Add a %$ at the end of your verbatim environment.

#### <a name="url"></a>How do I format a url in a paper?

Include a url package in the beginning of the paper (before \begin{document}):

```latex
 \usepackage{url} 
```

 Then use `\url{...}` for urls.

#### <a name="bib"></a>How do I add a url to a bibliography item?
If you are referencing an online article, use the following in your .bib file:

```latex
@misc{...,
  ...,
  howpublished = {\url{http://...}}
} 
```

[Here](http://www.tex.ac.uk/FAQ-citeURL.html) is more information (caution: you must use ACM bibliography style so suggestions to change the style aren't applicable).

#### <a name="balance"></a>How do I balance the last two columns if \balancecolumns has no effect?

```latex
\usepackage{balance}
\begin{document}
...
\balance
\end{document} 
```

[Here](http://ctan.mackichan.com/macros/latex/contrib/preprint/balance.pdf) is more information.

#### <a name="a4"></a>How do I check if my paper uses A4 or Letter Paper?
Using the templates from the senior seminar github fixes this issue Open it in Adobe Reader, go to File menu, and select Properties. In the tab Description it should show Paper Size as 8.5in by 11in (letter paper size). Otherwise it's A4. Note that the difference may not be visible on screen, but might show up when you are trying to print and A4 will mess up the final proceedings if left unchanged.

**Note that current senior seminar templates use letter paper**, so you don't need to worry about it if you use our templates (as you should). 

#### <a name="a4change"></a>How do change my page size from A4 to Letter Paper?
**Note that current senior seminar templates use letter paper**, so you don't need to worry about it if you use our templates (as you should). 

Using the templates from the senior seminar github fixes this issue Some LaTeX formatting programs allow you to set the paper size. For most of them, however, it's difficult to find and the setting may be overwritten later by A4 again. For the seminar proceedings use the sig-alternate.cls linked to the [resources page](seniorsemresources.md). It has a line

```latex
\usepackage[letterpaper]{geometry}
```

among its package declarations that fixes the problem.

If you are using a different document class, such as article (this wouldn't be for your senior seminar proceeding, but for something else that you might be using latex for), then use

```latex
\usepackage[letterpaper]{geometry}
```

after the document class.

#### <a name="capital"></a>How do I preserve capitalization in titles in my bibliography?
If a paper title contains a word that needs to be capitalized, surround it by curly braces, e.g. `{CAPTCHA}` or `{Java}`.

#### <a name="nav_icons"></a>How do I get rid of the navigation icons in Beamer?

If you don't want those pesky presentation controls on your slides during your presentation, use this:

```latex
\setbeamertemplate{navigation symbols}{}
```

(Courtesy of Dillon Stenberg - 03 Dec 2015.)

-- Main.elenam - 08 Oct 2009 