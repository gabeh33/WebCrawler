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

* test
```
code blocks for commands
```

## Help

Any advise for common problems or issues.
```
command to run if program contains helper info
```

## Authors

Contributors names and contact info

ex. Dominique Pizzie  
ex. [@DomPizzie](https://twitter.com/dompizzie)

## Version History

* 0.2
    * Various bug fixes and optimizations
    * See [commit change]() or See [release history]()
* 0.1
    * Initial Release

## License

This project is licensed under the [NAME HERE] License - see the LICENSE.md file for details

## Acknowledgments

Inspiration, code snippets, etc.
* [awesome-readme](https://github.com/matiassingers/awesome-readme)
* [PurpleBooth](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2)
* [dbader](https://github.com/dbader/readme-template)
* [zenorocha](https://gist.github.com/zenorocha/4526327)
* [fvcproductions](https://gist.github.com/fvcproductions/1bfc2d4aecb01a834b46)
README for Gabe Holmes Project5 - Web Crawler 
This project proved to be simplier than the other projects we have worked on. The high level approach is pretty simple. The crawler sends a GET request to the login page, and reads its response. The response inlcudes a csrf token that needs to be supplied along with the username and password. This inforamtion, along with the cookie provided, is supplied in a POST request to the login page. This was the most challenging part of the projet for me. I had my browser open and made many login requests in order to see exactly what my browser was sending. This information was very useful and I was able to extract the important information and create my own post request. The server then lets the crawler log in by sending it a sessionid. I then moved on to parsing the HTML for links, and adding them to the frontier if they have not already been visited. I ran into a problem trying to crawl these pages at first. I did not realize that the server will respond with a new sessionID occassionaly, and I cannot just use the one provided after logging in. Once I checked for a new sessionID after every request the crawler was able to start working. However, the first few runs I noticed the crawler would stop working after about 1000 requests. I then tried opening a new socket after every 100 requests, and this solved the issue. Finally, after some more html parsing, I was able to get the 5 flags and print them out, then exit the program. 
