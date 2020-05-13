# BookNuggets V2
This is the repository supporting the new BookNuggets GitHub Pages site.

## Why Re-factor BookNuggets?
Having learned a little web development, I realised that the old way of updating BookNuggets was extremely inefficient. Whenever I wanted to post a new summary, I had to add it to the YAML front matter of the `index.html` file. Then, I would need to add that same text to the YAML front matter of the page of whichever category it belonged to. As I read more books, the length of the YAML front matter grew exponentially longer. I figured that this could be done better if the site was designed using Jekyll.

I also used this as an excuse to practice my newly-acquired skills in web development, instead with a new tool (Jekyll). For learning purposes, I will be documenting my process for developing the site here.

## Why Jekyll?
Simple: GitHub Pages is built on Jekyll. Therefore, to make the best use of GitHub Pages, a site hosted there (like BookNuggets) should be designed with Jekyll. That might seem obvious, but there are plenty of sites out there that simply have an `index.html` file and an accompanying stylesheet sitting in the main folder. That means that these files end up underutilising some of the amazing features that Jekyll brings:

1. Use of layouts for flexibility
2. Use of Liquid Syntax for logic
3. Writing posts in markdown (and I **love** writing in markdown)

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

## Mistakes
As a first-timer in developing a Jekyll site, I learned some lessons the hard way. I'm documenting them so that I won't repeat them.

### Building the Site for a Local Server
When you run a local server, Jekyll builds the site by duplicating files and folders without an underscore prefix into a folder called `_site`. This allows it to serve the site in a local web server. At first, I edited the homepage in the `index.html` in the `_site` folder. After losing all my edits when I refreshed the page in the local browser did I realise that this was how Jekyll worked. Don't make the same stupid mistake: don't edit anything in the `_site` folder.

### Relative Filepaths
At first, I thought there was a discrepancy in how (1) local pages, (2) the home page on GitHub, and (3) post pages on GitHub linked to assets. From cross-referencing my Data&Stuff blog repository, I realised that using the paths defined in `_config.yml` was important to ensure that all pages referred to the same relative files and folders. The solution: when deploying, modify the URLs in `_config.yml`.