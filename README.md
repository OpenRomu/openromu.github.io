# OpenRomu Website

This repository contains the static websites for OpenRomu
It uses a template system, so dist folder has to be built using NodeJS.

## Build website

Create dist folder and pages by running

    npm run build
    or
    yarn build

## Upload to gh-pages

Since dist folder is in a subfolder and gh-pages requires pages to be at root,
we create a branch called "gh-pages" to host pages only.
We delete and recreate branch when we need to update the website using:

    git branch -D gh-pages
    git checkout --orphan gh-pages
    rm -r templates/ node_modules/ *.* && mv dist/* . && rm -r dist
    git add . && git commit -m "published pages" && git push origin gh-pages -f