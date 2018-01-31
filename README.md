# circDeep: End-to-End learning framework for circular RNA classification from other long non-coding RNA using multimodal deep learning
circDeep fuse RCM descriptor, ACNN-BLSTM sequence descriptor and conservation descriptor into high level abstraction descriptors, where the shared representations across different modalities are integrated. The experiments show that circDeep is not only faster than existing tools but also performs at an unprecedented level of accuracy by achieving a 12 percent increase in accuracy over other existing tools.

Authors: [Bioinformatics Lab](http://bioinformatics.louisville.edu/lab/index.php), [Kentucky Biomedical Research Infrastructure Network (KBRIN)](http://louisville.edu/research/kbrin/), University of Louisville

## Prerequisites
We recommend to use [Anaconda 3](https://www.anaconda.com/download/) platform. 
- [Keras](https://github.com/antoniosehk/keras-tensorflow-windows-installation) (Deep learning library)

- [scikit-learn](https://github.com/scikit-learn/scikit-learn) (Machine learning library)

- [h5py](https://anaconda.org/conda-forge/h5py)

- [gensim](https://anaconda.org/anaconda/gensim) 

- [pysam](https://github.com/pysam-developers/pysam) >= 0.9.1.4

- [pybigwig](https://bioconda.github.io/recipes/pybigwig/README.html)


## Usage

```bash 
usage: circDeep.py [-h] --train TRAIN --genome GENOME -gtf GTF --bigwig BIGWIG
               [--seq SEQ] [--rcm RCM] [--cons CONS] [--predict PREDICT]
               [--out_file OUT_FILE] [--model_dir MODEL_DIR] 
               [--positive_bed POSITIVE_BED] [--negative_bed NEGATIVE_BED] 
               [--testing_bed TESTING_BED] 

ircular RNA classification from other long non-coding RNA using multimodal deep learning

Required arguments:
=================== 
   --data_dir <data_directory>
                        Under this directory, you will have descriptors files
  --train TRAIN         use this option for training model
  --genome GENOME       Genome sequence. e.g., hg38.fa
  --gtf GTF             The gtf annotation file. e.g., hg38.gtf
  --bigwig BIGWIG       conservation scores in bigWig file format
                        
 optional arguments:
====================

   -h, --help            show this help message and exit
  --seq SEQ             The modularity of ACNN-BLSTM seq
  --rcm RCM             The modularity of RCM
  --cons CONS           The modularity of conservation
  --predict PREDICT     Predicting circular RNAs. if using train, then it will
                        be False
  --out_file OUT_FILE   The output file used to store the prediction
                        probability of testing data
  --model_dir MODEL_DIR
                        The directory to save the trained models for future
                        prediction
   --positive_bed POSITIVE_BED
                        BED input file for circular RNAs for training, it
                        should be like:chromosome start end gene
  --negative_bed NEGATIVE_BED
                        BED input file for other long non coding RNAs for
                        training, it should be like:chromosome start end gene
  --testing_bed TESTING_BED
                        BED input file for testing data, it should be
                        like:chromosome start end gene
```

## License

Copyright (C) 2017 .  See the [LICENSE](https://github.com/UofLBioinformatics/seekCRIT/blob/master/LICENSE)
file for license rights and limitations (MIT).
