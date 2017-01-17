# JavaScript Semifour-Standard Style
[![npm][npm-image]][npm-url]
[![downloads][downloads-image]][downloads-url]

### Semicolons and wider indents

All the goodness of [feross/standard] with semicolons and four-space indents

## Install

```bash
npm install semifour-standard
```

## Rules

Importantly:

- **semicolons**
- **four-space indents**
- Check [feross/standard] for the rest of the rules.


## Usage

The easiest way to use JavaScript Semifour-Standard Style to check your code is to install it
globally as a Node command line program. To do so, simply run the following command in
your terminal (flag `-g` installs `semifour-standard` globally on your system, omit it if you want
to install in the current working directory):

```bash
npm install semifour-standard -g
```

After you've done that you should be able to use the `semifour-standard` program. The simplest use
case would be checking the style of all JavaScript files in the current working directory:

```
$ semifour-standard
Error: Use JavaScript Semifour-Standard Style
  lib/torrent.js:950:11: Expected '===' and instead saw '=='.
```

### What you might do if you're clever

1. Add it to `package.json`

  ```json
  {
    "name": "my-cool-package",
    "devDependencies": {
      "semifour-standard": "*"
    },
    "scripts": {
      "test": "semifour-standard && node my-normal-tests-littered-with-semicolons.js"
    }
  }
  ```

2. Check style automatically when you run `npm test`

  ```
  $ npm test
  Error: Code style check failed:
    lib/torrent.js:950:11: Expected '===' and instead saw '=='.
  ```

3. Never give style feedback on a pull request again! (unless it's about semicolons)

### Custom Parser
To use a custom parser, install it from npm (example: `npm install
babel-eslint`) and add this to your package.json:

```json
{
  "semifour-standard": {
    "parser": "babel-eslint"
  }
}
```

### [Vim](http://www.vim.org/)

Install **[Syntastic][vim-1]** and add these lines to `.vimrc`:

```vim
let g:syntastic_javascript_checkers=['standard']
let g:syntastic_javascript_standard_exec = 'semifour-standard'
```

For automatic formatting on save, add these two lines to `.vimrc`:

```vim
autocmd bufwritepost *.js silent !semifour-standard % --fix
set autoread
```

[vim-1]: https://github.com/scrooloose/syntastic

### Ignoring files

Just like in `standard`, The paths `node_modules/**`, `*.min.js`, `bundle.js`, `coverage/**`, hidden files/folders
(beginning with `.`), and all patterns in a project's root `.gitignore` file are
automatically excluded when looking for `.js` files to check.

Sometimes you need to ignore additional folders or specific minfied files. To do that, add
a `semifour-standard.ignore` property to `package.json`:

```json
"semifour-standard": {
  "ignore": [
    "**/out/",
    "/lib/select2/",
    "/lib/ckeditor/",
    "tmp.js"
  ]
}
```

### Make it look `snazzy`
If you want prettier output, just install the [`snazzy`](https://github.com/feross/snazzy) package and pipe `semifour-standard` to it:

```bash
$ semifour-standard --verbose | snazzy
```

See [feross/standard] for more information.

[npm-image]: https://img.shields.io/npm/v/semifour-standard.svg?style=flat-square
[npm-url]: https://npmjs.org/package/semifour-standard
[downloads-image]: https://img.shields.io/npm/dm/semifour-standard.svg?style=flat-square
[downloads-url]: https://npmjs.org/package/semifour-standard
[feross/standard]: https://github.com/feross/standard
