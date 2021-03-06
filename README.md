## java-codesecurity
### Analysis of Java's Common Vulnerabilities and Exposures in GitHub's Projects

This ongoing project is in partial fulfilment of the degree of Master of Science, Software Engineering.

The central question aimed to be answered by this study is: How secured are the codes written in the top 100 GitHub's Java projects?

In answering this central question, the following are the objectives of the study:
* Identification of Java's CVE entities through text analysis of MITRE's vulnerability descriptions.
* Identification of security-related themes in the projects' commits through text analysis of the commit messages.
* Identification of vulnerabilities in the GitHub's Java projects using Variant Analysis with CodeQL.


#### Research Process
1. Data curation (in `1-data-scraping-curating` folder)
* Java vulnerability descriptions are extracted from [MITRE](http://cve.mitre.org/) and [IBM X-Force](https://exchange.xforce.ibmcloud.com/) websites. These are saved both as comma-seperated values (CSV) files and in a MySQL database.
* The list of top 100 Java project names is extracted.
* Each of the top 100 Java projects are cloned.
* Commit log for each of the top 100 Java projects are generated.
* The commit logs are parsed and saved as a CSV file. Specifically, the commit message and sha as identifier are extracted seperately and saved in another CSV file.

2. Text analysis (in `2-text-classification-CVE-Commits` folder)
* Text pre-processing to extract vulnerability phrases from the Java's vulnerability descriptions extracted from [MITRE](http://cve.mitre.org/).
* Analysis of the extracted vulnerability phrases with `NLTK` and `Wordnet Lemmatizer` to actualize vulnerability-representative tokens. These are visualized to identify the prominent Java vulnerability tokens from the MITRE.
* Tokenization of the projects' git commit messages and identification of mutual tokens with the MITRE's Java vulnerabilities tokens.

3. Variant analysis using CodeQL
* Conversion of the codebase to database for CodeQL functionality using this command from the home directory. 

 *codeql database create database --language=language-identifier*
 
  Example: codeql database create C:\Users\Semiu\JavaCodeQLDb\zxing_zxing --language=java
 
  The detailed process of creating CodeQL databases can be found [here](https://codeql.github.com/docs/codeql-cli/creating-codeql-databases/).

