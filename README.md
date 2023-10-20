# Domain adaptability of deep learning and feature based methods for image matching

### Abstract
This repository contains the python code for conducting the software experiment as well as evaluation scripts and result files.
The respective scientific paper was written in German, nevertheless the code/documentation is written in English. 

### Prerequisites
The code was tested with Python 3.10.9 and the following packages:
* kornia 0.7.0
* kornia-moons 0.2.8
* kornia-rs 0.0.8
* numpy 1.23.5
* pytorch 2.0.1
* matplotlib 3.5.3
* pandas 1.5.3
* tqdm 4.65.0
* seaborn 0.12.2

Set up and activate a virtual conda environment with the following command:
```
conda create -n <env_name> python=3.10.9
conda activate <env_name>
```
Install the required packages with the following command:
```
pip install -r requirements.txt
```

### Downloading the HPatches dataset
To start the download that extracts all the files necessary for this experiment just run the following shell script:
```
./download.sh
```
Reference: Dusmanu et al. (2019) - https://github.com/mihaidusmanu/d2-net/blob/master/hpatches_sequences/download.sh

### Executing the experiment
For each algorithm, the experiment can be started by running the respective python script located in the folder "extraction", e.g.:
```
python extraction/extractDISK.py
```
For each image, a .npz file with the extracted keypoints and descriptors will be created in the folder "hpatches_sequences/hpatches-sequences-results/[imageName]".


The used algorithms support CUDA acceleration, if a CUDA capable GPU is available. To facilitate the process, a Google Colab notebook was created that executes every ne. The resulting result.zip file needs to be downloaded and extracted into the root folder of this project to guarantee the correct functionality of the evaluation scripts. Access to this notebook can be granted upon request.

### Evaluation
For evaluating the Mean Matching Accuray (MMA) execute the following script (See also: https://github.com/mihaidusmanu/d2-net/blob/master/hpatches_sequences/HPatches-Sequences-Matching-Benchmark.ipynb):
```
python evaluation/evaluate_mma.py
```

For evaluating other metrics (e.g. M-Score, Repeatability) execute the following script:
```
python evaluation/evaluation.py
```
Results will be found in the respective files under /res.

### Contact
For further questions or inquiries please contact the owner of this repository.


