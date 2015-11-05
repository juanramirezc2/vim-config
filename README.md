# vim  config for Front End developers

### Full features list
#### Easy installation
You just need to place `.vimrc` in your home directory, and that's all. All
plugins and dependencies will install automatically upon first vim launch.
#### Folding
Folding is disabled by default, but you may fold any part of JS code according to
the syntax with just `Space` key.
#### Remember your last editing sessions
When you open file, which you used editted last, vim will open it on the exact
same line.
#### Vertical ruler
There is a vertical line indicating 80 character limit, it can be seen on
the screenshot above.
#### Smart search
Vim’s built-in search ignores case by default, but if you use mixed
lower/upper-case in the search pattern, it'll be case-sensitive.
#### Quick plugin install &mdash; [Neobundle](https://github.com/Shougo/neobundle.vim)
It's a bundler, which helps to install other bundles. It's quite smart and works better then
vundle.
#### Snippets &mdash; [Neosnippet](https://github.com/Shougo/neosnippet.vim) & [vim-snippets](https://github.com/honza/vim-snippets)
Neosnippet is a snippet engine itself, and Vim-snippets &mdash; it’s default snippets collection.

This config features snippets, which can be autocompleted by `tab`
аnd expanded by `Enter`. Here is [a full list of snippets](https://github.com/honza/vim-snippets/tree/master/snippets).

#### Smart panels &mdash; [Unite](https://github.com/Shougo/unite.vim)
Provides features like:
* Recent files list (with help of [neomru](https://github.com/Shougo/neomru.vim)).
* Quick tab navigation.
* Async fuzzySearch (with help of [vimproc](https://github.com/Shougo/vimproc.vim)).
* Grep/Ack integration.
* Yank/History.

#### On-the-go Syntax checker &mdash; [Syntastic](https://github.com/scrooloose/syntastic)
This plugin integrates many spellchekers and syntax checkers and shows
you errors when saving or opening a file.

By default this config use npm-packets [jshint](http://www.jshint.com/) and [css-lint](http://csslint.net/) to check js and css files on the fly.

#### Advanced file-system navigation &mdash; [NERDTree](https://github.com/scrooloose/nerdtree)
Imroved file-system navigation. Looks pretty much like the standard one but with some cool features like tree navigation, bookmarks, and some more.

#### Improved status line &mdash; [Airline](https://github.com/bling/vim-airline)
Nice and good loking status bar for vim, nicely integrated with syntastic and fugitive.

#### Good keyword completion system &mdash; [Neocomplcache](https://github.com/Shougo/neocomplcache.vim)
Provides smart autocompletion.

#### Integration with git &mdash; [Fugitive](https://github.com/tpope/vim-fugitive)
Provides full integration wit git.

#### Advanced javascript features &mdash; [Tern for Vim](https://github.com/marijnh/tern_for_vim)
Provides advanced javascript features like Smart variable rename, Find variable references, and Go to variable. If you use `.ternconf` &mdash; it'll improve autocompletion in your js files as well.
#### Improved editing
* [DelimitMate](https://github.com/Raimondi/delimitMate) &mdash; provides automatic closing of quotes, parenthesis, brackets, etc., also has some other related features that will make your time in insert mode a little bit easier.
* [tcomment](https://github.com/tomtom/tcomment_vim) &mdash; tcomment provides easy-to-use, file-type sensible comments for Vim. It can handle embedded syntax.
* [surround](https://github.com/tpope/vim-surround) is all about “surroundings”: parentheses, brackets, quotes, XML tags, and more. The plugin provides keystrokes to easily delete, change and add such surroundings in pairs.
* [MatchTag](https://github.com/gregsexton/MatchTag) &mdash; highlights the matching HTML tag when the cursor is positioned on a tag. It works in much the same way as the MatchParen plugin.


### Installation

To install just clone the repo, and place symlink to .vimrc in your home directory. E.g.:
```bash
 git clone https://github.com/adictovirtual/vim-config.git && ln -s ~/vim-config/.vimrc ~/
```
[NPM](http://en.wikipedia.org/wiki/Npm_(software)) is required for some features.

## You Complete Me plugin  installation
**Remember:** YCM is a plugin with a compiled component. If you **update** YCM
using Vundle and the ycm_support_libs library APIs have changed (happens
rarely), YCM will notify you to recompile it. You should then rerun the install
process.

**NOTE:** If you want C-family completion, you MUST have the latest Xcode
installed along with the latest Command Line Tools (they are installed when you
start Xcode for the first time).

Install CMake. Preferably with [Homebrew][brew], but here's the [stand-alone
CMake installer][cmake-download].

_If_ you have installed a Homebrew Python and/or Homebrew MacVim, see the _FAQ_
for details.

Compiling YCM **with** semantic support for C-family languages:

    cd ~/.vim/bundle/YouCompleteMe
    ./install.py --clang-completer

Compiling YCM **without** semantic support for C-family languages:

    cd ~/.vim/bundle/YouCompleteMe
    ./install.py

If you want semantic C# support, you should add `--omnisharp-completer` to the
install script as well. If you want Go support, you should add
`--gocode-completer`. If you want semantic TypeScript support, install the
TypeScript SDK with `npm install -g typescript` (you'll need to install
[nodejs and npm][npm-install]).

That's it. You're done. Refer to the _User Guide_ section on how to use YCM.
Don't forget that if you want the C-family semantic completion engine to work,
you will need to provide the compilation flags for your project to YCM. It's all
in the User Guide.

YCM comes with sane defaults for its options, but you still may want to take a
look at what's available for configuration. There are a few interesting options
that are conservatively turned off by default that you may want to turn on.
### ternJS
Tern consists of several components. Depending on what you are trying to do with it,
you will be interested in a different layer. At the very top are the editor plugins. 
These talk to a Tern server, which is implemented on top of the server module, which 
uses the inference engine to do the actual type inference.

``cd ~/.vim/bundle/tern_for_vim
npm install ``

Example `.tern-project` file (customize to your own needs) create in the ~ folder:

```json
{
  "ecmaVersion": 6,
  "libs": [
    "browser",
    "jquery"
  ],
  "loadEagerly": [
    "absolute/or/relative/path/to/your/js/**/*.js"
  ],
  "dontLoad": [
    "absolute/or/relative/path/to/your/js/**/*.js"
  ],
  "plugins": {
    "complete_strings": {},
    "node": {},
    "lint": {},
    "angular": {},
    "requirejs": {},
    "es_modules": {},
    "doc_comment": {
      "fullDocs": true
    }
  }
}
```

### Pro Tips

If you want to make some changes, just fork the repo.
If these changes will be helpfull to others, don't forget to share it through a pull request :).

