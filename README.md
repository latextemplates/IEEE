# Simplified IEEE Template [![Build](https://github.com/latextemplates/IEEE/workflows/Build%20and%20publish%20to%20gh-pages/badge.svg)](https://github.com/latextemplates/IEEE/actions?query=workflow%3A%22Build+and+publish+to+gh-pages%22)

> Quick start for modern LaTeXing for an IEEE conference, based on the [Manuscript Template for Conference Proceedings](https://www.ieee.org/conferences_events/conferences/publishing/templates.html).

The official template is distributed via CTAN as the [IEEEtran package](https://ctan.org/pkg/ieeetran), which is actively maintained.
However, de-facto configurations (hyperref) and modern features of latex (microtype) are not configured.
This page does it.

This template is for the computer science conferences.
It is based on the `bare_conf_compsoc.tex` distributed by IEEE.
In case you need other configurations, please adapt `paper-conference.tex` or `paper-conference-compsoc.tex`.

Examples:

- [paper-conference.pdf](https://latextemplates.github.io/IEEE/paper-conference.pdf) - regular conference paper.
- [paper-conference-minted.pdf](https://latextemplates.github.io/IEEE/paper-conference-minted.pdf) - conference paper showing minted in action.
- [paper-conference-compsoc.pdf](https://latextemplates.github.io/IEEE/paper-conference-compsoc.pdf) - papers for IEEE Computer Society conference papers.
- [paper-9pt-technote.pdf](https://latextemplates.github.io/IEEE/paper-9pt-technote.pdf) - technical notes with font size 9pt.

## Attention

Some conferences distribute a `IEEEtran.cls` V1.7a dated 2007 and a parameter `compsocconf`.
**The parameter `compsocconf` was NEVER included in Michael Shell's IEEEtran.cls file. It is unclear, who did this patch and why it is around in the wild.**

The most recent version is V1.8b and automatically distributed over CTAN, because it is actively maintained by Michael Shell at <http://www.michaelshell.org/tex/ieeetran/>.
A full changelog is available at <http://mirror.ctan.org/tex-archive/macros/latex/contrib/IEEEtran/changelog.txt>.

```text
 2014/09/17 V1.8a (MDS) changes:

 1) Extensive rework of the compsoc mode to comply with the latest standards
    of the IEEE Computer Society.
```

The class parameter `compsocconf` never existed officially.
One has to use `conference, compsoc`, because the parameters are "orthogonal": Either "conference" or "journal", either "compsoc" or not.
With a modern IEEEtran.cls, you'll get

```text
LaTeX Warning: Unused global option(s):
    [compsocconf].
```

When using the 2007 version or the most recent version with (the unhandled) `compsocconf`, you'll get [paper-conference.pdf](https://latextemplates.github.io/IEEE/paper-conference.pdf) instead of [paper-conference-compsoc.pdf](https://latextemplates.github.io/IEEE/paper-conference-compsoc.pdf).
That differs significantly in the style used for section headings.

IEEE distributes their templates at <https://www.ieee.org/conferences_events/conferences/publishing/templates.html>.
With the update of July 2017, the archive <https://www.ieee.org/documents/ieee-latex-conference-template.zip> contains both `bare_conf.tex` and `bare_conf_compsoc.tex`.
Thus, the conference should state which option to use.

All in all, the distributions of IEEEtran from 2007 are roughly equivalent to `\documentclass[conference]{IEEEtran}` (and version V1.8b), which **does not comply** with IEEE's rules for computer science conferences, because the `compsoc` option is missing.

Hence, **double check with your conference whether you have to use `compsoc` or not.**

Statement from IEEE:

> Please note that, as stated on the webpage <https://www.ieee.org/conferences_events/conferences/publishing/templates.html>. "IEEE does not require a specific format for their conference articles". Thus, we dot not purport that the "compsoc" is a requirement for publishing conference papers with us.

## TOC

<!-- toc -->

- [Features](#features)
- [Quick start](#quick-start)
- [Tool hints](#tool-hints)
- [Using the template with your git repository](#using-the-template-with-your-git-repository)
- [FAQ](#faq)
- [Links](#links)

<!-- tocstop -->

## Features

- Provides skeletal [paper-conference.tex](paper-conference.tex) and [paper-conference-compsoc.tex](paper-conference-compsoc.tex) files.
- Generated PDF allows for copy and paste of text without getting words with ligatures such as "workflow" destroyed.
   This is enabled by the [cmap] package, which encodes ligatures (such as fl) using unicode characters.
- Support of hyperlinked references without extra color thanx to [hyperref].
- Better breaking of long URLs.
- Support for `\powerset` command.
- Support todos as pdf annotations. This is enabled by the [pdfcomment] package.
- [microtypographic extensions](https://www.ctan.org/pkg/microtype) for a better look of the paper.
- Adds modern packages such as [microtype], [cleveref], [csquotes], [booktabs], [paralist], [hyperref], [hypcap], [upquote].
- Shows how IEEE copyright notice can be added.
- Optional: Support for [minted] package. Prepared in `paper-conference-minted.tex`.
- Ready-to-go configuration for [latexindent].

## Quick start

- Click on `Download ZIP` or [here](https://github.com/latextemplates/IEEE/archive/master.zip).
- Extract `master.zip` in the folder where you want to write your paper.
- In case you are working in the computer science field: Edit [paper-conference-compsoc.tex](paper-conference-compsoc.tex).
- In case you are NOT working in the computer science field: Edit [paper-conference.tex](paper-conference.tex).
- `latexmk paper-conference-compsoc` OR `latexmk paper-conference`.

## Tool hints

There is currently no official biblatex support.
A first step towards that is done at the [biblatex-ieee package](https://ctan.org/pkg/biblatex-ieee).

MiKTeX installation hints are given at <https://github.com/latextemplates/scientific-thesis-template/blob/template/README.md#installation-hints-for-windows>.

- Grammar and spell checking is available at [TeXstudio].
  Please download [LanguageTool] (Windows: `choco install languagetool`) and [configure TeXstudio to use it](http://wiki.languagetool.org/checking-la-tex-with-languagetool#toc4).
  Note that it is enough to point to `languagetool.jar`.
  **If TeXstudio doesn't fit your need, check [the list of all available LaTeX Editors](http://tex.stackexchange.com/questions/339/latex-editors-ides).**
- Use [JabRef] to manage your bibliography (Windows: `choco install jabref`).


In case you want to get started using minted, do following steps:

1. Install python: `choco install python` - that uses [chocolatey](https://chocolatey.org/) to install Python
2. Install [pygments]: `pip instal pygments` - that uses the Pyhton package manager to install the pygments library
3. When latexing, use `-shell-escape`: `pdflatex -shell-escape paper`.
   You can also just execute `latexmk paper`.

## Using the template with your git repository

1. Initialize your git repository as usual
2. Add this repository as upstream: `git remote add upstream https://github.com/latextemplates/IEEE.git`
3. Merge the branch `upstream/master` into your `master` branch: `git merge upstream/master`.

After that you can use and push the `master` branch as usual.
Notes on syncing with the upstream repository [are available from GitHub](https://help.github.com/articles/syncing-a-fork/).

## FAQ

### Q: I get the error  `! pdfTeX error (font expansion): auto expansion is only possible with scalable fonts.` What can I do?

Install the `cm-super` package using the MiKTeX package manager. Then, run `initexmf --mkmaps` on the command line. (Long description: http://tex.stackexchange.com/a/324972/9075)

### Q: I have questions on the IEEEtran class itself.

The author of the class offers a large FAQ at <http://www.michaelshell.org/tex/ieeetran/>.
Please read on there.

### Q: How can I reformat my .tex files?

Execute `latexindent -l -s -sl -w paper.tex`

### Q: How I want to obey the one-sentence-per-line rule.

Execute `latexindent -m -l -s -sl -w paper.tex`.
Attention! This is work in progress and does not always produce best results.

## Links

- German: Hinweise zu Ausarbeitungen: <http://wiki.flupp.de/studium/ausarbeitungen>
- Other templates: <http://latextemplates.github.io/>

  [booktabs]: https://www.ctan.org/pkg/booktabs
  [cleveref]: https://ctan.org/pkg/cleveref
  [cmap]: https://www.ctan.org/pkg/cmap
  [csquotes]: https://www.ctan.org/pkg/csquotes
  [hypcap]: https://www.ctan.org/pkg/hypcap
  [hyperref]: https://ctan.org/pkg/hyperref
  [latexindent]: https://ctan.org/pkg/latexindent
  [microtype]: https://ctan.org/pkg/microtype
  [minted]: https://ctan.org/pkg/minted
  [newtx]: https://ctan.org/pkg/newtx
  [paralist]: https://www.ctan.org/pkg/paralist
  [pdfcomment]: https://www.ctan.org/pkg/pdfcomment
  [upquote]: https://www.ctan.org/pkg/upquote

  [JabRef]: https://www.jabref.org
  [LanguageTool]: https://languagetool.org/
  [TeXstudio]: http://texstudio.sourceforge.net/
  [pygments]: http://pygments.org/

<!-- markdownlint-disable-file MD026 -->
