# ShinyBuilder

ShinyBuilder is a point-and-click dashboard platform based on [R/Shiny](http://www.rstudio.com/shiny/) which makes it simple to create and share live, connected dashboards.

ShinyBuilder was created with the following goals:
* __Easy Access__ - Can be accessed from any web browser  
* __Easy Authoring__ - Dashboards are created via a point-and-click GUI, enabling anyone with basic SQL skills to set up a professional dashboard in a matter of minutes.  
* __Instantly Connected__ - ShinyBuilder charts begin as SQL queries, and are immediately linked to a live database.  Once created, the charts are refreshed daily & automatically, eliminating need to build ETL workflows.  
* __Extensible & Modular__ - all major JavaScript libraries used in the project have been wrapped into resusable R/Shiny packages, making it easy to extend ShinyBuilder or to use ShinyBuilder components in your own projects.  

ShinyBuilder components include:
* [shinyGoogleCharts](https://github.com/mul118/shinyGoogleCharts) - functions for displaying and interactively editing [Google Charts](https://developers.google.com/chart/) in Shiny 
* [shinyMCE](https://github.com/mul118/shinyMCE) - integrates [TinyMCE](http://www.tinymce.com/index.php) WYSIWYG text editor into Shiny
* [shinyAce](https://github.com/trestletech/shinyAce) - integrates [Ace](http://ace.c9.io/#nav=about) code editor into Shiny
* [shinyGridster](https://github.com/wch/shiny-gridster) - integrates the [gridster.js](http://gridster.net/) draggable framework into Shiny


## Install 

To install, run

```r
if (!require("devtools"))
  install.packages("devtools")
devtools::install_github("ShinyBuilder", "iheartradio")
```

If want to run ShinyBuilder from server, install [Shiny Server](http://www.rstudio.com/shiny/server/)

## Configure

* Add information for your database(s) of choice to the db_list.R file
* Set up cron job to update all dashboards by running the update_dashboards.R script 

```
sudo Rscript /srv/shiny-server/ShinyBuilder/R/update_dashboards.R 
```

## Use

Live demo of the open source candidate code is available at: http://shiny.iheart.com:3838/shiny-dashboards/dashboards/ShinyBuilder/

## Frontend Development

Javascript and CSS files are minified for improved performance, with the distribution files located in the `www` folder.  If you would like to develop either the CSS or Javascript, you can find the source files in the `web` folder.

You will need [npm](https://www.npmjs.org/) installed to setup the development environment, this can be done on a Macintosh via [Homebrew](http://brew.sh/) with `brew install npm`.

Once npm is installed, navigate to the web directory and run the following to setup your development environment and write the distribution files:

```
npm install
grunt
```

Running grunt will compile the source files in the web folder into their distribution versions and watch for changes within the file system, automatically recompiling the frontend files and checking for Javascript errors.

__NOTE:__ For the open source release, the demo will be hosted externally at RStudio's [ShinyApps](http://www.rstudio.com/shiny/hosted/) service.



    