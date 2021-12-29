

# Scopus Checker
A python script to check which (Google Scholar) documents and citations are missing from Scopus.



## About The Project

If you ever had to cross-check which papers and citations Scopus forgot to index, you would know--it is not fun. This script may provide a little help with that. 

*Please notice that this is a rather unreliable tool, and should only be used for a rough first screening. I take no responsibility for any missed citations or documents. See the license for more information.*




## Getting Started

To get a local copy up and running follow these simple example steps.

### Prerequisites

You are going to need:
- `pip` [https://pip.pypa.io/en/stable/installation/](https://pip.pypa.io/en/stable/installation/)
- `virtualenv` [https://virtualenv.pypa.io/en/latest/installation.html](https://virtualenv.pypa.io/en/latest/installation.html)
- a Scopus subscription (your University will probably provide that?) 

### Installation

1. Clone the repo
   ```sh
   git clone git@github.com:enzodesena/scopus-checker.git
   ```
2. Create python environment
   ```sh
   cd scopus-checker
   virtualenv -p /usr/bin/python3 env
   ```
3. Activate environment
   ```sh
   source env/bin/activate
   ```
4. Install pip packages
   ```sh
   pip install -r requirements
   ```
5. (Optional, but not so optional) Get a free API Scraper Key at [https://www.scraperapi.com](https://www.scraperapi.com) and copy/paste your scraper API key. 



<!-- USAGE EXAMPLES -->
## Usage

Before you can use the tool, you need to download some information from Scopus. 

1. Go to [https://www.scopus.com](scopus.com) and look up your own profile. The free search would not be enough for that. 
2. Go to your own `Documents` -> `Export all`, select `CSV`, and toggle all options under `Citation information` and nothing else; click on `Export` and move the file to your repository directory; we will call this the 'document file'
3. Go to `Cited by XXX Documents` -> `Export all`, select `CSV`, and toggle all options under `Citation information` and also **Include references**; click on `Export` and move the file to your repository directory; we will call this the 'citations file'
4. Go into your repository directory and activate the virtual environment:
   ```sh
   source env/bin/activate
   ```
5. Run the python script:
   ```sh
   python scopus-checker.py -d <document file> -c <citations file> -a '<your name and surname>' -p scraperapi -k <your own scraper api key>
   ```

In step 5, notice how we used the `scraperapi` proxy option. Given how strict Google Scholar has become over the years, this is pretty much the only option that will make this script work. You can also run it without that option, but it is unlikely to work for very long (see [https://scholarly.readthedocs.io/en/stable/quickstart.html#using-proxies](scholarly proxies) for more information. 


<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request


<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.


<!-- CONTACT -->
## Contact

Enzo De Sena - [@enzoresearch](https://twitter.com/EnzoResearch) [desena.org](https://desena.org) 




<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

* This is heavily based on [scholarly](https://github.com/scholarly-python-package/scholarly).
