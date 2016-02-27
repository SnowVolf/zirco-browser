Before starting a translation, you must agree that your work will be released under the same license as Zirco, e.g. [GPL version 3](http://www.gnu.org/copyleft/gpl.html). Also do not forget that a software translation is not a one-shot work, and that new translations may be needed after your initial work.

Translations are done is a language-specific XML file. A single translation string look like this :
```
<string name="Main.MenuAddBookmark">Add bookmark</string>
```

Where the part in the name parameter (here `Main.MenuAddBookmark`) is the string key, which you must leave unchanged, and the part between `<string …>` and `</string>` the translated string.

# Translation steps #
## Download the last reference language file ##

http://zirco-browser.googlecode.com/svn/trunk/res/values/strings.xml

Then select “Save as...” in your browser, and save it where you want on your computer.

## Translate ##

Open the file you downloaded with a decent text editor (hint: Windows Notepad is **NOT** a decent text editor). Do not change the default encoding (UTF-8) and the default line breaks (Unix style).

Translate every required strings.

### Specials cases ###
#### String-arrays ####
Do not translate anything within a `<string-array>` tag.

#### Apostrophe ####
Apostrophes must be preceded by a “\” character.

Example:
```
<string name="Main.VndErrorTitle">Impossible d\'ouvrir l\'url</string>
```

#### Formatted strings ####
Some strings may contains dynamic values, filled at runtime by the application. The place where the dynamics values are inserted in the string a represented by a `%s`, `%1$s` `%2$s`, etc. You must include the original `%s`-type in your translation, at the appropriate place.

Example:
```
<string name="Commons.HistoryBookmarksFailedMessage">Error message: %s.</string>
```

Will be displayed to the user as `Error message: unable to read bookmarks.` for instance.

```
<string name="HttpAuthenticationDialog.DialogTitle">Sign in to %1$s - %2$s</string>
```

When there is several values to dynamically change in a single string, the `%s` part change to `%1$s`, `%2$s`, etc. You may change the order of the `%s` in your translation, if its make sense in you language, e.g. you can do something like:

```
<string name="HttpAuthenticationDialog.DialogTitle">SomeText %2$s AnotherText %1$s</string>
```

#### Search URLs ####
Search URLs can be customized by language. For instance, the default search URLs:

```
http://www.google.com/m?hl=en&amp;gl=us&amp;client=ms-null&amp;source=android-browser-key&amp;q=%s
http://en.wikipedia.org/w/index.php?search=%s&amp;go=Go
```

Are customized in French to:

```
http://www.google.com/m?hl=fr&amp;gl=fr&amp;client=ms-null&amp;source=android-browser-key&amp;q=%s
http://fr.wikipedia.org/w/index.php?search=%s&amp;go=Go
```

So Google search result and Wikipedia results will use french.

#### Misc. ####
  * Use `&#8230;` instead of writing three points (`...`)
  * Never change
```
<string name="DATE_FORMAT_ISO8601">yyyy-MM-dd\'T\'HH:mm:ss.SSS</string>
```

## Submit your translation ##

Either send me an e-mail, with your modified file and the language you translated, or open an [issue](http://code.google.com/p/zirco-browser/issues/list) and post your file there.