# Site

Jekyll Based Personal Blog for Naysawn.com

## Drafts & Private content

This blog started out as a way to write down private notes. So not everything that's written should be published. 

Running the site locally should be done by telling jekyll to serve up drafts & unpublished content. `bundle exec jekyll serve -w --unpublished -D`. 

To compile frontend assets, run `yarn` or `yarn install`

## Deployment

Hosting is on Github pages. It's quite hacky to host on github pages with the free version with plugins and whatnot that we're using. This is what's set up. 

1. There's two braches `main` for writing content, `prod-build` for deployment
2. There's two remotes - `origin` going to a private repository on Github, `production` - going to a public repository on Github
3. "Building" is done in a pretty hacky way that currently works. 
  1. We generate the static site using `JEKYLL_ENV=production bundle exec jekyll build --destination prod-build` in the main branch. 
  2. Then change to the `prod-build` and copy everything in the folder to the root directory. 
  3. Then push the `prod-build` branch to production. 
  4. Finally on Github, go to the github pages tab here re-enter `naysawn.com` as where the site is hosted for the deployment to complete. 