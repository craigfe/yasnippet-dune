# YASnippets for the Dune build system

[Dune] ships with an Emacs major mode that defines [skeletons] for snippet
expansion. However...

- Emacs' built-in template support is somewhat archaic;
- the skeletons exclude certain fields that I often miss (particularly
  `package`);
- there is no `dune-project-mode`, thus no snippets for `dune-project` files.

These are alternative snippets that work with [YASnippet], a more
modern and complete template system that ships by default with [Spacemacs].

## Install

Clone the repository, and add its location to `yas-snippet-dirs`:

```elisp
(add-to-list 'yas-snippet-dirs '("~/dotfiles/yasnippet-dune"))
```

(Stock Emacs users will need to `M-x package-install yasnippet` first.)

## Usage

Type stanza name, then `M-x yas-expand` or (more likely) add a keybinding for
expansion.

In Spacemacs, `yas-expand` is invoked via `hippie-expand`:

```elisp
;; user-config.el
(global-set-key (kbd "<tab>") 'hippie-expand)

;; .spacemacs: stop auto-completion from getting in the way
  dotspacemacs-configuration-layers
  '((auto-completion :variables auto-completion-tab-key-behavior nil)
    ...)
```

[dune]: https://github.com/ocaml/dune
[skeletons]: https://github.com/ocaml/dune/blob/master/editor-integration/emacs/dune.el#L243
[yasnippet]: https://github.com/joaotavora/yasnippet
[spacemacs]: https://www.spacemacs.org/
