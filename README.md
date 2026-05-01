# GitHub Hosted Memorial Site
Updated with newer code and tweaks so it works well in 2025-26.
This fork has been updated to not require the gh-pages branch.


## Local Build Setup on a *nix Machine

```bash
# install dependencies
$ yarn install

# generate resized and normalised images
$ node index.js

# serve with hot reload at localhost:3000
$ yarn dev

# generate static project
$ yarn generate
```

## Building your own
To build your own, fork this repository, then make changes to:
* `nuxt.config.js` - Change the 2 variables at the top with your loved ones name and their dates from and to.
* `assets/frontimage.jpg` - Replace with your own image, this is the image that shows on the front page, image should be 244px by 292px.
* `pages/*` - Change the details in the pages to match what you want them to say.
* `static/CNAME` - Replace with your own custom domain
* `layouts/default.vue` - You can change the scss here, if you want to change the main colours used they are near the top of this file.
* `assets/images/` - Drop all the images you want to show in the gallery in this folder - As part of the github action it will rename the images that have problematic names, resize images to a max width of 1800px, and will create thumbnail versions to ensure the gallery is optimised. The original files in the `images` directory are not touched.

## Putting Live
* Make sure you have GitHub actions running
* Make sure you have set `static/CNAME` to what it needs to be
* On your nameservers point a CNAME from your custom domain to `<username>.github.io`
* Once the Github action runs it should all be setup, but if not, go to your repos `Settings / Options`, scroll down to `GitHub Pages` and for source select `Branch: gh-pages` - don't do this the cd.yml sorts this out.

Now, any time you make a change to the source and push the change, GitHub actions should pick up the change and run a workflow that generates the static files, and fixes image names.