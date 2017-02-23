# Init mac for developer

* Setting
  * Mac show all files
    * defaults write com.apple.finder AppleShowAllFiles -boolean true ; killall Finder
* Pure vpn
* Alfred
* Dash
* Atom
* Google chrome
* Terminal 替换工具：iTerm
* Homebrew
  * /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  * Wget
    * oh-my-zsh
      * sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
      * *Which plugins would you like to load? (plugins can be found in ~/.oh-my-zsh/plugins/*)
      * Custom plugins may be added to ~/.oh-my-zsh/custom/plugins/
      * Example format: plugins=(rails git textmate ruby lighthouse)
      * Add wisely, as too many plugins slow down shell startup.
      plugins=(git osx go golang man npm sudo svn vi-mode vim-interaction brew)
      * 入门：http://macshuo.com/?p=676
      * Sublime enhance
        * alias subl="'/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl'"
        * alias zshconfig="subl ~/.zshrc"
        * alias nano="subl"
        * export EDITOR="subl"
    * Autojump
      * Brew install autojump
      * autojump plugins
        * [[ -s /usr/local/Cellar/autojump/22.3.0/etc/profile.d/autojump.sh ]] && . /usr/local/Cellar/autojump/22.3.0/etc/profile.d/autojump.sh
    * Oh-my-fish
      * https://github.com/oh-my-fish/oh-my-fish
      * 教程：http://macshuo.com/?p=676
    * Git
    * Brew install git
    * Golang
    * Brew install go
      * Set GOPATH & GOROOT
        * https://gist.github.com/vsouza/77e6b20520d07652ed7d
        * http://www.zhubert.com/blog/2014/02/11/setting-up-go/
      * Init golang
        * http://golanghome.com/post/126
      * Gocode
        * go get -u github.com/nsf/gocode
    * Make
      * Brew install make
      * 教程：http://www.ruanyifeng.com/blog/2015/02/make.html
    * Thrift
      * Brew install thrift
    * Kdiff3
      * Brew install kdiff3
    * Glide
      * Brew install glide
    * Tree
      * Brew install tree
      * Tree -L 2
* Sublime
  * Package control
    * https://packagecontrol.io/installation
    * Install package
    * Gosublime
    * Gitgutter
    * Emmet
    * AllAutocomplete
    * Terminal
    * DocBlockr
    * SublimeCodeIntel
* Makefile
* Man 用法
* Vscode for golang
  * Go support
  * go get -u github.com/golang/lint/golint
  * go get -u github.com/newhook/go-symbols
  * go get github.com/tpng/gopkgs
  * go get github.com/lukehoban/go-outline
  * go get github.com/rogpeppe/godef
  * go get 9fans.net/go/plan9
  * go get github.com/rogpeppe/godef/go/token
  * go get github.com/rogpeppe/godef/go/scanner
  * go get github.com/rogpeppe/godef/go/ast
  * go get 9fans.net/go/plan9/client
  * go get 9fans.net/go/acme
  * go get github.com/rogpeppe/godef/go/parser
  * go get github.com/rogpeppe/godef/go/printer
  * go get github.com/rogpeppe/godef/go/types
  * go get github.com/rogpeppe/godef
  * //go get Golang.org/x/tools/imports
  * go get -v golang.org/x/tools/cmd/guru
  * go get golang.org/x/tools/refactor/importgraph
  * go get golang.org/x/tools/cmd/guru/serial
  * go get golang.org/x/tools/go/types/typeutil
  * go get golang.org/x/tools/go/loader
  * go get golang.org/x/tools/container/intsets
  * go get golang.org/x/tools/refactor/importgraph
  * go get golang.org/x/tools/go/ssa
  * go get golang.org/x/tools/go/callgraph
  * go get golang.org/x/tools/go/ssa/ssautil
  * go get golang.org/x/tools/go/pointer
  * go get golang.org/x/tools/go/callgraph/static
  * go get golang.org/x/tools/cmd/guru
