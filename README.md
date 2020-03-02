# Emacs GDSCript Flycheck

This package adds linting support for Godot GDScript code through [Flycheck](https://www.flycheck.org/en/latest/), using [gdlint](https://github.com/scony/godot-gdscript-toolkit/).

For general support for Godot in Emacs, see [Emacs GDScript mode](https://github.com/GDQuest/emacs-gdscript-mode).

## Installation

![banner showing the "GDScript mode" title with GDScript code in the background](https://github.com/GDQuest/emacs-gdscript-mode/raw/master/assets/banner.svg?sanitize=true)

## How to install

This package isn't available in the MELPA archive yet, so you need to install it manually.

You should have `flycheck` available in Emacs. Distributions like [Spacemacs](https://github.com/syl20bnr/spacemacs) and [Doom Emacs](https://github.com/hlissner/doom-emacs) can install it for you. To install it manually, see the [Flycheck install guide](https://www.flycheck.org/en/latest/user/installation.html).

You also need to have gdtoolkit installed. It's a GDScript parser, linter, and code formatter written in Python. You can install gdtoolkit using the pip package manager from Python 3:

```
pip3 install gdtoolkit
```

To install `flycheck-gdscript` manually:

1. Clone the repository to your computer.
1. In your init.el file, add a call to load and require the package.

```lisp
(add-to-list 'load-path "/path/to/gdscript-flycheck.el")
(require 'flycheck-gdscript)
```

### Installing in Spacemacs

1. Clone the repository to the `private/local` sub-directory of your `.emacs.d` directory, where you installed Spacemacs.
2. Add the package to the `dotspacemacs-additional-packages` and mark it as local. That's Spacemacs' feature to make it easy to load locally installed packages.

```lisp
dotspacemacs-additional-packages '((flycheck-gdscript :location local))
```

3. In your `dotspacemacs/user-config` function, require the package.

```lisp
(defun dotspacemacs/user-config ()
  (require 'gdscript-mode))
```

### Installing in Doom Emacs ###

Add the following package definition to your `.doom.d/packages.el` file:

```lisp
(package! gdscript-mode
          :recipe (:host github
                   :repo "GDQuest/emacs-gdscript-flycheck"
                   :files ("*.el")))
```

Require the package in your `.doom.d/config.el` file:

```lisp
(require 'flycheck-gdscript)
```

## Contributing ##

If you find a bug or would like to suggest an improvement, [open an issue](issues/new).

For code style, we follow the [Emacs lisp style guide](https://github.com/bbatsov/emacs-lisp-style-guide) by Bozhidar Batsov, and the [tips and conventions](https://www.gnu.org/software/emacs/manual/html_node/elisp/Tips.html) from the Emacs manual.
