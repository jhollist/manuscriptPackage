![travis_badge](https://travis-ci.org/jhollist/manuscriptPackage.svg)

manuscriptPackage
====================

This repository contains materials for using an R package to distribute a reproducible manuscript. Since it is structured as an R package all scripts can be saved as functions in /R, data stored in /data, and the manuscript stored as an R Markdown file in /vignettes.  

The current template is a generic manuscript and could be used for draft versions of a manuscript or possible for pre-prints.  In the future having additional .latex files for other journals (e.g. plos, JSS, etc.) that parse the YAML would be useful.  Don't know if I will get around to that.  

#Install the Package
To install the package and gain access to the materials do the following:
```
install.packages("devtools")
library("devtools")
install_github("jhollist/manuscriptPackage",build_vignettes=TRUE)
library("manuscriptPackage")
```
If this were a real manuscript, the data used in this manuscript would be available via:
```
#This does not work as no data are included with this example
data(manuscript_data)
```
And the manuscript vignette can be read via:
```
vignette("manuscript",package="manuscriptPackage")
```

#How to use this?
As this is a function-free package (if they were all this easy to build!), it has little use currently being installed into R (except if you want to view the rendered output with `vignette()`).  It is useful, however, as a starting point for new manuscripts.  The way I have used it is as follows:

1. Fork it
2. Rename it.  You will need to rename the Github repo, rename the package in `DESCRIPTION`, rename `manuscriptPackage-package.r` and change the name in the `manuscriptPackage-package.r` documentation.
3. Add some functions in /R.
4. Add your data in /data.
5. Edit /vignettes/manuscript.Rmd to include your manuscript.  The manuscript.Rmd included here provides for an example of how to layout the document and includes all(?) allowed YAML. Tables and figures with captioning and references in a .bib file are also include.
6. Commit, push, and share!

## Or, use it as a .Rmd template
So huge thanks go to @Pakillo, who wrapped this template up, along with some others, to be used directly from the RStudio interface. His repo, [rmdTemplates](https://github.com/Pakillo/rmdTemplates) has the details on install.  Once installed you can seled the template and knit direcly from RStudio.  Thanks Francisco!

#Thanks
The inspiration for housing a  manuscript entierly within a package came from two sources.  First, @rmflight has two blog posts about this concept.  [First post](http://rmflight.github.io/posts/2014/07/analyses_as_packages.html) lays out the idea and the [second post](http://rmflight.github.io/posts/2014/07/vignetteAnalysis.html) details the steps to do it. Second is @cboettig's [template package](https://github.com/cboettig/template).  

Everything here is built upon their efforts.  The latex template is a modified version of the default latex template that ships with pandoc/rstudio.

#Questions/Suggestions
If you have any questions about this template, please use the issues in this repository.  I will do my best to get back to you quickly.

If I have messed something up or if you have some thoughts on ehancements (i.e. different latex templates/YAML) please fork, make those changes and submit a pull request.
