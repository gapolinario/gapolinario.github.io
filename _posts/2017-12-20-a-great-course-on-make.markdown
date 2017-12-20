---
layout: post
title:  "A great course on Make"
date:   2017-12-20 12:00:00 -0200
categories: linux
---

Software Carpentry has [this][carpentry-make] great introductory
course on the workings of make and makefile, including
some good programming practices, such as automatic documentation.
The course follows the analysis of [Zip's Law][zipf] on some
free books.

To start:

```Makefile
target : input
    command
```

Some make standard variables: `$@` refers to the target,
`$^` to all input variables, and `$<` to the first input variable.
`%` is a matched variable.

`@` at the beginning of a command shows the result of a command,
but not the command itself.

`.PHONY` means a dumb variable, unrelated to any
files or folders in the main folder.

A file called `config.mk` holds the first variable definitions.

```Makefile
# Count words script.
COUNT_SRC=wordcount.py
COUNT_EXE=python $(COUNT_SRC)

# Plot word counts script.
PLOT_SRC=plotcount.py
PLOT_EXE=python $(PLOT_SRC)

# Test Zipf's rule.
ZIPF_SRC=zipf_test.py
ZIPF_EXE=python $(ZIPF_SRC)
```
First, we define a number of variables.
`wildcard` and `patsubst` are `makefile` commands, but I don't know
if they support regex.

```Makefile
include config.mk

TXT_DIR=books
TXT_FILES=$(wildcard $(TXT_DIR)/*.txt)
DAT_FILES=$(patsubst $(TXT_DIR)/%.txt, %.dat, $(TXT_FILES))
PNG_FILES=$(patsubst $(TXT_DIR)/%.txt, %.png, $(TXT_FILES))
RESULTS_FILE=results.txt
ZIPF_DIR=zipf_analysis
ZIPF_ARCHIVE=$(ZIPF_DIR).tar.gz
```

Next, we display the contents of the `Makefile` file.
The first rule is usually `all`,
we can simply run `make` or `make all`.

```Makefile
## all         : Generate archive of code, data, plots and Zipf summary table.
.PHONY : all
all : $(ZIPF_ARCHIVE)

$(ZIPF_ARCHIVE) : $(ZIPF_DIR)
	tar -czf $@ $<

$(ZIPF_DIR): Makefile config.mk $(RESULTS_FILE) \
             $(DAT_FILES) $(PNG_FILES) $(TXT_DIR) \
             $(COUNT_SRC) $(PLOT_SRC) $(ZIPF_SRC)
	mkdir -p $@
	cp -r $^ $@
	touch $@

## results.txt : Generate Zipf summary table.
$(RESULTS_FILE) : $(DAT_FILES) $(ZIPF_SRC)
	$(ZIPF_EXE) $(DAT_FILES) > $@

## dats        : Count words in text files.
.PHONY : dats
dats : $(DAT_FILES)

%.dat : $(TXT_DIR)/%.txt $(COUNT_SRC)
	$(COUNT_EXE) $< $@

## pngs        : Plot word counts.
.PHONY : pngs
pngs : $(PNG_FILES)

%.png : %.dat $(PLOT_SRC)
	$(PLOT_EXE) $< $@

## clean       : Remove auto-generated files.
.PHONY : clean
clean :
	rm -f $(DAT_FILES)
	rm -f $(PNG_FILES)
	rm -f $(RESULTS_FILE)
	rm -rf $(ZIPF_DIR)
	rm -f $(ZIPF_ARCHIVE)

## variables   : Print variables.
.PHONY : variables
variables:
	@echo TXT_DIR: $(TXT_DIR)
	@echo TXT_FILES: $(TXT_FILES)
	@echo DAT_FILES: $(DAT_FILES)
	@echo PNG_FILES: $(PNG_FILES)
	@echo ZIPF_DIR: $(ZIPF_DIR)
	@echo ZIPF_ARCHIVE: $(ZIPF_ARCHIVE)

.PHONY : help
help : Makefile
	@sed -n 's/^##//p' $<
```

And that's it, good automation.

[carpentry-make]: http://swcarpentry.github.io/make-novice/
[zipf]: https://en.wikipedia.org/wiki/Zipf%27s_law
