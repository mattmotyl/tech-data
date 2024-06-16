# Tech Data

## Installation Notes 

### Ensure you have `git` installed

`which git`

If you don't, install git.

### Install `hugo`

https://gohugo.io/installation/

### Clone this Repo

`git clone https://github.com/mattmotyl/tech-data.git tech-data`

### Clone the Lotus Docs Customization Repo

This is a fork of [Lotus Docs](https://lotusdocs.dev/docs/quickstart/) with customizations specific to this project.

`git clone https://github.com/gbdubs/lotusdocs-tech-data themes/lotusdocs`

## Development Workflow

- run `hugo server --disableFastRender`
- navigate to [http://localhost:1313](http://localhost:1313)
- create pages using `hugo new docs/my-page.md`
- edit markdown files in `content/docs/...`, saving auto-refreshes browser
- commit changes using git and push them up
    - deploy to github pages kicks off immediately
    - track deploy process in the 'actions' tab
    - site is published when action completes - clear cache to check.