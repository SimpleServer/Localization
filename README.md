SimpleServer Translations
=========================
Every message SimpleServer displays in-game can be localized (i.e. translated) in any language.

### Currently available languages
* English (en)
* German (de)
* Swedish (sv)

## Changing the language
The preferred language can be set in the *simpleserver.properties* file with the `serverLanguage` option. You need to use the language codes listed above (e.g. `en`).

## Translating
SimpleServer is open and can be translated by anyone.
We encourage you to contact us if you are willing to add a new language or work on an abandoned one.

### Requirements
* You should read and understand English fluently.
* You obviously need a good knowledge of the language you want to translate to. Only using Google translate is **not** OK ;)
* You should be willing to learn the very basics of [git](http://en.wikipedia.org/wiki/Git_(software\)) (commiting, pushing and pulling changes)

### Contacting us
* Talk with us on IRC: irc.euirc.net#SimpleServer ([webchat](http://www.mibbit.com/?server=irc.euirc.net&channel=%23SimpleServer))
* Send us a [private message](https://github.com/inbox/new/sadimusi)
* Write in our [forum thread](http://www.minecraftforum.net/topic/309373-software-simpleserver-wrapper-813-166/)

### Setting up your workspace
* Create a free GitHub account [here](https://github.com/signup/free) (if you don't have one already).
* Set up git on your computer. There are good tutorials in the GitHub [help pages](http://help.github.com/set-up-git-redirect).
* [Installation](https://github.com/SimpleServer/SimpleServer/wiki/Installation)
* Clone the [localization repository](https://github.com/SimpleServer/Localization) into your SimpleServer folder. To do that simply navigate to said folder using [cd](http://en.wikipedia.org/wiki/Cd_(command\)) and then execute <br>
```
git clone git@github.com:SimpleServer/Localization.git
```
* Rename the newly created folder *Localization* to *translations*

### Add a new language
* Locate a file called *template.json* in your *translations* folder
* Copy this file and rename it to *language_code.json* where *language_code* is the two-letter code of your language according to [ISO 639-1](http://en.wikipedia.org/wiki/List_of_ISO_639-1_codes).

### Editing a language file
The language files contain a [JSON](http://www.json.org/) formatted dictionary where the keys are the original English messages and the value is the translated version.

Each line looks like this:
```
"Original English message" : "Translated message",
```

In order to translate a message simply change the right part to the specific translation.

### Special message components
You will often encounter `%s`, `%d` or other letters preceded by a `%` symbol. These are [placeholders](http://download.oracle.com/javase/6/docs/api/java/util/Formatter.html) for variable game information (e.g. player names) which will be inserted at the specified locations. Translations must have exactly the same number and order of these symbols!

If a message contains a quote character (`"`) it must be preceded by a backslash (`\`) to comply with the [JSON](http://www.json.org/) format.

### Testing
If you followed the above instructions you can test your translation by simply setting the `serverLanguage` in the *simpleserver.properties* file to your language code and running the server. Make sure the *translations* folder is at the same location as the main SimpleServer files (e.g. *SimpleServer.jar*). 
The translations file can be reloaded at any time by using the `reload` command.

### Submitting
The translations are submitted via [git](http://en.wikipedia.org/wiki/Git_(software\)). Navigate your git console into the *translations* folder (using [cd](http://en.wikipedia.org/wiki/Cd_(command\)) again). Then execute the following commands:
```
git pull origin master
git add .
git commit -m 'Here is a short message about your changes'
git push origin master
```

### Updates
Whenever SimpleServer's code gets updated there might be new untranslated messages. These get added to the translation files automatically, you just have to translate them. To get them use the `git pull origin master` command again. The new messages will be at the very bottom of the file.
