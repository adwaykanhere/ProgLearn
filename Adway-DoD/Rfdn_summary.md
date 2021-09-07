# When are Deep Networks really better than Random Forests at small sample sizes?

Paper:

[![arXiv](https://img.shields.io/badge/arXiv-2108.13637-red.svg?style=flat)](https://arxiv.org/abs/2108.13637)


## Abstract
- Compare the performance and conditions between DNN and RF for number of features and sample sizes.
- Choose datasets with atleast 10,000 samples across image,audio and tabular settings.
- RF rocks at structured and tabular data with smaller sample sizes.
- DN rocks at larger sized structured data.

## 1. Tabular

### Methods
- Used OpenML CC-18 dataset
- Downsampled to 10,000 samples
- RF used 500 trees with no depth limit but varying number of features.
- DN were optimized based on similar prior work.

### Evaluation

- Cohen's Kappa and Expected Calibration error (ECE)
- Performance calculated in both cases by subtracting metric for DN from RF at each sample size

### Results

At larger sample sizes, RF wins on CK and accuracy while DN win on ECE with better calibration

## 2. Image

### Methods
- Data from CIFAR-10 and CIFAR-100
- Expreimented with 3,8,90 class settings
- Classical arch: RF and SVC-rbf
- DNN arch: 3 custom models and pretrained Resnet-18

### Evaluation

Classificaton accuracy and training wall times

### Results

- Unbounded time and cost: RF & SVM good at small sizes; eventually got beaten by CNN. CNN dominated at higher class experiments.
- SVM-rbf training times were much larger while that of RF were consistent. DN training times descended at 100 samples with early stopping but increased with larger sample sizes and took more time.
- **DN benefit from larger sample sizes and classes. RF/SVM dominated with better accuracy at smaller samples and time constraints**


## 3. Audio

### Methods
- Data from Free Spoken Digit dataset
- Main preprocessing includes computing short time Fourier transform to generate spectrograms. Mel-spectrograms and Mel-freq cepstral coeff were also computed.

### Evaluation
Classification accuracy 

### Results

- RF completely dominated performance for all sample sizes and number of classes.
- Resnet-18 failed on both conditions

## *Future directions*
- Add more metrics and experiments
- Optimize HPP search for each sample size
- Extend by using other models/estimators
