# searchrefiner

_Systematic Review Query Visualisation and Understanding Interface_

searchrefiner is an interactive interface for visualising and understanding queries used to retrieve medical literature for
[systematic reviews](https://en.wikipedia.org/wiki/Systematic_review).

It is currently in development, however please find a demo link [on the project home page](https://ielab.io/searchrefiner).

## Building

searchrefiner is built as a Go application. It needs to be installed slightly differently than most Go applications:

 1. First, clone this repository.
 2. Configure the application. The application can then be configured via a `config.json` (a [sample](sample.minimal.config.json) is provided). In this minimal file, everything up to and including `Entrez` needs to be configured. The other options below this key do not need to be configured to run searchrefiner in a minimal setting and they should not be changed unless you know what you are doing. Many of the tools require specific attributes in the configuration. Please get in contact if you are setting up your own instance of searchrefiner to determine how these advances configuration items should be set. 
 3. Ensure that `g++-5` and `cmake` are installed on your system.
 4. Run `make run`. This will download all of the necessary dependencies and run the application. 

At the moment, you still need to make an account to use searchrefiner, even locally. The account that you make is a local account and is not the same as the one you might create on another instance of searchrefiner.

## Docker build
searchrefiner can also be run from a preprepared [Dockerfile](./Dockerfile):
1. Setup the docker image with `docker build -t ielab-searchrefiner .`
2. Create a `config.json` file (see above)
3. Run the server with `docker run --net=host ielab-searchrefiner`
4. Open the site at [http://localhost:4853](http://localhost:4853)


## Documentation

Documentation for authentication, administration, and usage can be found at the project homepage: 
[ielab.io/searchrefiner](https://ielab.io/searchrefiner)

## Citing

Please cite any references to the searchrefiner project as:

```
@inproceedings{scells2018searchrefiner,
    Author = {Scells, Harrisen and Zuccon, Guido},
    Booktitle = {Proceedings of the 27th ACM International Conference on Information and Knowledge Management},
    Organization = {ACM},
    Title = {searchrefiner: A Query Visualisation and Understanding Tool for Systematic Reviews},
    Year = {2018}
}
```

Please cite any references to any of the automation tools embedded in searchrefiner as:

```
@inproceedings{li2020systematic,
	Author = {Li, Hang and Scells, Harrisen and Zuccon, Guido},
	Booktitle = {Proceedings of the 43rd Internationa SIGIR Conference on Research and Development in Information Retrieval},
	Date-Added = {2020-06-09 13:11:19 +1000},
	Date-Modified = {2020-07-03 15:45:14 +1000},
	Month = {July},
	Pages = {25--30},
	Title = {Systematic Review Automation Tools for End-to-End Query Formulation},
	Year = {2020}
}
```
