# pure-gnugo

A purescript binding to gnugo

## Run locally

First build [wasm-gnugo](https://github.com/TristanCacqueray/wasm-gnugo/) in `../`
Then symlink `ln -s ../../wasm-gnugo/ dist/wasm-gnugo`

## Update pages

The application is available at [https://tristancacqueray.github.io/pure-gnugo/](https://tristancacqueray.github.io/pure-gnugo/).
To update the pages, run:

```
spago build && rm -Rf dist/ && parcel build --public-url /pure-gnugo/ src/index.html
git checkout pages && git rm src.* && rsync -a dist/ $(pwd)/ && git add src.* && git commit -a --amend -m "Add build" && git push -f origin pages
```
