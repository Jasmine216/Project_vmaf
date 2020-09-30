# Project_vmaf

## Data Analysis

Files of data analysis for results are provided.

## Attention-map Generation

Before quality prediction, run the [Attention model](Attention_video.ipynb) which can generate videos with attention maps. The videos with attention maps are called obj_videos in dataset files.

## Dataset

This project utilizes two datasets including the Netflix public dataset and the LIVE dataset. [Dataset files](resource/dataset) are provided here called LIVE.py and NFLX_dataset_public.py.


## Usages
There are a number of ways one can use the package:

  - [VMAF Python library](resource/doc/VMAF_Python_library.md) offers full functionalities including running basic VMAF command line, running VMAF on a batch of video files, training and testing a VMAF model on video datasets, and visualization tools, etc.
  - [`libvmaf` - a C library](libvmaf/README.md) offers an interface to incorporate VMAF into your C/C++ code.

To improve the accuarcy of the VMAF, many Codes are modified in these two parts.

## Models

Besides the default VMAF model which predicts the quality of videos displayed on a 1080p HDTV in a living-room-like environment, VDK also includes a number of additional models, covering phone and 4KTV viewing conditions. Refer to the [models](resource/doc/models.md) page for more details.


## Results in CSV files

To save results of model prediction for two datasets, codes in python library are modified to write result in csv files instead of show results direcly. Many [CSV files](results_CSV) provide data for analysis.



