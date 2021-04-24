1. Data curation (in `1-data-scraping-curating` folder)
* Java vulnerability descriptions are extracted from [MITRE](http://cve.mitre.org/) and [IBM X-Force](https://exchange.xforce.ibmcloud.com/) websites. These are saved both as comma-seperated values (CSV) files and in a MySQL database.
* The list of top 100 Java project names is extracted.
* Each of the top 100 Java projects are cloned.
* Commit log for each of the top 100 Java projects are generated.
* The commit logs are parsed and saved as a CSV file. Specifically, the commit message and sha as identifier are extracted seperately and saved in another CSV file.
