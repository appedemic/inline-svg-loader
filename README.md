# html loader for webpack

Just a quick hack for now, will improve on it soon...

It converts `<svg src="some.svg">` to an `<svg>` element with inlined contents of the file. The file is resolved through webpack.

Currently it only works as loader on top of `html-loader` and the regex is poor too.

You will need to setup loaders something like this:
``` javascript
{
  { test: "\.html$", loader: "inline-svg-loader!html-loader?attrs[]=svg:src" },
  { test: "\.svg$", loader: "raw-loader" }
}
```
