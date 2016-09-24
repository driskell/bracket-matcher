# Bracket Matcher package
[![OS X Build Status](https://travis-ci.org/atom/bracket-matcher.svg?branch=master)](https://travis-ci.org/atom/bracket-matcher)
[![Windows Build status](https://ci.appveyor.com/api/projects/status/rrsl2h7e0od26k54/branch/master?svg=true)](https://ci.appveyor.com/project/Atom/bracket-matcher/branch/master) [![Dependency Status](https://david-dm.org/atom/bracket-matcher.svg)](https://david-dm.org/atom/bracket-matcher)


Highlights and jumps between `[]`, `()`, and `{}`. Also highlights matching XML
and HTML tags.

Autocompletes `[]`, `()`, and `{}`, `""`, `''`, `“”`, `‘’`, `«»`, `‹›`, and
backticks.

Use <kbd>ctrl-m</kbd> to jump to the bracket matching the one adjacent to the cursor.
It jumps to the nearest enclosing bracket when there's no adjacent bracket,

Use <kbd>ctrl-cmd-m</kbd> to select all the text inside the current brackets.

Use <kbd>alt-cmd-.</kbd> to close the current XML/HTML tag.

---
### Configuration

Matching brackets and quotes are sensibly inserted for you. If you dislike this
functionality, you can disable it from the Bracket Matcher section of the
Settings view (<kbd>cmd-,</kbd>).

#### Smart Quotes

You can toggle whether English/French style quotation marks (`“”`, `‘’`, `«»`
and `‹›`) are autocompleted via the *Autocomplete Smart Quotes*  setting in the
settings view.

#### Custom Pairs

You can add or remove matching pairs from Bracket Matcher at any time. You can do so either Globally via the Settings view (<kbd>cmd-,</kbd>) or at the Scope level via `config.cson` (<kbd>cmd-shift-p</kbd> + "config"). Changes take effect immediately.

* <b>Add Pairs</b> - Comma-separated pairs to append to package defaults.
  * ie: `<:>, %:%, @:@`
* <b>Exclude Pairs</b> - Comma-separated pairs to remove from package defaults.
  * ie: `':', [:]`

###### config.cson
In addition to Global configs, you are able to add scope-specific modifications to Atom in `config.cson`. This is especially useful for editor rule changes specific to each language. Example:
```
".rust.source":
  "bracket-matcher":
    addPairs: [
      "<:>"
    ]
    excludePairs: [
      "':'"
    ]
```
