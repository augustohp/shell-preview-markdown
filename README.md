# Preview Markdown files from the Shell

How is your markdown file going to be rendered? This receives a file and opens
it in a browser for you.

    $ preview-markdown --from README.md
    /tmp/markdown-preview_README.html
    $ preview-markdown --output email.rtf --from email.md
    email.rtf

The output of the program is always the file generated for preview. By default,
a browser is opened - if [Lynx][] is present we prefer it. HTML is preferred as
well, but any format supported by [Pandoc][] can be used as output - use file
extensions to denote them.

    Usage: preview-markdown [options]
           preview-markdown --from README.md
           preview-markdown --from letter.md --output letter.pdf

    Will generate an HTML preview of a markfown <file> and open it inside a
    browser (Lynx if existing).

    Options:
        -f <path>, --from       The markdown file to generate a preview from.
                                Default: README.md
        -o <path>, --output     The output file which will hold the preview.
        -b, --browser           Prefer a real browser (e.g: Firefox) instead of
                                Lynx (if it is available).
        -j, --just-preview      Avoids opening the browser, just generates the
                                preview file as HTML.
        -v, --version           Prints version of the program.
        -h, --help              This help message.
    Environment variables:
        PM_CSS_URL              The CSS file to be used for the rendered mardown.
                                Default: GitHub markdown style
        PM_MARKDOWN_EXTENSION   File extension to remove from the generated
                                preview file.
                                Default: md
        PM_DEFAULT_INPUT        If no options are passed, which file should be
                                used as input?
                                Default: README.md

    Report issues on https://github.com/augustohp/preview-markdown.
    Contact me over augusto.hp [at] gmail [dot] com.

## Installation

You can put the single file `preview-markdown` inside your *BIN* directories or
declare a new `PATH` to where it is. If you want this easy, you can also use the
line below:

    sh <(curl -sSL http://git.io/sinister) -u https://git.io/preview-markdown

When you execute this, [Pandoc][] may be installed in the first execution.
command - only supported on OSX.

## LICENSE

MIT

[Lynx]: http://lynx.browser.org/ "Lynx text browser"
[Pandoc]: http://pandoc.org/ "A universal document converter"
