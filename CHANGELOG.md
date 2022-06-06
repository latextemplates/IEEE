# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/).
From 2022-02-28 onwards, versioning is done using [Calendar Versioning](https://calver.org/).

## [2022-06-06]

### Added

- Magic comment for [LTeX](https://github.com/valentjn/vscode-ltex#ltex-extension-for-vs-code-grammarspell-checker-using-languagetool-with-support-for-latex-markdown-and-others) (because of [vscode-ltex#632](https://github.com/valentjn/vscode-ltex/issues/632))

### Changed

- `_latexmkrc` is available instead of `latexmkrc` to ease usage at overleaf. [lncs#40](https://github.com/latextemplates/LNCS/issues/40)

### Fixed

- Fixed reference to examples in IEEE template
- Fixed line break in introduction

## [2022-02-28]

### Added

- Added package [mindflow](https://www.ctan.org/pkg/mindflow), which supports quickly noting down thoughts with a) a proper rendering of LaTeX and b) a proper differentiation from the main text

### Removed

- Removed `paper-conference-compsoc.tex` as the option `compsoc` is not in use any more.
- Removed `paper-9pt-technote.tex` as that format is not used at all.

### Changed

- Now generated using the [latex template generator](https://www.npmjs.com/package/generator-latex-template).
- Updated to TeXLive 2021
- Switch from [balance](https://ctan.org/pkg/balance) to [pbalance](https://ctan.org/pkg/pbalance), because the latter works better in edge cases.

### Fixed

- Examples now also work on overleaf. `\currfile` now correctly returns `main.tex`/`paper.tex` instead of `output.tex`.

## [1.5.0] – 2020-03-29

### Fixed

- Fixed compatibility with recent babel versions: using `main=english` as package parameter.

## [1.4.0] – 2018-03-07

### Added

- Added "aboveskip" and "belowskip" hints.
- Added example Java listing using minted.
- Added example XML listing using listings.

### Changed

- Changed minted style from friendly to bw.

## [1.3.0] – 2018-03-06

### Added

- Added optional tweak to reduce spacing between bibitems
- Added `crefname` for `lstlisting` to ensure cleveref works

### Changed

- Removed `chngcntr`, because lsitings package counts right in the case of IEEE.
- Separated minted support to separate file `paper-conference-minted.tex`.

## [1.2.0] – 2018-02-07

### Changed

- Ligatures are disabled for monospaced font. E.g., \texttt{--} stays `--` and is not converted to an en dash.

## [1.1.0] – 2018-02-03

### Fixed

- Title of `paper-conference.tex` does not show "Computer Society" any more.

### Added

- One more lipsum paragraph on first page and separate Lorem Ipsum section.
- Enforce version V1.8b (2015/08/26) of [IEEEtrans.cls](http://www.michaelshell.org/tex/ieeetran/).

### Changed

- Removed `tracking=smallcaps` option in microtype to have letters in `\textsc{BPMN}` standing closer together.
- Instead of package [cite](https://www.ctan.org/pkg/cite) the more comprehensive package [natbib](https://www.ctan.org/pkg/natbib) is used. Thereby, `\citet{ref}` is enabled.

### Removed

- Removed wrong `\allowbreak{}` example.

## [1.0.0] – 2018-01-30

First release using semantic versioning.

[Unreleased]: https://github.com/latextemplates/IEEE/compare/2022-06-06...HEAD
[2022-06-06]: https://github.com/latextemplates/IEEE/compare/2022-02-28...2022-06-06
[2022-02-28]: https://github.com/latextemplates/IEEE/compare/1.5.0...2022-02-28
[1.5.0]: https://github.com/latextemplates/IEEE/compare/1.4.0...1.5.0
[1.4.0]: https://github.com/latextemplates/IEEE/compare/1.3.0...1.4.0
[1.3.0]: https://github.com/latextemplates/IEEE/compare/1.2.0...1.3.0
[1.2.0]: https://github.com/latextemplates/IEEE/compare/1.1.0...1.2.0
[1.1.0]: https://github.com/latextemplates/IEEE/compare/1.0.0...1.1.0
[1.0.0]: https://github.com/latextemplates/IEEE/releases/tag/1.0.0

<!-- markdownlint-disable-file MD024 MD033 -->
