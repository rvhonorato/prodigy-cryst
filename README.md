# Interface Classifier  
Collection of scripts to predict whether an interface in a protein-protein 
complex is biological or crystallographic from its atomic coordinates.

## Installation

Clone the repository:
```
git clone http://github.com/haddocking/interface-classifier
```

Its easier with Anaconda:
```
conda create -n interface_classifier python=3.6
conda activate interface_classifier
pip install biopython
pip install -U scikit-learn==0.21.3
```

Install freesasa v1.0
```
wget https://github.com/mittinatten/freesasa/releases/download/1.0/freesasa-1.0.tar.gz
tar -xzvf freesasa-1.0.tar.gz
cd freesasa-1.0
./configure && make && make install
```

Edit `interface-classifier/prodigy_cryst/config.py`

Example:
```python
# (Absolute) Paths to the freesasa binary and config files
FREESASA_BIN = "/Users/rodrigo/software/freesasa-1.0/src/freesasa"

# No need to set this if FreeSASA version is >= 2:
FREESASA_PAR = "/Users/rodrigo/software/freesasa-1.0/share/naccess.config"
```

## Have fun!
```

## Usage

```bash
python interface_classifier.py <pdb file> [--selection <chain1><chain2>]
```

Type --help to get a list of all the possible options of the script.

## Dependencies  
* The scripts rely on [Biopython](www.biopython.org) to validate the PDB structures and calculate interatomic distances.
* [freesasa](https://github.com/mittinatten/freesasa), with the parameter set used in NACCESS ([Chothia,1976](http://www.ncbi.nlm.nih.gov/pubmed/994183)), is also required for calculating the buried surface area. Both 2.x and 1.x version series are supported.
* [scikit-learn](https://github.com/scikit-learn/scikit-learn) for Python 3 is necessary to load and use the classifier.

To install and use the scripts, just clone the git repository or download the tarball zip
archive. Make sure `freesasa`, Biopython and scikit-learn are accessible to the Python scripts
through the appropriate environment variables ($PYTHONPATH).

## License  
These utilities are open-source and licensed under the Apache License 2.0. For more information
read the LICENSE file.

