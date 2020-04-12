Flexdashboard Example
=====================
[Flexdashboard][1] uses [R Markdown][2] to publish data visualizations as a dashboard.

This project shows how to create and host one of your own using Github Pages.

Getting Started
---------------
Install Homebrew

    ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

Install R and Pandoc

    brew tap homebrew/science
    brew install r
    brew install pandoc

Start the R console and install the flexdashboard package

    r
    install.packages("flexdashboard")

Create a new flexdashboard R Markdown file from the R console

    rmarkdown::draft("index.Rmd", template = "flex_dashboard", package = "flexdashboard")

Create `_site.yml`

    name: "my-website"
    output_dir: docs

Render the site

    rmarkdown::render_site()

Note about README.md
--------------------
The rmarkdown renderer will also process your `README.md` file into `docs/README.html` which will
override `index.html` as the default page for the URL. In order to prevent the `docs/README.html`
file from being commited, add it to `.gitignore`

    echo docs/README.html >> .gitignore

Host on Githb
-------------
After you've created a new github repository (use <https://github.com/new>), commit
and push the site.

    git add -A
    git commit -m "create flexdashboard site"
    git remote add origin https://github.com/pbatey/flexdashboard-example.git
    git push -u origin master

Then enable GitHub Pages. Set **Source** to **master branch /docs folder** in the
*GitHub Pages* section of the repository settings.

Visit your flexdashboard on GitHub!

### <https://pbatey.github.io/flexdashboard-example/>

[1]: http://rmarkdown.rstudio.com/flexdashboard/
[2]: http://rmarkdown.rstudio.com/
