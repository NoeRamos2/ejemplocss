CSS3
====

The most complete CSS support for Sublime Text 3.

## Features

* __Absurdly Complete__: I basically mined the entire set of draft specs
  and supported everything. Some of this stuff won't be implemented in browsers
  for *years*. With a few exceptions, if it's in the spec, it's supported.
* __Productive__: Full set of completions for every property, including many
  prefixed properties. W3C Validation.
* __Modern__: Bad, old CSS is flagged. Unnecessarily prefixed properties aren't
  highlighted. Catches lots of mistakes.
* __Faithful__: Follows the spec extremely closely, with minor deviations that
  encourage a few best practices ([see below](https://github.com/y0ssar1an/CSS3#best-practices)).

## Before & After

![before and after 1](https://github.com/y0ssar1an/CSS3/raw/dev/screenshots/before_and_after1.png)
![before and after 2](https://github.com/y0ssar1an/CSS3/raw/dev/screenshots/before_and_after2.png)

## Installation

This package replaces my previous CSS3_Syntax plugin. This is a billion times
better :)

1. [Install Package Control](https://sublime.wbond.net/installation)
2. Install CSS3

    | Platform | Install Command                                                      |
    | -------- | -------------------------------------------------------------------- |
    | Mac      | `cmd+shift+p`&nbsp;&nbsp; → Package Control: Install Package → CSS3  |
    | Linux    | `ctrl+shift+p` → Package Control: Install Package → CSS3             |
    | Windows  | `ctrl+shift+p` → Package Control: Install Package → CSS3             |

3. (Recommended) Disable the default CSS package

    | Platform | Disable Command                                                      |
    | -------- | -------------------------------------------------------------------- |
    | Mac      | `cmd+shift+p`&nbsp;&nbsp; → Package Control: Disable Package → CSS   |
    | Linux    | `ctrl+shift+p` → Package Control: Disable Package → CSS              |
    | Windows  | `ctrl+shift+p` → Package Control: Disable Package → CSS              |

    ![disabling the default CSS package](https://github.com/y0ssar1an/CSS3/raw/dev/screenshots/disable_default.gif)

    Make sure you don't have any open files set to the default CSS syntax (bottom-right)
    or you may get an error message.

    *Warning: may break other CSS plugins*

4. (Recommended) Disable CSS completions in Emmet

    If you have Emmet installed, its completions will drown out the completions
    offered by this package. You can disable Emmet completions by adding these
    two lines to your Emmet Package settings.

    ```
    "show_css_completions": false,
    "disable_tab_abbreviations_for_scopes": "source.css"
    ```

5. (Recommended) Set CSS3 as the default language for `.css` files
    * Open a `.css` file.
    * View → Syntax → Open all with current extension as... → CSS3

    ![setting CSS3 as default](https://github.com/y0ssar1an/CSS3/raw/dev/screenshots/set_default.gif)

    *Warning: may break other CSS plugins*

## Best Practices

* [End every property declaration with a semicolon](https://google.github.io/styleguide/htmlcssguide.xml?showone=Declaration_Stops#Declaration_Stops).
* [Put a space after the colon in a property declaration](https://google.github.io/styleguide/htmlcssguide.xml?showone=Property_Name_Stops#Property_Name_Stops)
* [Always use quotes in `url()`](https://drafts.csswg.org/css-values/#urls)

## Known Issues

1. __Within nested code blocks, like inside a @media query, if the first
selector starts with a letter, it will not be highlighted.__

![nested selector bug and workarounds](https://github.com/y0ssar1an/CSS3/raw/dev/screenshots/nested_selector_bug.png)

This is an annoying limitation of the Sublime Text syntax highlighting
system. It can't recursively match curly braces across multiple lines. In
this case, the first nested selector is mistaken for a property, which
doesn't match. I went through three or four rewrites before I arrived at the
current design, which is the least fragile and most predictable that I know.
Other CSS highlighters, including my previous CSS3_Syntax and the Default CSS
bundle, have the same problem, but are much easier to break. If this bugs you
like it bugs me, two simple workarounds are shown above.

## Help Me Out!

If you think something's missing, make sure you're not asking for something
on [this list of bad CSS properties](https://gist.github.com/y0ssar1an/bb95223148e486acbe7a#file-bad_css).
If it's not on that list, open an issue and I'll investigate. I'll be monitoring
the specs as they're updated on [the W3C feed](https://www.w3.org/Style/CSS/current-work.en.html),
but I still need your help. Let's keep bad code out of the Web!
