# Tutorial
URL: http://berndbischl.github.io/mlr/tutorial/html/

## Howto
* Install dependencies:
  `pip install --user mkdocs` or `easy_install --user mkdocs`.
  Install the [math extension for Python-Markdown](https://github.com/mitya57/python-markdown-math):
  After download type `python setup.py build` and `python setup.py install`.
  Install R dependencies as required.
* Only edit R markdown files in subfolder `src`.
* Markdown basics:
  * Basic Markdown: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
  * RStudio Support: https://support.rstudio.com/hc/en-us/articles/200552086-Using-R-Markdown
  * Knitr options: http://yihui.name/knitr/options
* Put additional images in `../images`.
* Link to mlr manual: `[&function]` and `[name](&function)`.
* Link to other manuals: `[&pkg::function]` and `[name](&pkg::function)`.
* Links will only work properly if they point to the *base name* of the help file:
  For example, in order to link to mlr function `foo` documented on help page `bar` write
  `[foo](&bar)` instead of `[&foo]`.
* Link to packages: `[%pkg]` and `[name](%pkg)`.
* Run `./build` to generate new static HTML.
* Commit and push all changes in `html/` and `src/` to update the tutorial.

## More
* "mkdocs serve" starts a http server listening on http://localhost:8000
  and updates the docs on change.
* Sometimes function names collide. These packages must be loaded _first_
  in "build". That way mlr overwrites these functions again, e.g. caret::train.
* The build caches the output of running the R commands in the cache/ directory.
  If your R setup has changed (e.g. new version of mlr), you should delete
  everything in the cache directory to make sure that the tutorial is
  regenerated with the new code.
