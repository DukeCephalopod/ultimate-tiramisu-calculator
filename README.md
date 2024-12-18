# ultimate-tiramisu-calculator

Fan copy of James Hoffmann's Ultimate Tiramisu Calculator.

`calculator.html` is the script that James puts on his site; the site builder wraps it
in the containing page. Enough of the page to give us CSS (and a bit of header) is
copied into `pre.html.part` (with closing tags in `post.html.part`).

To assemble the three files into a loadable
webpage, `cat` them together, packaged for convenience as

```
./Taskfile build
```

Open the resulting `index.html` in your browser directly.

To automate those changes, if you have `entr` and a node installation, you can run

```
./Taskfile dev
```

To automatically

- Notice changes to calculator.html and the part files and rebuild index.html, and
- Serve index.html from a small server that inject hot-reloading

If you just want the "automatic rebuild" but don't mind manually reloading your browser,
you can run just this line, if you have [entr](https://github.com/eradman/entr)
installed:

```
find . -maxdepth 1 -type f -name '*html*' -not -name 'index*' | entr ./Taskfile build
```
