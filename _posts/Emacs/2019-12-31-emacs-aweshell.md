---
title: Emacs 筆記：Aweshell
category: Emacs
layout: post
hidden: true
---
[Aweshell](https://github.com/manateelazycat/aweshell) 是一個 Emacs 套件，用於增強內建的 Eshell。作者自己也有寫了一篇介紹：[《像 IDE 一样使用 Shell》](https://manateelazycat.github.io/emacs/2018/08/10/aweshell.html)，可以參考下。

摘錄一下特點列表：（作者提了 15 項，我這裏摘錄一下我自己覺得最常用的）

1. 像 MultiTerm 一样对 eshell 进行多 bufffer 创建和切换功能
2. 实时检查命令是否有效, 并对无效命令/别名提前进行高亮显示, 避免执行后发现敲错字符
3. unpack 命令可以直接解压压缩文件, 不用记住那么多解压命令
4. 命令敲错的时候, 显示 didi you mean 的帮助
5. 后台命令完成或终止时提醒用户

## 安裝方法
我自己是用 el-get。但是因爲某些原因，el-get 的維護者對於我的 rcp 有些[疑問](https://github.com/dimitri/el-get/pull/2691)，我自己也不是 aweshell 的作者，不知道從何修起，遂把 rcp 放在我自己的 ``el-get-user/recipes`` 資料夾下：

``` Lisp
(:name aweshell
       :type github
       :description "Awesome shell extension base on eshell"
       :pkgname "manateelazycat/aweshell"
       :prepare
       (require 'aweshell))
```

## 在 Eshell 中包入自定義的 ``$PATH``
會用 Awehsll，主要是我在 macOS 的終端下，有很多工具不是裝在系統 ``$PATH`` 內（例如，自己編譯的工具、homebrew 本身以及用 brew 安裝的軟體等）。我本來用了一段來自 StackOverflow - [How to make Emacs use my .bashrc file?](https://stackoverflow.com/questions/6411121/how-to-make-emacs-use-my-bashrc-file) 的方案，很是複雜！。

``` Lisp
(defun set-exec-path-from-shell-PATH ()
  (let ((path-from-shell
         (replace-regexp-in-string
          "[ \t\n]*$"
          ""
          (shell-command-to-string
           "$SHELL --login -i -c 'echo $PATH'"))))
    (setenv "PATH" path-from-shell)
    (setq eshell-path-env path-from-shell) ; for eshell users
    (setq exec-path (split-string path-from-shell path-separator))))

(when window-system (set-exec-path-from-shell-PATH))
```

用了 Aweshell 後，我再也不用擔心這個問題啦！同時也獲得了接近於 [Fish](https://fishshell.com) 這個 shell 的體驗。