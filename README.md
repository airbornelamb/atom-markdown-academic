# atom-markdown-academic

After following all the instructions you will have a good setup for academic writing using Atom with Zotero/Bibtex integration, prose linting, and Pandoc support.

## Setup

1. Install atom from https://atom.io/
2. Install necessary atom packages
  ```bash
  apm install zen atom-clock atomic-vale autocomplete-bibtex busy-signal file-icons intentions linter linter-just-say-no linter-proselint linter-ui-default linter-write-good wordcount
  ```
3. Install Zotero and better bibtex
  + Download and install Zotero and browser extension [download here](https://www.zotero.org/download/)
  + and Better Bibtex plugin, which you can [download here](https://github.com/retorquere/zotero-better-bibtex/releases/) and use these [install instructions](https://github.com/retorquere/zotero-better-bibtex/wiki/Installation) to set it up for periodic export to a .bib file
4. Setup atom packages
  + Setup zen: check fullscreen, check softwrap, set "show wordcount: right"
  + Setup autocomplete-bibtex: set the "Bibtex" setting to the .bib file which is exported by zotero better bibtex
5. Install Pandoc [download here](http://pandoc.org/installing.html)

Congratulations! You should now be able to fire up zotero and open your web browser and save sources with a single click. Then better-bibtex will export everything periodically to a .bib file which will be read by Atom. You can begin typing your paper in Markdown and then type "[@author]" and press the Tab key for source completion. Check out [vim-academic](https://github.com/airbornelamb/vim-academic/blob/master/README.md#conversion) for sample commands and files to use pandoc to convert to docx.

---

## Bonus: Setting up Vale

This repo contains some modified grammatical styles from Vale and some instrustions for setting it up with Atom text editor. Vale is "A syntax-aware linter for prose built with speed and extensibility in mind".

1. Clone this repo into your home directory 
  ```bash
  git clone https://github.com/airbornelamb/atom-markdown-academic.git ~/
  ```
2. Download the vale release https://github.com/ValeLint/vale/releases
3. Extract the vale release and move the binary to your path. e.g. /usr/local/bin/vale
6. Open Atom and configure the atomic-vale package by setting the path to your vale installation
7. Create a .vale file in your home directory and fill it with the below contents

```
# Core settings
StylesPath = /home/PUTYOURUSERNAMEHERE/atom-markdown-academic
MinAlertLevel = warning # suggestion, warning or error

# Global settings (applied to every syntax)
[*]
# List of styles to load
BasedOnStyles = vale, proselint, write-good, 18F, MailChimp, Middlebury, OpenStack, PlainLanguage
# Style.Rule = {YES, NO} to enable or disable a specific rule
vale.GenderBias = NO
# You can also change the level associated with a rule
vale.Hedging = error


# Syntax-specific settings
# These overwrite any conflicting global settings
#[*.{md,txt}]
```

Should be good to go. You will also be able to lint files from the command line with `vale FILENAME`
