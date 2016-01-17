
quaint-emoji
============

Use emojis in your Quaint documents.

The svg/png emojis provided by `quaint-emoji` are the excellent ones
designed by [Emoji One](http://emojione.com/)


## Install

    npm install quaint-emoji -g


## Sample configuration

This configuration entry must be added in the `plugins` field of
`quaint.json`:

```json
"emoji": {
  "method": "svg",
  "fuzzy": true
}
```

## Sample use

```quaint
The :cat: is in the :top_hat:!
```


## Rules

### `:name:`

Inserts the emoji with the given name. This must be an exact
match. You can search the codes [here](http://emoji.codes/).

If the `fuzzy` options is enabled, `quaint-emoji` will search for some
emoji that matches what you have written. For instance, there is no
`:tree:` emoji, but with `fuzzy` enabled, you will still get
something, like `:evergreen_tree:`.


### `!! name`

Same as `:name:`.


## Options

### `fuzzy`

(default: false)

If true, if there is no emoji with the exact name you have given,
`quaint-emoji` will search for one that has a name matching what you
have written.

For instance, there is no `:tree:` emoji, but with `fuzzy` enabled,
you will still get something, like `:evergreen_tree:`. If it's close
enough to what you want, at least that saves some time searching ;)

To match :x:, fuzzy tries to find, in this order:

1. An emoji that starts with `x_`
2. An emoji that ends with `_x`
3. An emoji that starts with `x`
4. An emoji that ends with `x`

If there are multiple matches at one step, which one is picked is
arbitrary and might change in a future version (but always towards a
better match).

### `method`

(default: `"svg"`)

This option controls which emoji set to show, which image format to
use, and can take the following values:

* `"svg"`: use `svg` icons from [Emoji One](http://emojione.com/) (served through cdnjs)
* `"png"`: use `png` icons from [Emoji One](http://emojione.com/) (served through cdnjs)
* `"unicode"`: insert unicode code points directly

### `operator`

(default: `"!!"`)

The prefix operator to use for emojis, or `null`.

