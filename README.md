# sent is a simple plaintext presentation tool.

sent does not need latex, libreoffice or any other fancy file format, it uses
plaintext files to describe the slides and can include images via farbfeld.
Every paragraph represents a slide in the presentation.

The presentation is displayed in a simple X11 window. The content of each slide
is automatically scaled to fit the window and centered so you also don't have to
worry about alignment. Instead you can really concentrate on the content.

## Patches

As this is my own build, I've added some patches to it.

- [inverted-colors](https://tools.suckless.org/sent/patches/inverted-colors/)
- [progress-bar](https://tools.suckless.org/sent/patches/progress-bar/)

## Dependencies

You need Xlib and Xft to build sent and the farbfeld[0] tools installed to use
images in your presentations.

## Demo

To get a little demo, just type

```bash
$ make && ./sent example
```

You can navigate with the arrow keys and quit with `q`.

## Usage

```bash
$ sent [FILE]
```

If FILE is omitted or equals `-`, stdin will be read. Produce image slides by
prepending a `@` in front of the filename as a single paragraph. Lines starting
with `#` will be ignored. A `\` at the beginning of the line escapes `@` and
`#`. A presentation file could look like this:

```text
sent
	
@nyan.png
	
depends on
- Xlib
- Xft
- farbfeld

sent FILENAME
one slide per paragraph
# This is a comment and will not be part of the presentation
\# This and the next line start with backslashes

\@FILE.png

thanks / questions?
```

## Development

sent is developed at [http://tools.suckless.org/sent](http://tools.suckless.org/sent)

0: [http://tools.suckless.org/farbfeld/](http://tools.suckless.org/farbfeld/)
