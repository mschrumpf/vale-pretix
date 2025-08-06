# vale-pretix

This repository contains a Vale configuration and style for writing the [pretix documentation](https://github.com/pretix/pretix-docs/). 

It is based on [vale-boilerplate](https://github.com/errata-ai/vale-boilerplate). 

## Installation

 1. Install [Vale](https://github.com/errata-ai/vale). 
    (Tested installing Vale from the official Arch Linux repositories. 
    Other installation methods may require some setup)
    
 2. Clone this repository ([vale-pretix](https://github.com/mschrumpf/vale-pretix)) to your machine. 
 
 3. Open a terminal **in the directory** to which you cloned this repository, for instance: 
    
``` bash
$ cd ~/vale-pretix/
```

 4. Install the Vale packages predefined in `.vale.ini` with the following command: 
 
``` bash
$ vale sync
```

## Usage

 1. Run commands from the [Vale CLI](https://vale.sh/docs/cli), for instance: 

``` bash
$ vale ~/pretix-docs/docs/guides/index.md
```

 2. Use the output to improve your contribution to the pretix docs or to facilitate your review process. 
 
 3. Remember that **you are smarter than Vale**. 
 Many of the rules have exceptions that cannot be reasonably defined in Vale. 
 Use your own judgement instead of fixing every single thing that Vale detects as a problem. 
 
## Contributing 

**Before you make any changes**, create a new branch to this repo. 
Once you have made your changes, submit a pull request. 
If you encounter any problems, create an issue on this repo. 

### Orthography

Orthograph errors come with a message such as: `Did you really mean 'pretix'?` 
If you encounter such an error, double-check that the word is spelled correctly. 
Edit `~/vale-pretix/styles/config/vocabularies/Docs/accept.txt` and add the word at the proper place in the alphabetical order. 
Use regular expressions to catch variations in capitalization and grammatical suffixes. 
Use the already existing entries as examples how to do this. 

If your file contains any orthographical errors that are not caught by Vale, edit `~/vale-pretix/styles/config/vocabularies/Docs/reject.txt` and add the word at the proper place in the alphabetical order. 

### Irrelevant messages 

It is normal and expected to get several irrelevant messages when using Vale on your text. 
If you get a message that is irrelevant for the individual case, but still relevant for the pretix docs as a whole, ignore it and move on. 
You may use `grep` or other command line tools to filter out irrelevant messages. 

If you encounter a `warning` or `error` message that is irrelevant for the pretix docs **as a whole**, check the end of the line to see which style that rule came from. 
For example, if the end of the line says `write-good.Passive`, then the style is called `write-good` and the rule is called `Passive`. 
If the message is from the `pretix` style, see below. 

If the message is from any other style, add a line to `.vale.ini` to ignore the rule in question. 
For instance, if you want to ignore the Contractions.yml rule from the Microsoft style, add: 

``` ini
Microsoft.Contractions = NO
```

Do **not** edit rules from packages. 
Any changes will be overridden the next time you update those packages. 

### Issues with rules in the `pretix` style 

If you encounter a `warning`, `error`, or `suggestion` message  from the `pretix` style, create an issue. 
You can also create a pull request instead and edit the rule in question. 
Refer to the [Vale docs](https://vale.sh/docs) and reference existing rules files to learn how to edit rules. 

### Issues in the text that are not detected by Vale 

If your text has an issue that is not detected by Vale, but you think it should be, create an issue. 
You can also create a pull request instead and add a new rule. 
Refer to the [Vale docs](https://vale.sh/docs) and reference existing rules files to learn how to create rules. 

If the issue is merely an orthographical error that is not caught by Vale, edit `~/vale-pretix/styles/config/vocabularies/Docs/reject.txt` and add the word at the proper place in the alphabetical order. 
