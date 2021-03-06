---
title: "Supercharging Vim: Using plugins"
description: >-
  Vim is an extremely powerful text editor.
  With no setup,
  you can do amazing work,
  however,
  you can supercharge Vim
  by extending it with plugins.
  This blog series will show how to get the most out of Vim.
image: img/2017/vim.png
type: post
aliases:
 - /2017/supercharging-vim-using-plugins.html
categories:
 - Guide
tags:
 - Vim
 - plugins

---

For many years,
I worked in private networks
for different contracts
where having a customized editor
for software development
was tough.
That environment made me feel that customizing my work tools was fruitless.
Looking back,
I wish I had ignored that feeling.

My main editor is
{{< extlink "http://www.vim.org/" "Vim" >}},
a tool with a strong reputation.
I was very comfortable with the tool's default settings,
but I had not explored how to customize it
beyond turning on syntax highlighting.

Once I joined
{{< extlink "https://storybird.com/" "Storybird" >}}
and was working
with my own hardware,
I decided to improve my workflow
with Vim plugins.

This is the beginning
of a blog series that will cover how to use plugins
in Vim
and some of the plugins
that have supercharged the way I work.
I hope it will inspire you
to make your own work experience better.

If you dig this,
check out other posts
in the series.

{{< vim-series "plugins" >}}

## Managing plugins

Vim has a built-in way to use plugins,
but it doesn't provide a lot of features
to *manage* those plugins.

To install and manage Vim plugins,
you'll need a Vim plugin manager.
There are a few options like
{{< extlink "https://github.com/tpope/vim-pathogen" "Pathogen" >}},
{{< extlink "https://github.com/VundleVim/Vundle.vim" "Vundle" >}},
and {{< extlink "https://github.com/junegunn/vim-plug" "vim-plug" >}}.
Each of these tools works in a similar way.
I happen to use vim-plug
so that's the tool I'll describe here.

### Bootstrapping

There is an interesting challenge
of getting started when adding a package/plugin manager.
Programming languages
and development ecosystems now often include management tools
such as `pip` or `npm`,
but Vim takes a bit of manual intervention.

To install vim-plug, we must:

1. Fetch the tool and put it in a directory
   where Vim will automatically load it.
2. Configure the editor to use it.

If you've used Vim
in the past,
you may be familar with a `~/.vimrc` file
that can contains any settings
to change the editor
(e.g., `syntax on`).
Instead of using a single file,
modern Vim can load configuration data
from a `~/.vim` directory.
On your local machine,
vim-plug must be placed in `~/.vim/autoload`.

```bash
$ curl -fLo "~/.vim/autoload/plug.vim" \
  https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

After you download vim-plug,
let's configure Vim to use it.
In your `vimrc`
(which will now be in `~/.vim/vimrc`),
you can include a section to list your plugins.

```vim
call plug#begin('~/.vim/plugged')
" Put your plugins here.
Plug 'tpope/vim-unimpaired'
call plug#end()
```

The `Plug` line is an example plugin.
This should be all you need to start using vim-plug.

### Installing plugins

Vim plugins often use Git and GitHub
for hosting.
In the example configuration above,
the vim-unimpaired plugin comes from
{{< extlink "https://github.com/tpope/vim-unimpaired" "https://github.com/tpope/vim-unimpaired" >}}.

vim-plug works by cloning each Git repository
into the location specified by `begin`.
After installing,
you can find the example plugin
in `~/.vim/plugged/vim-unimpaired`.

Installing plugins is done *inside*
of Vim.
From your open editor session,
run `:PlugInstall`.
This will bring up a split
in your editor
that will show the progress
of installing each plugin.
vim-plugin downloads plugins
in parallel
so it should be a quick process.

Now you know how to install plugins
in Vim!
Learn more about vim-plug
at the {{< extlink "https://github.com/junegunn/vim-plug" "vim-plug project page" >}}.

## Next time

In the next post,
we'll look at how you can run unit tests
inside of Vim,
and minimize the delay
in getting test feedback.

Next up: {{< extlink "https://github.com/janko-m/vim-test" "vim-test" >}}.
