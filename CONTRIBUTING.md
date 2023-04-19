# Contribution Guidelines

Contribution and suggestions are welcome! Please ensure your pull request adheres to the following guidelines:

* This is an open source compilation, please check that the license of the software is suitable.
* Please search previous suggestions before making a new one, as yours may be a duplicate.
* Please make an individual pull request for each suggestion.
* Use the following format: 
    * ``[PACKAGE](LINK)``
        * ``[CLASS](LINK) - DESCRIPTION: [`example`](reprex/class.md)``
* Add the package to the table of content.
* Keep descriptions short and simple.
* The example should show a concise representation of printed output. Add text if necessary.
* Provide a [reprex](https://reprex.tidyverse.org/) that demonstrates usage of the class in a new file `class.md` in the [`reprex/`](./reprex) directory, see below.
    * If you're editing the list on GitHub, it's okay to paste the reprex as a comment to the pull request.
* Omit the full stop/period after the example.
* Order projects alphabetically within each category.
* Check your spelling and grammar.
* New categories, or improvements to the existing categorisation are welcome.

Thank you for your suggestions!


## How to create a reprex

A [reprex](https://reprex.tidyverse.org/) is a reproducible example that demonstrates the usage of a class.

* Review [the units example](reprex/units.md) and [others](./reprex) for inspiration.
* Open a new file.
* Write code.
* Copy the code to the clipboard.
* Run `reprex::reprex()`.
* Paste the result into a new `reprex/class.md` file (preferred) or as a comment to the pull request.
