# Attention-based Video Multi-method Assessment Fusion (VMAF)

Video Multi-method Assessment Fusion (VMAF) is a video quality metric developed by Netflix to assess automatically the quality of content compressed under different conditions. VMAF was designed on the observation that some state-of-the-art quality metrics correlate well with human judgement for some particular compression artefacts but do not perform as well when the type of distortion is different. Given that lossy compression introduces a combination of the well-known blocking, blurring, ringing and motion artefacts, VMAF runs different state-of-the-art quality metrics devoted to assess a particular artefact and then combines the scores obtained using machine learning, more precisely a Support Vector Machine (SVM) classifier. The parameters used by such SVM have been trained over content representative of on demand video streaming and are provide as baseline configuration which is used to run the metric. The training has been performed by providing the SVM with the subjective scores associated with each video along with the values of the different state-of-the-art quality metrics considered in VMAF’s design. Worth noting that the subjective score provided for each video refers to the whole duration of the clip and doesn’t explicitly carry information on which areas of video frames contributed more to the final score. Having such local information would allow to optimise compression by improving image areas likely to draw more attention than others.

Accordingly, the aim of this project is to improve the estimation of quality provided by VMAF by incorporating an attention model. Such model can be one chosen from the literature or derived by using data coming from camera eye trackers. The project will involve the use of the VMAF’s code base provided by Netflix to extend its workflow and accommodate the use of attention driven processing. Ad-hoc subjective tests are also expected to be designed to collect the data needed by the improved metric.


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

To improve the accuarcy of the VMAF, many Codes are modified in these two parts.Please refer to [C library](libvmaf) and [VMAF Python library](python).

## Models

Besides the default VMAF model which predicts the quality of videos displayed on a 1080p HDTV in a living-room-like environment, VDK also includes a number of additional models, covering phone and 4KTV viewing conditions. Refer to the [models](resource/doc/models.md) page for more details.



## Results in CSV files

To save results of model prediction for two datasets, codes in python library are modified to write result in csv files instead of show results direcly. Many [CSV files](results_CSV) provide data for analysis.



