# ac-html-csswatcher

Add CSS/LESS CLASS/ID completion support for `ac-html` and `company-web`

## SYNOPSIS ##

![completion with company=web](https://github.com/osv/ac-html-csswatcher/raw/master/screenshot.png)

## DESCRIPTION ##

This package provide completion data for EMACS's `ac-html`
(tested with v0.31, recent version may not work 2015-09-29)
and `company-web` modes by using external tool  - `csswatcher`.
To point your project root directory use projectile style (.git folder, etc) or use `.csswatcher`
file if you want ignore some CSS/LESS files.

## SETUP ##

Install/update Perl module - csswatcher

```
sudo cpan i CSS::Watcher
```

Add to emacs config file:

```lisp
(require 'ac-html-csswatcher)
(ac-html-csswatcher-setup)
;; or if you prefer company-style names:
;;  (company-web-csswatcher-setup)

```

Completion  will regenerated  by  csswatcher after  saving css/less files,
opening html(jade,slim,haml) files, or manually by
`ac-html-csswatcher-refresh` or `company-web-csswatcher-refresh` commands.

To enable completion when editing html use `M-x ac-html-csswatcher+` or add it in your hook.

## FILE .csswatcher ##

If you need exclude some css files create inside your project file `.csswatcher` and add:

```
# ignore all css
ignore: \.css$
# except app.css
use: app\.css
```
