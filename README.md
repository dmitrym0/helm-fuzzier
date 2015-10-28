
### Description

This package provides more intuitive fuzzy matching behavior for
[Helm](https://github.com/emacs-helm/helm).

Now available on MELPA, install it with `package-install`.

`helm-fuzzier` only fixes half the trouble with Helm, the other half
(showing the best results first and the nice highlighting seen in the
demo below) is provided by the
[helm-flx](https://github.com/PythonNut/helm-flx) package from MELPA.

### Demo

![Action Gif](https://cloud.githubusercontent.com/assets/15329740/10805173/7faaf286-7dd4-11e5-9fba-f453f2faa49e.gif)

[This demo](https://www.youtube.com/watch?v=8Ceeew4Hdz8) is even better.

### Installation:

```elisp
  (require 'helm-fuzzier)
  (helm-fuzzier-mode 1)
```

`helm-fuzzier` will only enhance matching for sources that have
fuzzy-matching enabled, so **be sure to enable fuzzy-matching for the
sources** you're interested in by setting the appropriate variable
(`helm-M-x-fuzzy-match`, `helm-mode-fuzzy-match`,
`helm-apropos-fuzzy-match`, etc').

### Usage

Any query that currently works for you should generally continue to do so.
However, when `helm-fuzzier-mode` is enabled, a query that:

- Begins with the same letter as the desired match.
- Is formed by stringing together two or more prefixes from the words
that make up the match.

... should nearly always result in the match you're looking for appearing in the
top few results.

**Example Queries**:

- `el`, `em`, `elm`, `eli`, `elmo`, should all match `emacs-lisp-mode`.
- `plp`, `plpa`, `paclp`, should all match `package-list-packages`.
- `hcn`, `hnl`, `hecl`, should all match `helm-candidate-number-limit`.

Try toggling `helm-fuzzier-mode` on and off and compare the results you
get with and without `helm-fuzzier`.

### Requirements

- Emacs >= 24.3
- Helm >= 1.7.0

### Notes

See source code for more detailed information on the implementation.
