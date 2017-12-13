# valestyles
This repo contains some modified grammatical styles from Vale and some instrustions for setting it up with Atom text editor. Vale is "A syntax-aware linter for prose built with speed and extensibility in mind"

1. Clone this repo into your home directory `git clone https://github.com/airbornelamb/valestyles.git ~/`
2. Download the vale release https://github.com/ValeLint/vale/releases
3. Extract the vale release and move the binary to your path. e.g. /usr/local/bin/vale
4. Install atom from https://atom.io/
5. Install the necessary atom packages from terminal `apm install linter linter-just-say-no atomic-vale`
6. Open atom and set the path to your vale installation
7. Create a .vale file in your home directory and fill it with the below contents

```
# Core settings
StylesPath = /home/PUTYOURUSERNAMEHERE/valestyles
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
