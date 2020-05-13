# BookNuggets V2
This is the repository supporting the new BookNuggets GitHub Pages site.

## About
Being relatively new to web development, I found this an excellent opportunity to develop my skills by use GitHub pages and Jekyll to re-design my book summary site, BookNuggets. I will be documenting my process for developing the site here.

## Setup
We need to install Jekyll and Ruby (which Jekyll is built on). I used the instructions from the [Jekyll website](https://jekyllrb.com/docs/installation/windows/):

1. Install the [Ruby Installer](https://rubyinstaller.org/downloads/).
2. Check "Run `ridk install` in the final dialog box of the installation to install `gem`.
3. Install Jekyll and Bundler using the command: `gem install jekyll bundler`
4. Check that Jekyll is installed properly using the command: `jekyll -v`

Then, navigate to a target directory and run the following command in Command Prompt to create a folder (with the name `FOLDER_NAME`) containing all the required files for the site:

```sh
jeklly new FOLDER_NAME
```

Finally, check that the site can be run locally:

```sh
bundle exec jekyll serve --watch
```