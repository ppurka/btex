About:
======

`btex` is yet another (!) LaTeX compiler that grew out of my desire to make
compiling into dvi or ps or pdf quickly.

Installation:
-------------

 1. Copy the file btex to a directory which is in your `PATH`. For instance
    `/usr/local/bin`.
 2. Copy the files from <https://github.com/ppurka/sh_functions> to
    a directory which is in your `PATH`. For instance `/usr/local/bin`.

Configuration:
--------------

 * The first time you run btex, it should create a configuration file as
   `$HOME/.config/btex.config`
 * You can open that file and set a pdf and/or ps and/or dvi viewer and set
   other options.
 * It is not mandatory to modify or configure the config file. btex will
   run perfectly fine with the default untouched configuration, but you
   will see less options in the menu during the execution of the program.

Usage:
------

btex can be run simply as if you were running `latex` with no arguments. For
instance if you are used to running:

    $ latex file.tex

then you can simply do

    $ btex  file.tex

Via the configuration file, you can set extra options that will be passed
to `latex` directly. You can also set the default output format by setting
the `MODE` variable in the configuration file.

Look at `btex --help` for more information.


zsh completion:
---------------

A [zsh](http://www.zsh.org) completion file `_btex` is included. An
elementary zsh completion, without using the file `_btex`, can be achieved
by simply adding the following line to your `zshrc`:

    $ echo 'compdef _gnu_generic btex' >> ~/.zshrc
    $ exec zsh

A more elaborate completion can be obtained by placing the file `_btex` in
some completion directory and adding that directory to your zsh's `fpath`:

    $ mkdir -p ~/.config/zsh-completion
    $ cp _btex ~/.config/zsh-completion
    $ echo 'fpath=( ~/.config/zsh-completion $fpath )' >> ~/.zshrc
    $ exec zsh

If you enable this advanced completion, then do not use the `compdef` line
in your `~/.zshrc`.
