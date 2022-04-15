
# LinMLTBS
A <u>L</u>inear time <u>M</u>ulti-<u>l</u>evel <u>T</u>hresholding approach for finding <u>B</u>inding <u>S</u>ites in ChIP-Seq data.

This is an implementation of the method described in:

```
Musab Naik, Luis Rueda & Akram Vasighizaker (2021).
Identification of Enriched Regions in ChIP-seq Data via a Linear-time Multi-level Thresholding Algorithm.
Published in: IEEE/ACM Transactions on Computational Biology and Bioinformatics
DOI: 10.1109/TCBB.2021.3104734 (https://ieeexplore.ieee.org/document/9514438)
```


<!-- TABLE OF CONTENTS -->
## Table of Contents

* [About the Project](#about-the-project)
  * [Built With](#built-with)
* [Getting Started](#getting-started)
  * [Prerequisites](#prerequisites)
  * [Datasets Used](#datasets-used)
  * [Installation](#installation)
* [Usage](#usage)
* [Roadmap](#roadmap)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)
* [Acknowledgements](#acknowledgements)



<!-- ABOUT THE PROJECT -->
## About The Project

Chromatin immunoprecipitation followed by high-throughput sequencing (ChIP-Seq) is a powerful method for identifying genome-wide DNA-Protein interaction. However, putative identification of binding sites from the millions of short reads aligned over the reference genome is truly a bioinformatic challenge that requires considerable computational resources.

LinMLTBS is peak calling method that works on the principle of Linear-time Optimal Multi-level thresholding. Using concepts such as Otsu's between class criterion, SMAWK algorithm, indices of validity, and concurrent multiprocessing, LinMLTBS has shown promising results when compared to existing peak calling methods. 

### Built With

* [Python](https://www.python.org/)
* [Cython](https://cython.org/)

The implementation of LinMLTBS is based on Python 3.7.6.
As pure Python will always be slower than any compiled language, the implementation is complied in Cython to gain a bit of speed.

However, as the use of Cython's special syntax is minimal and the entire project can be operated in pure Python mode with little to no change in the code.

<!-- GETTING STARTED -->
## Getting Started

The following steps can be followed in order to replicate the results shown in the paper. The prerequisites, datasets used, installation, pre-processing needed, etc. are all mentioned down below:

### Prerequisites
*Python 3.6+

The implementation depend on the following Python libraries:

* numpy
* pandas
* pyBigWig
* multiprocessing
* Cython

### Datasets Used
*Target protein: H3K27ac

| Cell-line 	| Encode Accession no. 	| GEO Accession no. 	|
|-----------	|----------------------	|-------------------	|
| GM12878   	| ENCSR000AKC          	| GEO:GSM733771     	|
| HSMM      	| ENCSR000ANF          	| GEO:GSM733755     	|
| HUVEC     	| ENCSR000ALB          	| GEO:GSM733691     	|
| K562      	| ENCSR000AKP          	| GEO:GSM733656     	|
| NHEK      	| ENCSR000ALK          	| GEO:GSM733674     	|
| NHLF      	| ENCSR000AMR          	| GEO:GSM733646     	|

### Installation

1. Clone the repo
```sh
git clone https://github.com/MusabNaik/LinMLTBS.git
```
2. Install the necessary libraries

3. Download the ChIP-Seq dataset from:
* [ENCODE PORTAL](https://www.encodeproject.org/)
OR
* [ENCODE ChIP-seq Experiment Matrix](https://genome.ucsc.edu/ENCODE/dataMatrix/encodeChipMatrixHuman.html)

4. Install [Juypter Notebook](https://jupyter.org/) or any other Python IDE 


<!-- USAGE EXAMPLES -->
## Usage

### Pre-processing 

The implementation requires the input file to be in .bigwig format.

All the example datasets previously mentioned are in the required '.bigwig' format, however if need be, the more commonly available '.bam' format can be easily converted into '.bigwig' using the the tool [bamCoverage](https://deeptools.readthedocs.io/en/develop/content/tools/bamCoverage.html)

### Running the Code

The project includes an IPython notebook which contains the entire code. The notebook is self explanatory and contains comments on how to run it.

The project also includes the individual functions such as SMAWK, MFILL, REDUCE, multiWindow, etc. as individual modules so that they can be imported into other projects.

<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/MusabNaik/LinMLTBS/issues) for a list of proposed features (and known issues).

<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contacts

Musab Naik -  naikm@uwindsor.ca

Luis Rueda - lrueda@uwindsor.ca

Akram Vasighizaker - vasighi@uwindsor.ca

Project Link: [https://github.com/MusabNaik/LinMLTBS](https://github.com/MusabNaik/LinMLTBS)



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
This research work has been partially supported by the Natural Sciences and Engineering Research Council of Canada, NSERC. The authors would like to thank the University of Windsor Office of Research Services and Innovation.
