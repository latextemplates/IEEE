# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

## [Unreleased]

## [1.4.0] - 2018-03-07

### Added
- Added "aboveskip" and "belowskip" hints.
- Added example Java listing using minted.
- Added example XML listing using listings.

### Changed
- Changed minted style from friendly to bw.

## [1.3.0] - 2018-03-06

### Added
- Added optional tweak to reduce spacing between bibitems
- Added `crefname` for `lstlisting` to ensure cleveref works

### Changed
- Removed `chngcntr`, because lsitings package counts right in the case of IEEE.
- Separated minted support to separate file `paper-conference-minted.tex`.

## [1.2.0] - 2018-02-07

### Changed
- Ligatures are disabled for monospaced font. E.g., \texttt{--} stays `--` and is not converted to an en dash.

## [1.1.0] - 2018-02-03

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

## [1.0.0] - 2018-01-30

First release using semantic versioning.

[Unreleased]: https://github.com/latextemplates/IEEE/compare/1.4.0...HEAD
[1.4.0]: https://github.com/latextemplates/IEEE/compare/1.3.0...1.4.0
[1.3.0]: https://github.com/latextemplates/IEEE/compare/1.2.0...1.3.0
[1.2.0]: https://github.com/latextemplates/IEEE/compare/1.1.0...1.2.0
[1.1.0]: https://github.com/latextemplates/IEEE/compare/1.0.0...1.1.0
[1.0.0]: https://github.com/latextemplates/IEEE/releases/tag/1.0.0
