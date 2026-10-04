# Source backup

`bundle.pretty.js` is the readable, editable version of the whole app (React + Firebase + the patch-bay code).
It is the source of truth: the app's own code is the section starting around `function $R` (search for
"Select nothing / clear this field" or "PRECISION SOUND" to find your way around).

To rebuild the deployed file after editing:

    npm install esbuild
    npx esbuild source/bundle.pretty.js --minify --target=es2020 --outfile=bundle.js

Then bump the `?v=` number on the script tag in `index.html` (cache-busting) and the build marker string
(search for "UTC") so you can see the new version has loaded.
