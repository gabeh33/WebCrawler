# Web Crawler 

This project crawls fakebook.3700.network looking for the secret flags related to the provided user. 

## Description

The program WebCrawler takes in a username and password for the website fakebook.3700.network, logs in as that user, and then generates HTTP1.1 GET requests in an attempt to find 5 secret flags located somewhere on the website. The flags are embedded within the HTML and start with ```<h2 class='secret_flag' style="color:red">```. There is also a list of other users pages on each page that the crawler will visit. The crawler adds these pages to a stack and that is how it explores the frontier. The program also needs to keep track of the csrf token and sessionID that is provided when it logs in as a user. If both printResponses and printCrawling in the source code are false, then the only output will be the 5 flags as the program finds them. 

## Getting Started

### Dependencies

* No non-native dependinces. In addition, all HTML parsing and GET/POST requests are made from scratch without any outside libraries. 

### Installing

* To install simply download the source code seen above. 
### Executing program

* To run, you need to have python installed. 
* Then download the source code, and make the file webcrawler executable by typing
```
chmod +x webcrawler
```
* Then you can run the program by typing 
```
./webcrawler [username] [password]
```

## Authors

Gabe Holmes
https://www.linkedin.com/in/gabe-holmes/
holmes.ga@northeastern.edu

## Version History

* 0.1
    * Initial Release

